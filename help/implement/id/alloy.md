---
title: Visitor identification using the Web SDK JavaScript library
description: Correctly identify visitors when implementing the Web SDK JavaScript library.
exl-id: e650d6b1-6e29-4a9c-98dd-8482f50968d1
---
# Visitor identification using the Web SDK JavaScript library

The Adobe Experience Platform Web SDK JavaScript library (`alloy.js`) offers a unified, modern approach to data collection for all Adobe Experience Cloud applications, including Adobe Analytics. While most customers typically implement the [Web SDK tag extension](web-sdk-extension.md), you can use the Web SDK JavaScript library on its own or within a third-party tag management system. See [Alloy](https://github.com/adobe/alloy) on GitHub to download the latest version of the library.

Identity data can be extended to support custom IDs and multiple namespaces using XDM's `identityMap`. Adobe recommends using the Adobe Experience Cloud ID Service as the primary identifier for Analytics, using other identity management options for advanced scenarios.

If your organization uses the Web SDK JavaScript library to send data to Adobe Analytics, minimal configuration is required for visitor identification. The Visitor ID Service is baked in natively to the library, only requiring that you set **[!UICONTROL Edge Domain]** in the `configure` command. If this field is set to the desired value, visitor identification works without any additional configuration.
