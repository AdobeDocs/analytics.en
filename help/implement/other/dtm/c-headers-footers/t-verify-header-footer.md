---
description: Verify that your Dynamic Tag Management library is loading properly on your site.
keywords: Analytics Implementation;implementation method;dynamic tag management;dtm;code;page code;header code;footer code;embed code;verify code;verify header code;verify footer code;embed tab;embed
title: Verify header and footer code
topic-fix: Developer and implementation
uuid: d395a417-0c61-41a6-a124-d2f400f4626f
exl-id: bed44ba7-8e0e-49e2-bedc-fb1ba66e5b18
---
# Verify header and footer code

Verify that your Dynamic Tag Management library is loading properly on your site.

1. Open your site in your browser.
1. Open the [!UICONTROL Developer Console] by right-clicking and choosing **[!UICONTROL Inspect Element]** > **[!UICONTROL Console]**.
1. Press **[!UICONTROL Enter]**.

   If the code was properly installed, you will see *`true`* display in the console.

   If the code was not properly installed, you will see the reference error:

   `_satellite is not defined`

   If you receive this error, ensure that:

* You have included the full header code on every page of the site in the [!DNL HEAD] section, as close to the `<head>` tag as possible.
* You do not have unexpected characters appearing in the code snippet, potentially as a result of copying and pasting from a formatted document.
