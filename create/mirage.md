---
description: Also known as "illusion diffusion".
icon: island-tropical
---

# Mirage

This pipeline takes an image and a text description as input and then generates the image as an illusion.

Example, in response to an image: `/mirage liminal space illusion`

## Parameters

***

You can also add Parameters at the beginning of the prompt. Multiple parameters per prompt is supported. Example: `/mirage -raw liminal (space) illusion`

<details>

<summary>Keyword Strength</summary>

Adjust keyword strength is to use `()` and `[]`. `(keyword)` increases the strength of the keyword by a factor of 1.1 and is the same as `(keyword:1.1)`. `[keyword]` decrease the strength by a factor of 0.9 and is the same as `(keyword:0.9)`.

You can use multiple of them, just like in algebra. The effect is multiplicative.

* (keyword) is equivalent to (keyword: 1.1)
* ((keyword)) is equivalent to (keyword: 1.21)
* (((keyword))) is equivalent to (keyword: 1.33)

Similarly, the effects of using multiple `[]` are:

* \[keyword] is equivalent to (keyword: 0.9)
* \[\[keyword]] is equivalent to (keyword: 0.81)
* \[\[\[keyword]]] is equivalent to (keyword: 0.73)

Example: `/mirage (((Phil))) dressed as a tiny vampire, standing under a full moon, surrounded by bats and glowing pumpkins, in a foggy graveyard ((distorted perspective, unique perspective, side profile, viewed from above, (ultra-wide angle lens), vanishing point))`

</details>

<details>

<summary>Override/Enable Prompt Enhancer</summary>

Want to manually bypass [prompt-enhancer.md](prompt-enhancer.md "mention") for your short prompts? If your prompt is 350 characters or less and you want to use it as is, add the parameter `-raw`.

To activate Prompt Enhancer for long prompts, add the parameter `-p`.

</details>

<details>

<summary>Temperature</summary>

Temperature is useful when remixing or refining an image based on your prompt.

Use the `-t` flag to manually control temperature, which determines how much the output image diverges from the original prompt.

* **Higher values** produce **stronger edits** and greater visual deviation.
* **Lower values** retain **closer resemblance** to the original concept.
* Recommended range: `30–70`

If no `-t` value is set, Prompt Enhancer will automatically assign a temperature for you based on prompt structure. You can iterate and tweak from there.

Example:

`/mirage -raw -t 61 Milady, a 2D neochibi girl with striking black skin and intense determination, stands shirtless in a dark room illuminated by a subtle teal radiance. Positioned off-center on the left third, viewed from a low-angle Dutch tilt. Her wolf fur hood billows dramatically, fur strands catching in the faint glow. Background features retro-futuristic lo-fi textures: flickering CRT scanlines, pixelated static, and dithered gradients.`

</details>

## Examples

***

<figure><img src="../.gitbook/assets/image (83).png" alt=""><figcaption><p><code>/mirage liminal space illusion underground oasis with arches and plants above the water in a dimly lit space</code></p></figcaption></figure>

<figure><img src="../.gitbook/assets/image (47).png" alt=""><figcaption><p><code>/mirage green neon glowing text, retrowave landscape, high quality digital render, ray tracing, path tracing, reflections</code></p></figcaption></figure>

<figure><img src="../.gitbook/assets/Frame 12.png" alt=""><figcaption><p><code>/mirage solitary moon, vibrant flowers, lush forest, Milky Way across the night sky</code></p></figcaption></figure>

{% content-ref url="../developers/memelord-api.md" %}
[memelord-api.md](../developers/memelord-api.md)
{% endcontent-ref %}
