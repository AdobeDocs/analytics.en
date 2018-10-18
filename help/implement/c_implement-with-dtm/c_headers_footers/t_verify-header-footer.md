---
description: Verify that your Dynamic Tag Management library is loading properly on your site.
keywords: Analytics Implementation;implementation method;dynamic tag management;dtm;code;page code;header code;footer code;embed code;verify code;verify header code;verify footer code;embed tab;embed
seo-description: Verify that your Dynamic Tag Management library is loading properly on your site.
seo-title: Verify header and footer code
solution: Analytics
title: Verify header and footer code
topic: Developer and implementation
uuid: 16cac035-7bee-4015-9e0d-65d4be2c8c29
index: y
internal: n
snippet: y
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

* You have included the full header code on every page of the site in the [!DNL HEAD] section, as close to the [!DNL <head>] tag as possible. 
* You do not have unexpected characters appearing in the code snippet, potentially as a result of copying and pasting from a formatted document.

