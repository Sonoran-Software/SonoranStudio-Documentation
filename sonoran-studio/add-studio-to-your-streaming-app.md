---
description: >-
  Add a Sonoran Studio browser source to OBS, TikTok LIVE Studio, or Streamlabs
  Desktop.
icon: display
---

# Add Studio to your streaming app

Select **Setup guide** in Sonoran Studio to see the private URL and exact source size for the active layout.

![Sonoran Studio streaming setup guide](https://files.gitbook.com/v0/b/gitbook-x-prod.appspot.com/o/spaces%2FSNDrCcXxwsnYIi72Ym9Z%2Fuploads%2FWHgiBFycHCMAlW0X2NrX%2Fstreaming-setup-guide.webp?alt=media\&token=292432bb-df7b-446a-80ca-83a2e9ade920)

{% tabs %}
{% tab title="OBS Studio" %}
1. Open the scene that contains your game and select **+** in the Sources dock.
2. Choose **Browser**, select **Create new**, name it **Sonoran Studio**, and select **OK**.
3. Turn **Local file** off and paste your private Sonoran overlay URL into **URL**.
4. Enter the exact **Width** and **Height** shown in Studio.
5. Leave **Shutdown source when not visible** off so CAD and Radio events stay connected. Keep the transparent custom CSS OBS supplies.
6. Keep Sonoran Studio above your game capture in the Sources list. If necessary, use **Transform → Reset Transform**, then **Fit to Screen**.
7. Trigger a Studio **TEST** before going live.
{% endtab %}

{% tab title="TikTok LIVE Studio" %}
1. Open the landscape or portrait scene you plan to broadcast and select **Add source**.
2. Choose **Link**. Some versions call this a webpage or URL source.
3. Paste your private HTTPS overlay URL and name the source **Sonoran Studio**.
4. Set the source width and height to the exact Studio values when those fields are available. Otherwise, resize it to fill the complete scene.
5. Move it above your game, screen, or camera capture.
6. Check the mobile preview, then trigger a Studio **TEST**.
{% endtab %}

{% tab title="Streamlabs Desktop" %}
1. Open your gameplay scene, go to **Sources**, and select **+**.
2. Choose **Browser Source**, name it **Sonoran Studio**, and select **Add Source**.
3. Paste your private overlay URL.
4. Set **Width** and **Height** to the exact Studio values. You can normally leave FPS at 30.
5. Resize the source to fill the canvas and keep it above your game capture.
6. Trigger each Studio **TEST** before going live.
{% endtab %}
{% endtabs %}

{% hint style="danger" %}
Never show or share the complete overlay URL. If it is exposed, select **Replace URL** in Studio and update the browser source in every scene that used the old URL.
{% endhint %}

## Fix a square or cropped overlay

Verify the source width and height, reset its transform, and fit it to the scene again. For portrait broadcasts, confirm both Studio and the streaming app use the vertical dimensions.
