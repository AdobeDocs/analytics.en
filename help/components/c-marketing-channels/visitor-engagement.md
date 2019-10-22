---
description: Learn how to specify visitor engagement expiration in Marketing Channels.
seo-description: Learn how to specify visitor engagement expiration in Marketing Channels.
seo-title: Visitor engagement expiration
solution: Analytics
subtopic: Marketing channels
title: Visitor engagement expiration
topic: Reports and analytics
uuid: 47f1ccaf-3ce7-494d-b456-956a3a3c6c9a
---

# Visitor engagement expiration

Learn how to specify visitor engagement expiration in Marketing Channels.

Visitor engagement is how much time you want to allow for the visitor's previous activity on your site to be attributed to the first touch channel.

For example, visitors often click through a Paid Search campaign and add products to a cart, but they end the session before the conversion event. If the visitor returns later to make a purchase, you can specify whether their previous and current activity counts as one engagement. The default expiration setting is 30 days. 

| Field  | Definition  |
|--- |--- |
|Days of Inactivity|The number of days that must pass before a visitor's first-touch engagement expires. The default value is 30.|
|Never|The visitor's engagement period does not expire.|
|Channel Reset|Expires all visitor engagement periods.  If you have need to reset all marketing channel data you can expire all visitor engagement periods. You may need to reset data if your processing rules were previously configured incorrectly. All first and last touch channel values will immediately expire and be reset when visitors return.|

## Specify visitor engagement expiration {#specify-visitor-expire}

Specify the visitor engagement expiration.

1. Click **[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Report Suites]**.
1. In the [!UICONTROL Report Suite Manager], click **[!UICONTROL Edit Settings]** > **[!UICONTROL Marketing Channels]** > **[!UICONTROL Marketing Channel Expiration]**.

   ![](assets/mchannel_expiration.png)

1. Configure the visitor engagement expiration fields.
1. Click **[!UICONTROL Save.]**
