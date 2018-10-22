---
description: Learn how to assign cost and budget amounts to channels.
seo-description: Learn how to assign cost and budget amounts to channels.
seo-title: Costs and budgets
solution: Analytics
subtopic: Marketing channels
title: Costs and budgets
topic: Reports and analytics
uuid: 9656fb1f-a91a-4a66-b5b0-5a4cc0223b08
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

See [Calculated metrics used Marketing Channel reports](../c-marketing-channels/c-channel-calc-metrics.md#topic_4521D324A79E43EF99E69FCDE1E92F74).

You can assign costs and budgets only to channels. All costs are given a time range over which they apply in reporting. When costs are associated with a channel directly, an allocation metric is chosen to show how costs break down across campaigns within a channel.

After you add cost and budget items, you can export the table data to a CSV file. You can also import a CSV file to the Marketing Channel Costs page.

>[!NOTE]
>
>&nbsp;If you are familiar with importing classifications, you can add Numeric 2 classifications and upload them for use as cost and budget metrics. See [Numeric 2 Classifications](https://marketing.adobe.com/resources/help/en_US/sc/saint/index.html#Numeric%202%20Classifications).

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

<table id="table_C18A0F1C9E214EB585A29801BA2400F8"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Field </p> </th> 
   <th colname="col2" class="entry"> <p>Definition </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Name </p> </td> 
   <td colname="col2"> <p>The name of the cost or budget item. (This value is the <span class="uicontrol"> Key</span> value if you are using SAINT.) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Channel </p> </td> 
   <td colname="col2"> <p>The channel to which you want to associate this amount. Specify whether the cost or budget applies to a First Touch channel or Last Touch channel. Think of a first-touch cost amount as a one-time new engagement. A last-touch cost amount is for click-throughs. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Date Range </p> </td> 
   <td colname="col2"> <p>The time that you want to use for this amount. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Type </p> </td> 
   <td colname="col2"> <p> The type of cost or budget, either a Rate or a One-Time Cost. The Rate specifies an ongoing cost, such as an amount per click. A One-Time Cost lets you specify a Distribute By amount. For example, if you distribute the cost by clicks, the affiliate with 60% of the total clicks is attributed 60% of the total cost. The <span class="uicontrol"> Distributed by</span> value is the metric used when you are breaking down numeric classifications. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Export File </p> </td> 
   <td colname="col2"> <p>Lets you export the table data to a CSV file. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Import File </p> </td> 
   <td colname="col2"> <p>Lets you import a CSV file to the <span class="wintitle"> Marketing Channel Costs</span> page. </p> </td> 
  </tr> 
 </tbody> 
</table>

