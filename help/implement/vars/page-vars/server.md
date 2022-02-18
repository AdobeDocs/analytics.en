---
title: server
description: Populate the 'Servers' dimension.
feature: Variables
exl-id: 7904c3c2-9a91-497e-89d0-9eed9ae7a902
---
# server

The `server` variable typically stores the hostname of your site. It is commonly used in report suites that contain data from multiple domains. It is functionally identical to a prop.

## Server using tags in Adobe Experience Platform

You can set server either while configuring the Analytics extension (global variables) or under rules.

1. Log in to the [Data Collection UI](https://experience.adobe.com/data-collection) using your AdobeID credentials.
2. Click the desired property.
3. Go to the [!UICONTROL Rules] tab, then click the desired rule (or create a rule).
4. Under [!UICONTROL Actions], click an existing [!UICONTROL Adobe Analytics - Set Variables] action or click the '+' icon.
5. Set the [!UICONTROL Extension] dropdown to Adobe Analytics, and the [!UICONTROL Action Type] to [!UICONTROL Set Variables].
6. Locate the [!UICONTROL Server] section.

You can set server to any string value or data element.

## s.server in AppMeasurement and custom code editor

The `s.server` variable is a string that typically contains the hostname of your site. It has a maximum value of 100 bytes; longer values are truncated.

```js
// Set the server variable to a static string
s.server = "Example server";

// Automatically set the server variable to the site's hostname
s.server = window.location.hostname;
```
