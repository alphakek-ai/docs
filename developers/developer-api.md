---
description: AI-as-a-Service for your tools and applications.
icon: webhook
---

# Developer API

{% hint style="info" %}
The Enterprise API is the main access point for [#aikek-memelord](../launch/universal-agents.md#aikek-memelord "mention") and [#aikek-wizard](../launch/universal-agents.md#aikek-wizard "mention") universal agents.
{% endhint %}

Alphakek API gives developers access to some of our B2C functionalities, [meme-generator.md](../create/meme-generator.md "mention") and [ai-playground.md](../research/ai-playground.md "mention"), via open, modular, and composable APIs. Designed for applications such as:

* Chatbots
* Image generation
* Crypto research
* Community engagement
* Trade alerts
* Drafting documents
* Answering questions about a knowledge base
* and much more

## Modules

***

<table data-view="cards"><thead><tr><th></th><th></th><th></th><th data-hidden data-card-target data-type="content-ref"></th><th data-hidden data-card-cover data-type="files"></th></tr></thead><tbody><tr><td><strong>Memelord API</strong></td><td>Integrate our <a data-mention href="../create/meme-generator.md">meme-generator.md</a> to generate images.</td><td></td><td><a href="memelord-api.md">memelord-api.md</a></td><td><a href="../.gitbook/assets/card_alpha_visuals.png">card_alpha_visuals.png</a></td></tr><tr><td><strong>Wizard API</strong></td><td>Integrate <a data-mention href="../research/ai-playground.md">ai-playground.md</a> into your product!</td><td></td><td><a href="wizard-api.md">wizard-api.md</a></td><td><a href="../.gitbook/assets/card_chat_api.png">card_chat_api.png</a></td></tr></tbody></table>

Further reading:

* For pricing, refer to the [api-pricing.md](api-pricing.md "mention").
* For code examples, refer to [api-usage-examples.md](api-usage-examples.md "mention") or our [Python SDK](https://github.com/alphakek-ai/sdk).

## Authentification

***

To start using the API, the user must first obtain the access token. After logging in with Metamask or WalletConnect on [alphakek.ai](https://www.alphakek.ai/), open the API Keys tab on the user profile page.&#x20;

Note that the newly created token will never be shown on the screen. Instead, it will be copied to the copy buffer immediately for security reasons.

<figure><img src="../.gitbook/assets/image (48).png" alt=""><figcaption><p>API Keys tab on the user profile page</p></figcaption></figure>

## Account Data

***

The `/account` endpoint allows users to see their current balances of:

* [API Credits](api-pricing.md)
* [$AIKEK tokens](../tokenomics.md)
* $AIKEK value in USD

This API endpoint is free to use.

{% openapi src="https://api.alphakek.ai/openapi.json" path="/account" method="get" expanded="false" fullWidth="false" %}
[https://api.alphakek.ai/openapi.json](https://api.alphakek.ai/openapi.json)
{% endopenapi %}

{% content-ref url="api-usage-examples.md" %}
[api-usage-examples.md](api-usage-examples.md)
{% endcontent-ref %}
