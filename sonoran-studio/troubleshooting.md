---
description: Solve common Sonoran Studio overlay, connection, and companion problems.
icon: screwdriver-wrench
---

# Troubleshooting

## The overlay looks square, stretched, or cropped

Use the exact Studio canvas width and height in the browser source. Reset the source transform and fit it to the scene again.

## A temporary widget is missing

Radio transmission, panic takeover, and dispatch notification appear only while matching live data is present or while **TEST** is active. Confirm the widget is enabled and run its test.

## Live CAD or Radio data is not appearing

* Confirm you signed in with the correct Sonoran account.
* Keep the browser source active and connected.
* In OBS, leave **Shutdown source when not visible** off.
* Verify the community and product session granting Studio context is active.
* Replace and re-copy the overlay URL if the existing source was revoked.

## A premium layout is not broadcasting

Only the fallback layout broadcasts without premium access. Restore premium access or switch the streaming scene back to the fallback layout.

## The desktop companion says premium is unavailable

Confirm the companion is signed in and that either the personal Studio subscription or eligible Sonoran One community context is active.

## Smart lights do not respond

* Verify the companion is running.
* Confirm the displayed FiveM endpoint matches your integration.
* Test the scene directly in the companion.
* Check local-network access to the bridge or bulb.
* If LAN access is enabled, verify the caller uses the generated private token.

## Streamer.bot does not connect

Verify Streamer.bot's WebSocket server is enabled, normally on `127.0.0.1:8080`. Confirm its port, endpoint, and optional password in the companion, then select **Save & connect**.

## Still stuck?

Contact [Sonoran Support](https://support.sonoransoftware.com/) and include the streaming app, canvas size, affected widget, and whether the issue also appears during a Studio test.
