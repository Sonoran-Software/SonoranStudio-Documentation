---
description: >-
  Integrate smart lighting for in-game emergency lights, turn signals, CAD/Radio
  events, and more!
icon: lightbulb
---

# Smart Lighting

{% hint style="info" %}
Smart Lighting requires the [Pro version of Sonoran Studio](pricing.md) and the Windows or macOS desktop app.
{% endhint %}

## What is Smart Lighting?

Sonoran Studio connects to supported RGB lights to toggle and change colors based on stream events. With the FiveM, LSPDFR, and ER:LC integrations, you can build custom patterns for emergency lights, hazards, turn signals, panic activity, and more.

## What Lights are Supported?

Studio only lists lights that expose the color and power controls required by the selected provider. A product having Wi-Fi, Bluetooth, Matter, Alexa, or Google Home support does **not** by itself guarantee compatibility.

{% hint style="warning" %}
Smart lights are third-party products. Their manufacturers may change or retire cloud and local APIs. Match the exact brand, family, and requirements below before purchasing.
{% endhint %}

{% hint style="info" %}
Amazon links on this page are affiliate links. As an Amazon Associate, Sonoran Software may earn from qualifying purchases.
{% endhint %}

<details>

<summary>Wyze Color</summary>

Wyze connects through the Wyze cloud and requires the four account values shown in Studio.

#### Setup

