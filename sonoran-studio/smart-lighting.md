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



## Integrated Games:

### FiveM

Configuring Smart Lighting for FiveM is easy!

Ensure your FiveM community is using the latest version of the Sonoran CAD FiveM resource. Once in-game, your smart lighting events will be automatically synced to the desktop app.

### ER:LC

Smart lighting for ER"LC works by reading the lighting and siren controller on your in-game screen. Sonoran CAD and Radio are not required for this feature at all.
