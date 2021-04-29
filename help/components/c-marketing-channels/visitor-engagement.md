---
description: Learn how to specify visitor engagement expiration in Marketing Channels.
subtopic: Marketing channels
title: Marketing channel expiration
feature: Reports & Analytics Basics
uuid: 47f1ccaf-3ce7-494d-b456-956a3a3c6c9a
exl-id: a9df659b-3b6a-4bdb-bd77-f4490d2b7c79
---
# Marketing channel expiration

>[!NOTE]
>
>To maximize effectiveness of Marketing Channels for Attribution IQ and Customer Journey Analytics, we have published some [revised best practices](/help/components/c-marketing-channels/mchannel-best-practices.md).

Learn how to specify the expiration, or visitor engagement period, for Marketing Channels.

Visitor engagement is how much time you want to allow for the visitor's previous activity on your site to be attributed to the first touch channel. The default expiration setting is 30 days. 

If the visitor uses the site frequently, the engagement window will roll with them. They must be inactive for 30 days for the period to expire and channels to be reset. Both the first and last-touch channels for a visitor will reset after 30 days of inactivity on that browser. 

Example:

* Day 1: User comes to the site on Display. First & Last-touch channels will get set to Display.
* Day 2: User comes to the site on Natural Search. First-touch remains Display, and Last touch is set to Natural Search.
* Day 35: User has not been to the site in 33 days and comes back using the tab they had open in their browser. Assuming a 30 day engagement window, the window would have closed and Marketing Channel cookies would be expired. The first touch & last touch channel will get reset, and will be set to Session Refresh since the user came from an internal URL.

## Marketing channel expiration settings

Expiration settings consist of the following:

| Field  | Definition  |
|--- |--- |
|Days of Inactivity|The number of days that must pass before a visitor's first-touch engagement expires. The default value is 30.|
|Never|The visitor's engagement period does not expire.|
|Channel Reset|Expires all visitor engagement periods.  If you have need to reset all marketing channel data you can expire all visitor engagement periods. You may need to reset data if your processing rules were previously configured incorrectly. All first and last touch channel values will immediately expire and be reset when visitors return.|

## Define marketing channel expiration {#define-expiration}

Specify the visitor engagement period.

1. Click **[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Report Suites]**.
2. In the [!UICONTROL Report Suite Manager], click **[!UICONTROL Edit Settings]** > **[!UICONTROL Marketing Channels]** > **[!UICONTROL Marketing Channel Expiration]**.

   ![](assets/mchannel_expiration.png)

3. Configure the visitor engagement period fields.
4. Click **[!UICONTROL Save.]**
