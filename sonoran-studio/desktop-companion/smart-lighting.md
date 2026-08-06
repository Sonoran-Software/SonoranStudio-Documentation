---
description: Connect smart lights and map Sonoran states to local lighting scenes.
icon: lightbulb
---

# Smart lighting

The desktop companion can control Philips Hue, Wyze Color, Govee Wi-Fi, and supported Govee Bluetooth bulbs from live Sonoran states.

{% stepper %}
{% step %}
### Import an existing CAD setup, if needed

Close the Sonoran CAD desktop application, then use the one-time importer. Studio reads the existing `twitchConfig1` lighting scenes and supported local pairing details.
{% endstep %}

{% step %}
### Connect devices

Choose **Philips Hue**, **Govee Wi-Fi**, **Wyze Color**, or **Govee Bluetooth**.

* For Hue, enter the bridge IP if needed and leave the username blank to start bridge linking.
* For Govee Wi-Fi, enter the Govee API key.
* Wyze and Govee Bluetooth devices are imported from CAD so existing local pairing details remain intact.

Select **Connect & find devices** where available.
{% endstep %}

{% step %}
### Configure scenes

Assign bulbs and a color/brightness sequence to each state. Test the scene before relying on it in game.
{% endstep %}

{% step %}
### Connect FiveM

FiveM sends JSON such as `{"state":"panic"}` to the local endpoint shown in the companion, normally `http://127.0.0.1:9990/lighting`.
{% endstep %}
{% endstepper %}

## Supported states

Restore, Emergency Lights, Panic, Unavailable, Available, Busy, En Route, On Scene, Left Signal, Right Signal, and Hazard.

## LAN access

The endpoint binds to the current computer by default. Enable LAN access only when another trusted device must send lighting states. Remote LAN calls require the generated private token.
