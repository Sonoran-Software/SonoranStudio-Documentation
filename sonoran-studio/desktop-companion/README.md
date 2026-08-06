---
description: Install and use the optional Sonoran Studio desktop companion.
icon: desktop
---

# Desktop companion

The optional desktop companion adds local integrations to the hosted Studio. Normal browser-source overlays do not require it.

Use the companion for:

* Philips Hue, Wyze Color, Govee Wi-Fi, and supported Govee Bluetooth lighting
* Existing Sonoran CAD lighting configuration import
* Streamer.bot action mappings
* A local FiveM lighting endpoint

{% hint style="info" %}
Smart lighting and Streamer.bot require premium access through Sonoran Studio or an eligible Sonoran One community.
{% endhint %}

## Download

Choose the installer for your operating system. These links always download the latest stable Sonoran Studio companion release.

<table data-view="cards"><thead><tr><th></th><th></th><th></th><th data-hidden data-card-target data-type="content-ref"></th></tr></thead><tbody><tr><td><h3><i class="fa-windows">:windows:</i></h3></td><td><strong>Windows</strong></td><td>Download the Windows installer (.exe).</td><td><a href="https://github.com/Sonoran-Software/Sonoran-Studio-Releases/releases/latest/download/Sonoran-Studio-Windows.exe">https://github.com/Sonoran-Software/Sonoran-Studio-Releases/releases/latest/download/Sonoran-Studio-Windows.exe</a></td></tr><tr><td><h3><i class="fa-apple">:apple:</i></h3></td><td><strong>macOS</strong></td><td>Download the macOS / OS X installer (.dmg).</td><td><a href="https://github.com/Sonoran-Software/Sonoran-Studio-Releases/releases/latest/download/Sonoran-Studio-macOS.dmg">https://github.com/Sonoran-Software/Sonoran-Studio-Releases/releases/latest/download/Sonoran-Studio-macOS.dmg</a></td></tr></tbody></table>

## Install

Run the downloaded installer, open Sonoran Studio, and sign in through the hosted Studio window. Production builds check for updates automatically and install them when the companion exits.

<table data-view="cards"><thead><tr><th></th><th></th><th></th><th data-hidden data-card-target data-type="content-ref"></th></tr></thead><tbody><tr><td><h3><i class="fa-lightbulb">:lightbulb:</i></h3></td><td><strong>Smart lighting</strong></td><td>Connect devices and build scenes for Sonoran states.</td><td></td></tr><tr><td><h3><i class="fa-bolt">:bolt:</i></h3></td><td><strong>Streamer.bot</strong></td><td>Map Sonoran events to existing automations.</td><td></td></tr></tbody></table>

## Security

Credentials are encrypted by the operating system and remain on that computer. The local lighting server binds to loopback by default. If LAN access is enabled, remote requests also require the companion's private token.
