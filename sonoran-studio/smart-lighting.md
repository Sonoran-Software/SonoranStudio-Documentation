---
description: >-
  Integrate smart lighting for in-game emergency lights, turn signals, CAD/Radio
  events, and more!
icon: lightbulb
---

# Smart Lighting

{% hint style="info" %}
Smart Lighting requires the [Pro version of Sonoran Studio](pricing.md) and the Windows or OSX desktop app.
{% endhint %}

## What is Smart Lighting?

Sonoran Studio connects to smart lightbulbs to toggle and change colors based on stream events. With additional integrations for FiveM and ER:LC you can even create custom lighting patterns for emergency lights, hazards, turn signals, and more!

## What Bulbs are Supported?

{% hint style="info" %}
As smart bulbs are from third-party providers, we cannot guarantee permanent support for every vendor. We are limited to their ongoing availability of cloud and localized APIs. Providers may change this access at any time.
{% endhint %}

<details>

<summary>Wyze (Recommended)</summary>

We strongly recommend the Wyze Bulb color for the best integration. Not only are these some of the cheapest available, but local integrations allow for faster updates and less rate limits.

* [4-Pack](https://amzn.to/4g0gDYw)
* [2-Pack](https://www.amazon.com/WYZE-4-PACK-MILLION-TUNABLE-CONTROL/dp/B097C3VLLL/ref=sr_1_1?crid=2I7KDAA2M0TI1\&dib=eyJ2IjoiMSJ9.mbF7sH6vDpzZIk_E9B1M_bTzQApc499H7_O1KkebqHhy1_lmFtpfH8ZANpohjgeacJdlvNaRuLEJnS-8M6j-Vrv35_26M8EaKktWqBL6c2uI1uFF5lF3-qDDXTGKLibi4LNIVIKBJFfjoYPcx-lKGPBbzKQKDom4XNxRifPLy7N0633_MW5eoxoOcMZS3i0iVTeSDWvaTGU4E_LbM1TSEQblV653RUNKx5iz2qQN3Po.8SqWrk6V95YjnLuNUzqwIbTU5O6LJReapZjKAqssFDU\&dib_tag=se\&keywords=wyze%2Bbulb%2Bcolor\&qid=1786061688\&sprefix=wize%2Bbulb%2Bcol%2Caps%2C278\&sr=8-1\&th=1)

</details>

<details>

<summary>Philips Hue</summary>

Philips Hue bulbs are popular, premium, but come with harsher rate limits. You may need to increase the delays between lighting frames to avoid the bulbs rate limiting your Studio configuration. Additionally, these require a local "Hub" to be purchased for the connection.

* [Starter Kit w/Required Hub and 4x Bulbs:](https://amzn.to/45JQcBo)
* [Single Bulb](https://amzn.to/4xrsG8h)
* [4-Pack](https://amzn.to/4xkzi8f)

</details>

<details>

<summary>Govee Wifi</summary>

Govee is a popular choice for smart lighting. Ensure you purchase the **Wi-Fi** enabled bulbs, not the local Bluetooth controlled bulbs, for proper API integration. Because these bulbs connect over a cloud API, rate limits will be the harshest. You may need to increase the delay between lighting frames in your sequences for the best results.

* [4-Pack](https://amzn.to/4wGbE6f)

</details>

## Creating Light Sequences

Light sequences tell Studio which bulbs to use, what color each bulb should display, and how long each frame should remain active. Each game or CAD event has its own saved sequence.

### 1. Choose a game source

Open **Smart Lighting** in the Sonoran Studio desktop app. Under **Choose your game**, select **FiveM** or **ER:LC**. The scene editor only shows events supported by the selected game.

### 2. Connect your lights

Under **Connect devices**, choose your provider and follow the connection steps. After Studio discovers the lights, they are available in every scene and frame.

### 3. Select the event

Under **Build event scenes**, use **Scene event** to select the event you want to configure, such as **Panic**, **Emergency lights**, **Left signal**, or **Hazards**. Every event saves a separate sequence.

### 4. Build the frames

The first frame is created for you. Select the frame, check the bulbs that should participate, choose a color for each selected bulb, and set **Delay to next frame** in milliseconds.

Select **Add frame** to copy the currently selected frame, then change its bulbs, colors, or delay. Drag frame cards to reorder them. A sequence can contain up to 40 frames, and each frame delay can be between 50 and 60,000 milliseconds.

<figure><img src="../.gitbook/assets/smart-lighting-sequence-overview.png" alt="The real Sonoran Studio lighting sequence editor showing three frames for a panic event"><figcaption>A three-frame panic sequence using different colors and bulbs in each frame.</figcaption></figure>

Each frame can control a different set of lights. A bulb that is not selected in a frame is left unchanged during that frame.

<figure><img src="../.gitbook/assets/smart-lighting-frame-editor.png" alt="The real Sonoran Studio frame editor with bulb selection, colors, and delay controls"><figcaption>Select the bulbs and colors for the active frame, then set the time until the next frame.</figcaption></figure>

### 5. Test and save

Changes save automatically on this computer. Select **Test once** to play Frame 1 through the final frame one time before going live.

When the corresponding live event occurs, Studio loops the saved sequence until another lighting event takes over. Single-frame scenes remain on their configured colors. Testing, direct bulb control, or another sequence cancels the sequence currently playing.

{% hint style="warning" %}
Cloud-connected bulbs may rate limit rapid color changes. If a sequence skips or delays colors, increase the frame delay. Philips Hue can also require longer delays for larger groups, while Wyze bulbs use a firmware-controlled fade that Studio cannot disable.
{% endhint %}


## Integrated Games:

### FiveM

Configuring Smart Lighting for FiveM is easy!

Ensure your FiveM community is using the latest version of the Sonoran CAD FiveM resource. Once in-game, your smart lighting events will be automatically synced to the desktop app.

FiveM scenes include emergency lights, turn signals, hazards, CAD unit statuses, and panic activity. Keep the Sonoran CAD resource running and the Studio desktop app open.

### ER:LC

Smart lighting for ER:LC works by reading the lighting and siren controller in the Roblox window. Sonoran CAD and Radio are not required for this feature.

Leave the ER:LC ELS controller visible while playing. On macOS, allow Sonoran Studio under **Screen & System Audio Recording** when prompted. Detection remains on your computer; screenshots are never saved or uploaded.
