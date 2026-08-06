---
description: Trigger existing Streamer.bot actions from live Sonoran events.
icon: bolt
---

# Streamer.bot actions

The desktop companion connects outbound to Streamer.bot's local WebSocket server and maps Sonoran events to actions you already created.

## Before you begin

Enable Streamer.bot's WebSocket server. Its common local address is `127.0.0.1` on port `8080`.

## Connect

1. Open **Streamer.bot actions** in the companion.
2. Enter the host, port, endpoint, and optional WebSocket password.
3. Select **Save & connect**.
4. Once connected, Studio loads the available Streamer.bot actions.

## Map events

Choose an action for each Sonoran event, or leave it set to **Do nothing**. Use **Test** to send a sample event before going live.

Available event mappings include unit status changes, panic activation and clearing, call attachment changes, dispatch notifications, and radio transmission activity.

{% hint style="info" %}
The integration reuses the authenticated Studio event stream. It does not add CAD or Radio polling and connects only to the local Streamer.bot server.
{% endhint %}

## Troubleshoot

If the companion shows **Not connected**, verify the WebSocket server is enabled, the port and endpoint match, and the password is correct. Then select **Save & connect** again.
