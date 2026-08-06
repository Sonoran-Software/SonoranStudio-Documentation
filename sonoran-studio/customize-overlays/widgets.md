---
description: Enable, position, resize, style, and test Sonoran Studio widgets.
icon: grid-2
---

# Widgets

![Sonoran Studio widget controls, canvas, and styling editor](https://files.gitbook.com/v0/b/gitbook-x-prod.appspot.com/o/spaces%2FSNDrCcXxwsnYIi72Ym9Z%2Fuploads%2Fo32NGSHNkvUrcyZlTKve%2Fwidgets-editor-clean.png?alt=media\&token=a58aab05-4bc4-4379-84fa-17aa2f6ab992)

## Available widgets

| Widget                | Source        | Behavior                                            |
| --------------------- | ------------- | --------------------------------------------------- |
| Radio transmission    | Sonoran Radio | Temporary popup for the active speaker and waveform |
| Unit HUD              | Sonoran CAD   | Persistent unit, department, status, and location   |
| Attached call         | Sonoran CAD   | Persistent details for the unit's attached call     |
| Panic takeover        | Sonoran CAD   | Temporary high-priority emergency animation         |
| Dispatch notification | Sonoran CAD   | Temporary important call or priority update         |

## Enable and test

Use the toggle beside a widget to include or remove it. **TEST** is available for temporary widgets so you can see their layout and animation without live traffic.

## Position and resize

Drag a widget on the canvas to move it. Drag its red corner to resize. For exact placement, select the widget and edit its **X**, **Y**, **W**, and **H** values. Use **Reset positions** to return the active widget to its default geometry.

## Style the active widget

The widget editor includes:

* Accent, background, and text colors
* Independent opacity controls
* Solid, fade-right, fade-left, soft-sides, and center-glow backgrounds
* Left, center, right, and stretch alignment
* Enter and exit animations
* Visible duration for temporary popups
* Reduced motion
* Text size

## Content and labels

Edit supported labels directly in the widget preview. Reorder content rows below the preview and hide rows you do not want on stream.

{% hint style="info" %}
Temporary widgets only occupy the canvas while matching live data is present or a test is running.
{% endhint %}