1. Add each color bulb or lightstrip in the Wyze app and confirm it is online.
2. Open the [Wyze developer console](https://developer-api-console.wyze.com/#/apikey/view), sign in with the same account, and create an API key.
3. In Studio, select **Wyze Color** and enter the Wyze email, password, key ID, and API key.
4. Select **Connect Wyze & find lights**. The credentials are encrypted on this computer; use **Re-login** if they change.

Supported color bulbs:

* [Wyze Bulb Color A19, 2-pack](https://amzn.to/4wNzeyc)
* [Wyze Bulb Color BR30, 2-pack](https://amzn.to/4z2rk5k)

Wyze Light Strip and Light Strip Pro are detected by the current integration and receive a single solid RGB color across the strip. Segment and effect control are not supported. Because Wyze does not publish device-control rate limits for this endpoint, use frame delays of **1,000 ms or longer** for the most reliable sequences.

Official product references: [Bulb Color A19 and BR30](https://support.wyze.com/hc/en-us/articles/360056870611-Wyze-Bulb-Color-Features) and [Light Strip / Light Strip Pro](https://support.wyze.com/hc/en-us/articles/4403317129627-About-Wyze-Light-Strip-and-Wyze-Light-Strip-Pro).

</details>

<details>

<summary>Philips Hue</summary>

Philips Hue uses the local Hue Bridge API. A Hue Bridge is required, including for products that can also connect over Bluetooth. Studio supports Hue lights that report full color controls; buy the **White and color ambiance** version, not White or White ambiance.

#### Setup

1. Add the Hue Bridge and color lights in the Hue app and confirm every light works.
2. Keep the Bridge and Studio desktop app on the same local network.
3. Press the round link button on top of the Hue Bridge.
4. In Studio, select **Philips Hue**, leave the optional fields blank, and select **Connect Hue Bridge**. Studio discovers the Bridge and creates a local API username. Advanced users may enter an existing Bridge IP and API username instead.

Compatible Hue families include color A19/BR30 bulbs, Lightstrip Plus and Gradient lightstrips, Play light bars, Go, Iris, Bloom, and Signe lights when paired to a Hue Bridge. Studio sets one color for the whole light and does not address gradient segments or entertainment areas.

* [Starter kit with Hue Bridge and color bulbs](https://amzn.to/45JQcBo)
* [Single color bulb](https://amzn.to/4xrsG8h)
* [Color bulb 4-pack](https://amzn.to/4xkzi8f)
* [Hue Lightstrip Plus base kit](https://amzn.to/4wOFeXx)

The Hue API recommends approximately **10 light commands per second**. Studio now queues Bridge writes at 100 ms intervals; use frame delays of at least **100 ms**, and longer delays for large groups. See the official [Hue rate-limit guidance](https://developers.meethue.com/support/) and [Hue Bridge overview](https://www.philips-hue.com/en-us/explore-hue/faq/controls/what-is-the-hue-bridge).

</details>

<details>

<summary>Govee Wi-Fi</summary>

Govee connects through the official cloud API and requires a [Govee API key](https://developer.govee.com/docs/getting-started). Studio only displays devices for which Govee reports both `powerSwitch` and `colorRgb`. This capability check is more reliable than assuming every product in a family supports the API.

#### Setup

1. Add every light in the Govee Home app and confirm it is online over Wi-Fi. Bluetooth-only products cannot use this connection.
2. Sign in to the [Govee developer portal](https://developer.govee.com/) with the account that owns the lights and request an API key.
3. In Studio, select **Govee Wi-Fi**, paste the API key, and select **Connect Govee & find lights**.
4. Studio lists only devices whose API capabilities include both RGB color and power control.

API-verified examples from Govee's [official supported-model list](https://developer.govee.com/docs/support-product-model):

* H6008 A19 bulb — [4-pack on Amazon](https://amzn.to/4fMMsVK)
* H605C Envisual TV Backlight T2 — [75–85 inch kit on Amazon](https://amzn.to/4bxpKyy)
* H607C Floor Lamp 2
* H6062 Glide RGBIC 3D Wall Light
* H7055 Outdoor Pathway Lights

Many other Govee Wi-Fi products may appear automatically when the API reports both required capabilities. Bluetooth-only products are not supported. Studio applies one RGB color to the whole device; RGBIC segments, DreamView, scenes, and music effects are not controlled.

Govee permits **2 control requests per second per device** and **12 per second per account**. Turning a light on with a new color requires two requests. Studio queues requests at 500 ms per device and 84 ms per account; use frame delays of **1,000 ms or longer** for cloud reliability. See Govee's official [device-control API](https://developer.govee.com/reference/control-you-devices).

</details>

<details>

<summary>Nanoleaf</summary>

Nanoleaf uses its local OpenAPI on port `16021`; no cloud account or hub is required. Enter the light's IP address or local hostname in Studio. In the Nanoleaf app, choose **Connect to API**, or hold the controller power button for 5–7 seconds, then select **Pair & find Nanoleaf** within 30 seconds.

#### Setup

1. Put the Nanoleaf device and Studio desktop app on the same local network, then find the device IP in the Nanoleaf app or your router.
2. Open the pairing window by choosing **Connect to API** in the Nanoleaf app or holding the controller power button for 5–7 seconds.
3. In Studio, select **Nanoleaf**, enter the IP address or local hostname, and leave the token blank for first-time pairing.
4. Within 30 seconds, select **Pair & find Nanoleaf**. Studio saves the returned local token; an existing token may be pasted when reconnecting.

Studio validates that the device reports RGB hue and saturation controls before adding it. Supported RGB families documented by Nanoleaf include:

* Shapes, Canvas, Lines, Light Panels, and Skylight
* Holiday String Lights (NL71K1/NL71K2)
* Indoor HD Lightstrip (NL72K1) and Indoor Lightstrip (NL72K3)
* Floor Lamp (NL72K4) and Rope Lights (NL72K6)
* Outdoor String Lights (NL73K1) and Permanent Outdoor Lights (NL73K3)
* Wi-Fi A19 bulb (NL75K1)

Elements panels are not listed because they do not expose the RGB controls Studio requires. Studio controls one solid color for the entire device; panel layouts, per-panel colors, and effects are not controlled.

Nanoleaf's official OpenAPI recommends no more than **10 updates per second**. Studio enforces a 100 ms interval per device. See the official [OpenAPI overview](https://nanoleaf.atlassian.net/wiki/spaces/nlapid/overview), [Light Panels OpenAPI](https://nanoleaf.atlassian.net/wiki/spaces/NOAD1/pages/2789310530), and [Matter Wi-Fi OpenAPI model list](https://nanoleaf.atlassian.net/wiki/spaces/nlapid/pages/2296381472/Nanoleaf%2BMatter%2BWiFi%2BEssentials%2BOpen%2BAPI%2BDocumentation).

{% hint style="info" %}
No exact, active Amazon listing could be verified for the official RGB OpenAPI models during the latest documentation review. We will add an affiliate link only after the listing exposes a matching Nanoleaf model number; do not purchase a similarly named marketplace light on compatibility alone.
{% endhint %}

</details>

<details>

<summary>LIFX</summary>

LIFX connects directly over the official local LAN protocol. No LIFX cloud token, account sign-in, or hub is required. Keep the Studio desktop app and the lights on the same local network, then select **Scan local network for LIFX**.

#### Setup

1. Add the color lights in the LIFX app, update their firmware, and confirm they can display RGB colors.
2. Keep the lights and Studio desktop app on the same local network. Guest Wi-Fi or client isolation must be disabled between them.
3. Allow local UDP port `56700` through the computer firewall if discovery traffic is restricted.
4. In Studio, select **LIFX** and then **Scan local network for LIFX**. No account, hub, address, or token is required.

Studio queries the vendor and product ID of every responding device and checks it against LIFX's official [machine-readable product registry](https://github.com/LIFX/products). A device is listed only when that exact product declares `color: true`. This covers the RGB versions of LIFX Color A19/A21/BR30/GU10 bulbs, Mini Color, Clean, Downlight, Z/Lightstrip, Beam, Tile, Candle Color, Neon, String, Ceiling, Spot, Path, PAR38, Tube, Luna, Mirror, and RGB outdoor families in the current registry.

* [LIFX Color A19 1100-lumen, 2-pack](https://amzn.to/4z6fE1t)

LIFX White, White-to-Warm, Day & Dusk, Filament, and Switch products are excluded because they do not declare RGB color capability. Unknown product IDs also remain hidden until their capabilities can be verified. Studio applies one solid color to the entire light; it does not address individual Beam, Tile, Candle, String, or lightstrip zones.

LIFX discovery and control use UDP port `56700`. Studio requests an acknowledgement for every command and retries a missing acknowledgement once. LIFX warns clients against excessive LAN message rates but does not publish a numeric request ceiling, so Studio serializes commands per light. Start with frame delays of **100 ms or longer** and increase the delay if Wi-Fi is congested. See the official [LAN discovery guide](https://lan.developer.lifx.com/docs/communicating-with-device), [SetColor/SetPower messages](https://lan.developer.lifx.com/docs/changing-a-device), and [packet header specification](https://lan.developer.lifx.com/docs/packet-contents).

</details>

<details>

<summary>WLED</summary>

WLED connects directly to each controller's local JSON API. Studio requires WLED `0.13` or newer so it can verify that at least one segment reports RGB capability. Enter the controller's IP address or local hostname; separate multiple controllers with commas.

#### Setup

1. Install WLED `0.13` or newer, configure the controller and LED output, and verify RGB colors from the WLED web interface.
2. Open the WLED Info screen, WLED app, or router and copy the controller's IP address or `.local` hostname.
3. In Studio, select **WLED** and enter the address. Separate multiple controllers with commas.
4. Select **Connect WLED controller**. Studio verifies RGB capability and represents each controller as one light controlling all configured segments.

Studio treats each WLED controller as one light. A color update switches every configured segment to the Solid effect and applies the same RGB color and full brightness across those segments. Existing per-segment colors and effects are intentionally replaced while a Studio scene is active.

* [WLED pre-installed Wi-Fi controller for 5V WS2811/WS2812B LEDs](https://amzn.to/4cuMU8X)

The linked controller appears on WLED's official [compatible-controller list](https://kno.wled.ge/basics/compatible-controllers/) under Domestic Automation. WLED supports many other pre-flashed and DIY controllers, but the controller, power supply, strip voltage, data signaling, fusing, and wiring must all match. Follow WLED's hardware guidance rather than treating every product whose listing says “WLED” as equivalent.

The WLED API explicitly advises clients not to make requests in parallel. Studio puts all WLED discovery and control requests through one sequential queue and uses the one-call `tt: 0` transition for immediate changes. Use frame delays of **100 ms or longer** for reliable animations, especially with several controllers. See the official [WLED JSON API](https://kno.wled.ge/interfaces/json-api/) and [getting-started guide](https://kno.wled.ge/basics/getting-started/).

</details>

## Provider Timing Reference

| Provider | Connection | Studio guard | Recommended frame delay |
| --- | --- | --- | --- |
| Wyze | Cloud | One combined action per light | 1,000 ms or longer |
| Philips Hue | Local Hue Bridge | 100 ms between Bridge writes | 100 ms or longer; increase for large groups |
| Govee | Cloud | 500 ms/device and 84 ms/account | 1,000 ms or longer |
| Nanoleaf | Local network | 100 ms/device | 100 ms or longer |
| LIFX | Local UDP | Acknowledged commands, one queue per light | 100 ms or longer |
| WLED | Local HTTP | One global sequential request queue | 100 ms or longer |

## Creating Light Sequences

Light sequences tell Studio which lights to use, what color each light should display, and how long each frame should remain active. Each game or CAD event has its own saved sequence.

### 1. Choose a game source

Open **Smart Lighting** in the Sonoran Studio desktop app. Under **Choose your game**, select **FiveM**, **LSPDFR**, or **ER:LC**. The scene editor only shows events supported by the selected game.

### 2. Connect your lights

Under **Connect devices**, choose your provider and follow the connection steps. After Studio discovers the lights, they are available in every scene and frame.

### 3. Select the event

Under **Build event scenes**, use **Scene event** to select the event you want to configure, such as **Panic**, **Emergency lights**, **Left signal**, or **Hazards**. Every event saves a separate sequence.

### 4. Build the frames

The first frame is created for you. Select the frame, check the lights that should participate, choose a color for each selected light, and set **Delay to next frame** in milliseconds.

Select **Add frame** to copy the selected frame, then change its lights, colors, or delay. Drag frame cards to reorder them. A sequence can contain up to 40 frames, and each frame delay can be between 50 and 60,000 milliseconds.

<figure><img src="../.gitbook/assets/smart-lighting-sequence-overview.png" alt="The Sonoran Studio lighting sequence editor showing three frames for a panic event"><figcaption>A three-frame panic sequence using different colors and lights in each frame.</figcaption></figure>

Each frame can control a different set of lights. A light that is not selected in a frame is left unchanged during that frame.

<figure><img src="../.gitbook/assets/smart-lighting-frame-editor.png" alt="The Sonoran Studio frame editor with light selection, colors, and delay controls"><figcaption>Select the lights and colors for the active frame, then set the time until the next frame.</figcaption></figure>

### 5. Test and save

Changes save automatically on this computer. Select **Test once** to play Frame 1 through the final frame one time before going live.

When the corresponding live event occurs, Studio loops the saved sequence until another lighting event takes over. Single-frame scenes remain on their configured colors. Testing, direct light control, or another sequence cancels the sequence currently playing.

## Integrated Games

### FiveM

Ensure your FiveM community is using the latest Sonoran CAD FiveM resource. Once in game, smart-lighting events automatically sync to the desktop app on local port `9990`.

FiveM scenes include emergency lights, turn signals, hazards, CAD unit statuses, and panic activity. Keep the Sonoran CAD resource running and the Studio desktop app open.

### LSPDFR

The Sonoran Studio LSPDFR plugin synchronizes emergency lights, left and right indicators, and hazards through RAGE Plugin Hook. It only connects to the Studio desktop app on your computer.

{% hint style="info" %}
You need LSPDFR, RAGE Plugin Hook, the Sonoran Studio Windows app, and Studio Pro or Sonoran One.
{% endhint %}

#### Install the plugin

1. [Download the LSPDFR lighting plugin](https://github.com/Sonoran-Software/Sonoran-Studio-Releases/releases/download/lspdfr-latest/Sonoran-Studio-LSPDFR.zip).
2. Close GTA V and RAGE Plugin Hook.
3. Extract the ZIP into your **Grand Theft Auto V** folder. Confirm this file exists: `Grand Theft Auto V\Plugins\SonoranStudio.LSPDFR.dll`.
4. Open RAGE Plugin Hook settings and enable **Load all plugins on startup**.
5. Open the Sonoran Studio Windows app, go to **Lighting**, and select **LSPDFR**.
6. Start GTA V through RAGE Plugin Hook and launch LSPDFR. Keep Sonoran Studio open while playing.

The plugin sends changes only to `127.0.0.1:9990`; it does not connect to a game server or expose a public port. If it does not load, open the RAGE Plugin Hook console with **F4** and run `LoadPlugin "SonoranStudio.LSPDFR.dll"`, then check `RagePluginHook.log` for a Sonoran Studio message.

### ER:LC

Smart lighting for ER:LC reads the lighting and siren controller in the Roblox window. Sonoran CAD and Radio are not required.

Leave the ER:LC ELS controller visible while playing. On macOS, allow Sonoran Studio under **Screen & System Audio Recording** when prompted. Detection remains on your computer; screenshots are never saved or uploaded.
