---
description: Learn how to assign cost and budget amounts to channels.
seo-description: Learn how to assign cost and budget amounts to channels.
seo-title: Costs and budgets
solution: Analytics
subtopic: Marketing channels
title: Costs and budgets
topic: Reports and analytics
uuid: 7ba0e968-e565-4d4c-8fc0-39bf25d3e5b1
index: y
internal: n
snippet: y
---

# Costs and budgets

Learn how to assign cost and budget amounts to channels.

## Costs and budgets {#topic_7CCFD3B54440433FBA0E4EE127F58B0C}

Learn how to assign cost and budget amounts to channels. 

Cost represents what you spend on the channel. Budget represents the amount available to spend.

A useful way to view your ROI is to create a calculated metric that shows revenue minus costs. Or create one that shows the total cost along with a breakdown of cost per new engagement. For example, you can run a [!UICONTROL First-Touch Channel] report showing new engagements. Then add a First-Touch Cost metric that shows you the cost per new engagement, by creating a calculated metric.

See [Calculated metrics used Marketing Channel reports](../../components/c-marketing-channels/c-channel-calc-metrics.md#topic_4521D324A79E43EF99E69FCDE1E92F74).

You can assign costs and budgets only to channels. All costs are given a time range over which they apply in reporting. When costs are associated with a channel directly, an allocation metric is chosen to show how costs break down across campaigns within a channel.

After you add cost and budget items, you can export the table data to a CSV file. You can also import a CSV file to the Marketing Channel Costs page.

## Add cost and budget items {#task_9238A033994440748960DE21593E6388}

Add cost and budget items to Marketing Channels.

1. Click **[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Report Suites]**.
1. On the [!UICONTROL Report Suite Manager] page, select a report suite.
1. Click **[!UICONTROL Edit Settings]** > **[!UICONTROL Marketing Channels]** > **[!UICONTROL Marketing Channel Costs]**.
1. On the [!UICONTROL Marketing Channel Costs] page, click **[!UICONTROL Add Cost Item]** or **[!UICONTROL Add Budget Item]**.
1. Click **[!UICONTROL Save.]**

   To continue adding cost items, click **[!UICONTROL Save and Add Another]**. 

1. (Optional) To export or import CSV files, access the [!UICONTROL Marketing Channel Costs] page, click **[!UICONTROL Export File]** or **[!UICONTROL Import File]**, then follow the prompts.

## Marketing Channel costs - definitions {#reference_0B193210E10A4B6B84A385A781FD9515}

Field definitions for Marketing Channel Costs or Budgets.



| Field  | Definition  |
|--- |--- |
|Name|The name of the cost or budget item. (This value is the  Key value if you are using SAINT.)|
|Channel|The channel to which you want to associate this amount. Specify whether the cost or budget applies to a First Touch channel or Last Touch channel. Think of a first-touch cost amount as a one-time new engagement. A last-touch cost amount is for click-throughs.|
|Date Range|The time that you want to use for this amount.|
|Type|The type of cost or budget, either a Rate or a One-Time Cost. The Rate specifies an ongoing cost, such as an amount per click. A One-Time Cost lets you specify a Distribute By amount. For example, if you distribute the cost by clicks, the affiliate with 60% of the total clicks is attributed 60% of the total cost. The  Distributed by value is the metric used when you are breaking down numeric classifications.|
|Export File|Lets you export the table data to a CSV file.|
|Import File|Lets you import a CSV file to the  Marketing Channel Costs page.|
