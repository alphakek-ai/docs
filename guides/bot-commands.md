---
description: The list of commands supported by our Telegram and Discord bots.
hidden: true
icon: rectangle-terminal
---

# Bot Commands

## Administrative

***

* **/show\_commands** - show all commands
* **/login** - log in to ALPHAKEK AI
* **/logout** - log out from ALPHAKEK AI
* **/account** - view your user tier and breakdown of $AIKEK holdings
* **/privacy** - show privacy policy
* **/kek** - get $AIKEK stats

## Research

***

* **/ask \[question]** - ask ALPHAKEK AI a question, uncensored mode is always on
* **/ask\_detailed \[question]** - ask AI a question and get a detailed report, takes 2-3 minutes
* **/ask\_biz \[question]** - ask AI a question, only use 4chan /biz/ data
* [**/t \[ticker\_or\_address\]**](../token-audit.md) - token audit, get token info
* [**/find\_buyers \[CA1 CA2...\]**](../wallet-finder.md#triangulator-1) - get common buyers of multiple tokens to triangulate wallet(s)
* [**/find\_num\_buys \[min\_count max\_count CA\]**](../wallet-finder.md#triangulator-2) - get all wallets that bought the token between min\_count and max\_count times
* [**/find\_buy\_amount CA amount \[amount\_max\] \[sol | usd | $ | token\]**](../wallet-finder.md#triangulator-3) - get wallets that bought the token for the specified amount
* **/visualize \[market topic]** - visualize market data for a given topic
* [**/summarize**](../chat-analysis.md) - get a summary of the chat
* **/tldr \[link]** - get a summary of a website or article
* [**/wordcloud**](https://x.com/alphakek_ai/status/1848108717923008524) - a visual tl;dr of your group chat
* **/random** - do a random thing :D

## Images

***

* **/image \[prompt]** - generate an image from a prompt (see [text-to-image.md](../create/text-to-image.md "mention") for more details)
* **/imagev \[prompt]** - generate a vertical image from a prompt
* **/imagew \[prompt]** - generate a wide image from a prompt
* **/imagesq \[prompt]** - generate a square image from a prompt
* **/effect \[attach image + optional prompt]** - universal AI filter
* **/retro \[attach image]** - gives the image a retro "PlayStation 1" effect, is the first of many /effect "presets"
* **/mirage \[attach image + optional prompt]** - illusion diffusion; transforms images into surreal, optical illusions
* **/meme \[prompt]** - generate a meme image

## Videos

***

* **/video \[prompt]** - generate a video from a prompt
* **/video \[attach image]** - generate a video from an image

{% content-ref url="../create/meme-generator.md" %}
[meme-generator.md](../create/meme-generator.md)
{% endcontent-ref %}
