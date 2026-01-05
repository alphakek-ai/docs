---
description: Generate memes, edit images, and more!
icon: message-image
---

# Memelord API

{% hint style="info" %}
Memes API has been deprecated in favor of the [#aikek-memelord](../launch/universal-agents.md#aikek-memelord "mention"), our new method of delivering our [universal-agents.md](../launch/universal-agents.md "mention") and [fractal.md](../fractal.md "mention") data infra to B2B.
{% endhint %}

## Pipelines

***

Our Memes API provides access to all of our [#graphic-pipelines](../create/meme-generator.md#graphic-pipelines "mention"): Text-to-Image, Effect, and Mirage. Read about [#authentification](developer-api.md#authentification "mention") if that's your first time using Alphakek API.

{% hint style="info" %}
Input image requirements: PNG or JPG format, size under 2MB
{% endhint %}

{% openapi src="https://api.alphakek.ai/openapi.json" path="/visuals/create_image" method="post" %}
[https://api.alphakek.ai/openapi.json](https://api.alphakek.ai/openapi.json)
{% endopenapi %}

{% hint style="danger" %}
Code examples in the next two widgets are WRONG! There seems to be a bug on GitBook's side. Refer to [#sending-form-data-requests](memelord-api.md#sending-form-data-requests "mention") for the correct code snippet.
{% endhint %}

{% openapi src="https://api.alphakek.ai/openapi.json" path="/visuals/apply_effect" method="post" expanded="false" %}
[https://api.alphakek.ai/openapi.json](https://api.alphakek.ai/openapi.json)
{% endopenapi %}

{% openapi src="https://api.alphakek.ai/openapi.json" path="/visuals/appy_mirage" method="post" %}
[https://api.alphakek.ai/openapi.json](https://api.alphakek.ai/openapi.json)
{% endopenapi %}

## Sending form-data requests

`/visuals/apply_effect` and `/visuals/appy_mirage` are using `multipart/form-data` format. Imagine you have a file named `selfie.png`. In this case, you'll need to call the following code:

{% tabs %}
{% tab title="Python" %}
```python
import requests  # Run `pip install requests` if you haven't installed it yet

url = 'https://api.alphakek.ai/visuals/apply_effect'
headers = {
    'accept': 'application/json',
    'Authorization': 'Bearer XXXXX'  # Replace with your API key
}
files = {
    'image': ('selfie.png', open('selfie.png', 'rb'), 'image/png')
}
data = {
    'prompt': 'scary clown',  # modifty these parameters as needed
    'seed': '123456',
    'allow_nsfw': 'true'
}

response = requests.post(url, headers=headers, files=files, data=data)

if response.status_code == 200:
    with open('output.png', 'wb') as f:
        f.write(response.content)
else:
    print(f"Failed with status code {response.status_code}")
    print(response.text)
```
{% endtab %}

{% tab title="JavaScript" %}
```javascript
// Run `npm install axios form-data` before executing this script
import axios from 'axios';
import FormData from 'form-data';
import fs from 'fs';

const url = 'https://api.alphakek.ai/visuals/apply_effect';
const headers = {
    'accept': 'application/json',
    'Authorization': 'Bearer XXXXXXXXX'  // Replace with your API key
};

const formData = new FormData(); // Replace with your image and parameters
formData.append('image', fs.createReadStream('selfie.png'), 'selfie.png');
formData.append('prompt', 'scary clown');
formData.append('seed', '123456');
formData.append('allow_nsfw', 'true');

// Combine headers
const config = {
    headers: {
        ...headers,
        ...formData.getHeaders() // Required to set the proper Content-Type for multipart/form-data
    },
    responseType: 'arraybuffer' // Necessary to handle binary data
};

axios.post(url, formData, config)
    .then(response => {
        if (response.status === 200) {
            fs.writeFileSync('output.png', response.data);
            console.log('File saved as output.png');
        } else {
            console.error(`Failed with status code ${response.status}`);
        }
    })
    .catch(error => {
        console.error('There was a problem with the request:', error);
    });

```
{% endtab %}
{% endtabs %}

## Chat API Costs

***

Each API call costs 1 credit. Read more at [api-pricing.md](api-pricing.md "mention").
