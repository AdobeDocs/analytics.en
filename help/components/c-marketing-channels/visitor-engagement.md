---
description: Learn how to specify visitor engagement expiration in Marketing Channels.
seo-description: Learn how to specify visitor engagement expiration in Marketing Channels.
seo-title: Visitor engagement expiration
solution: Analytics
subtopic: Marketing channels
title: Visitor engagement expiration
topic: Reports and analytics
uuid: 47f1ccaf-3ce7-494d-b456-956a3a3c6c9a
index: y
internal: n
snippet: y
---

# Visitor engagement expiration

Learn how to specify visitor engagement expiration in Marketing Channels.

## Visitor engagement expiration {#topic_32ADFDB12D3A4F35843A4545AC97C49F}

Learn how to specify visitor engagement expiration in Marketing Channels. 

Visitor engagement is how much time you want to allow for the visitor's previous activity on your site to be attributed to the first touch channel.

For example, visitors often click through a Paid Search campaign and add products to a cart, but they end the session before the conversion event. If the visitor returns later to make a purchase, you can specify whether their previous and current activity counts as one engagement. The default expiration setting is 30 days. 

<table id="table_C18A0F1C9E214EB585A29801BA2400F8"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Field </p> </th> 
   <th colname="col2" class="entry"> <p>Definition </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Days of Inactivity </p> </td> 
   <td colname="col2"> <p>The number of days that must pass before a visitor's first-touch engagement expires. The default value is 30. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Never </p> </td> 
   <td colname="col2"> <p>The visitor's engagement period does not expire. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Channel Reset </p> </td> 
   <td colname="col2"> <p>Expires all visitor engagement periods. </p> <p>If you have need to reset all marketing channel data you can expire all visitor engagement periods. You may need to reset data if your processing rules were previously configured incorrectly. All first and last touch channel values will immediately expire and be reset when visitors return. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Specify visitor engagement expiration {#task_A8B8B5A07C5A4882BB895252A018FDED}

Specify the visitor engagement expiration.

1. Click **[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Report Suites]**.
1. In the [!UICONTROL Report Suite Manager], click **[!UICONTROL Edit Settings]** > **[!UICONTROL Marketing Channels]** > **[!UICONTROL Marketing Channel Expiration]**.

   ![](assets/mchannel_expiration.png)

1. Configure the visitor engagement expiration fields.
1. Click **[!UICONTROL Save.]**
