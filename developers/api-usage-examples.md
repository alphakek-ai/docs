---
icon: rectangle-terminal
---

# API Usage Examples

The only pre-requisite to start using Alpha API is to obtain a token. Learn about it in [#authentification](developer-api.md#authentification "mention").

## Checking Account Status

***

The code sample below checks the account status of the API token owner: API Credits balance, User Tier, and $AIKEK balance. This API endpoint is free.

{% tabs %}
{% tab title="Python" %}
```python
import requests  # pip install requests

api_key = "YOUR_TOKEN_HERE"
url = "https://api.alphakek.ai/account"

response = requests.get(url, headers={"Authorization": f'Bearer {api_key}'})

user_data = response.json()

print(f"User credits: {user_data['credits']}")
print(f"User tier: {user_data['tier']}")
print(f"Amount of $AIKEK in USD: {user_data['tokens_usd']}")
```
{% endtab %}

{% tab title="JavaScript" %}
```javascript
const api_key = "YOUR_TOKEN_HERE";
const url = "https://api.alphakek.ai/account";

fetch(url, {
  method: 'GET',
  headers: {
    'Authorization': `Bearer ${api_key}`
  }
})
.then(response => {
  if (response.ok) {
    return response.json();
  }
  throw new Error('Network response was not ok.');
})
.then(user_data => {
  console.log(`User credits: ${user_data['credits']}`);
  console.log(`User tier: ${user_data['tier']}`);
  console.log(`Amount of $AIKEK in USD: ${user_data['tokens_usd']}`);
})
.catch(error => {
  console.error('There has been a problem with your fetch operation:', error);
});
```
{% endtab %}
{% endtabs %}

## Comparing Our AI Models

***

This code sample calls [developer-api.md](developer-api.md "mention") for each of the three available [ai-playground.md](../research/ai-playground.md "mention") [universal-agents.md](../launch/universal-agents.md "mention"), asks them the same question, and returns a streaming response.

**Note**: The code sample below spends 6 API Credits upon running.

{% tabs %}
{% tab title="Python" %}
```python
from openai import OpenAI

client = OpenAI(
    api_key="YOUR_TOKEN_HERE",
    base_url="https://api.alphakek.ai/v1"
)
question = "What to expect from Ethereum ETFs?"
print("Question:", question)

models = ["versa", "nexus", "eclipse"]
for model in models:
    response = client.chat.completions.create(
        model=model,
        messages=[
            {
                'role': 'user',
                'content': question
            }
        ],
        stream=True,
    )

    print(f"\n\nResponse from the {model.capitalize()} model:")
    for chunk in response:
        if chunk.choices[0].delta.content is None:
            continue
        print(chunk.choices[0].delta.content, end="")

```
{% endtab %}

{% tab title="JavaScript" %}
```javascript
import OpenAI from 'openai';

const apiKey = "YOUR_TOKEN_HERE";
const client = new OpenAI({
    apiKey: apiKey,
    baseURL: 'https://api.alphakek.ai/v1'
});

const question = "What to expect from Ethereum ETFs?";
console.log("Question:", question);

const models = ["versa", "nexus", "eclipse"];
models.forEach(async model => {
    try {
        const stream = await client.chat.completions.create({
            model: model,
            messages: [{
                role: 'user',
                content: question
            }],
            stream: true,
        });

        console.log(`\n\nResponse from the ${model.charAt(0).toUpperCase() + model.slice(1)} model:`);
        for await (const chunk of stream) {
            if (chunk?.choices[0]?.delta?.content) {
                process.stdout.write(chunk.choices[0].delta.content);
            }
        }
    } catch (error) {
        console.error('Error handling:', error);
    }
});
```
{% endtab %}
{% endtabs %}
