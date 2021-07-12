---
description: Steps on running the different report types.
title: Run different report types
uuid: f59ab2a1-e916-46e8-bb5b-e6361ba00dda
feature: Reports & Analytics Basics
role: User, Admin
exl-id: 2e8cac1b-d133-4095-b5db-886ce0566b82
---
# Run different report types

Steps on running the different report types.

## Run a ranked report {#task_C570BA4A213F4F2EB7B30E012934BE7D}

In a ranked report, the table shows the rankings of the report pages in relation to the metric, according to number or percentage. Ranked reports can display multiple metrics in a report.

1. Generate a report, such as a [!UICONTROL Pages Report] ( **[!UICONTROL Reports]** > **[!UICONTROL Site Content]** > **[!UICONTROL Pages]**).
1. In the report header, click **[!UICONTROL Ranked.]**
1. To rank the report, click a column heading in the table.

   Ranked reports can have up to 200 items listed in the table (such as products, categories, web pages, and so on) and ten metrics (revenue, orders, views, and so on).

## Run a trended report {#task_F03B4E760B9E4EA29FC3F654E6316887}

Trended reports display metrics over time. You use this report type when you want to see how a segment performs from one time period to the next.

Most Conversion and Traffic reports have a Trended view available. Using the [!UICONTROL Calendar], you can show improvement for any time period breakdowns, including days of a month, weeks of a year, weeks of a quarter, months of a year, and so on. Trended reports show trends for a single metric (revenue, orders, views, and so on) for up to five items (such as products, categories, web pages, and so on).

**To run a trended report** 

1. Run a conversion or traffic report, such as **[!UICONTROL Reports]** > **[!UICONTROL Site Content]** > **[!UICONTROL Pages]**.
1. Under **[!UICONTROL Report Type]**, click **[!UICONTROL Trended.]**

## Run a Fallout report {#task_8FD97C8260464F9DA731A93DB8F80184}

The [!UICONTROL Fallout Report] shows the number of visitors who visited a pre-specified sequence of pages. It also shows conversion and fallout rates between each step.

Check out the new [Fallout Analysis](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/visualizations/fallout/fallout-flow.html) panel in Analysis Workspace! 

1. In [!UICONTROL Adobe Analytics], click **[!UICONTROL Reports]** > **[!UICONTROL Paths]** > **[!UICONTROL Pages]** > **[!UICONTROL Fallout]**.
1. On the [!UICONTROL Fallout Report] page, click **[!UICONTROL Launch the Fallout Report Builder]**.

   ![Step Result](assets/fallout_add_items.png)

1. On the [!UICONTROL Define Checkpoints] page, specify the checkpoints that you want to use for the report.
1. Click **[!UICONTROL Run Report]**.

   ![Step Result](assets/fallout_report.png)

## Run a Page Flow report {#task_133E8B87C3F04DA0A42D10CBA499305B}

Page Flow reports show the order in which your visitors access pages and navigate through your site. This report helps answer

Check out the [Flow visualization](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/visualizations/fallout/fallout-flow.html) in Analysis Workspace!

For example, click **[!UICONTROL Reports]** > **[!UICONTROL Paths]** > **[!UICONTROL Pages]** > **[!UICONTROL Next Page Flow]**.

## Run a marketing channel report {#task_64ADED5CC75248319E06E3E029B47F78}

Marketing Channel reporting provides an overview report of the first and last-touch channel allocation, with standard reporting metrics like revenue, orders, and cost. These reports enable you to analyze how much revenue each channel generates.

See the [Marketing Channel](/help/components/c-marketing-channels/analyze-mc.md) help system for more information.

## Run an Anomaly Detection report {#task_4808C96327354D789C075823F5C3A049}

You can run [Anomaly Detection and Contribution Analysis](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/virtual-analyst/anomaly-detection/anomaly-detection.html) only in Analysis Workspace.

## Run a Real-Time report {#task_5D25929C918E40B18965222FA94176B0}

Describes how to view and interpret real-time reports.

**[!UICONTROL Reports > Site Metrics > Real-Time]** .

Real-Time reporting offers two main reports - an overview report and a detail report. They each consist of a number of reportlets.

For information on configuring real-time reports, see the [Analytics Reference Guide](https://experienceleague.adobe.com/docs/analytics/landing/home.html#RealTime_Reports_Configuration).

1. Take a look at the **[!UICONTROL Overview]** report and its components:  ![](assets/rtr_overview_report.png)

   <table id="choicetable_8586BECF55E843B2B5CD41205567EA32"> 
   <thead class="chhead sthead"> 
   <th class="choptionhd"> UI Component </th> 
   <th class="chdeschd"> Description </th> 
   </thead> 
   <tr class="chrow strow"> 
   <td class="choption"><strong>Select Report Suite</strong></td> 
   <td class="chdesc stentry"> Shows the report suite that this real-time report covers. To change the report suite, see <a href="https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/real-time-reports/t-realtime-admin.html"  > Real-Time Reports Configuration </a>. </td> 
   </tr> 
   <tr class="chrow strow"> 
   <td class="choption"><strong>Switch among reports</strong></td> 
   <td class="chdesc stentry"> Lets you switch among the reports you have set up (maximum of 3.) </td> 
   </tr> 
   <tr class="chrow strow"> 
   <td class="choption"><strong>Select time range</strong></td> 
   <td class="chdesc stentry"> Lets you choose the overall time range to be used by all reportlets in the report. </td> 
   </tr> 
   <tr class="chrow strow"> 
   <td class="choption"><strong>Configure reports</strong></td> 
   <td class="chdesc stentry"> This gear icon link is visible only if you have Admin rights. Clicking it takes you to the Report Suite Manager under <span class="ignoretag"> <span class="uicontrol"> Admin Tools </span>  &gt; <span class="uicontrol"> Report Suites </span>  &gt; <span class="uicontrol"> Edit Settings </span>  &gt; <span class="uicontrol"> Real-Time </span> </span>. </td> 
   </tr> 
   <tr class="chrow strow"> 
   <td class="choption"><strong>Full-screen view</strong></td> 
   <td class="chdesc stentry"> The full-screen view icon is visible only if your monitor has a specific aspect ratio (either 16:9 or 16:10) AND if your browser supports it. Note that you cannot interact with the screen while it is in full-screen mode (press <span class="uicontrol"> Esc </span> to exit). Full-screen mode does not time out. </td> 
   </tr> 
   <tr class="chrow strow"> 
   <td class="choption"><strong>Site Traffic Reportlet</strong></td> 
   <td class="chdesc stentry"> The blue trend line data shows the traffic total for the overall site. The X axis uses literal labels (15 minutes ago, 10 minutes ago) except for the current value, which is shown as a real-time expression. </td> 
   </tr> 
   <tr class="chrow strow"> 
   <td class="choption"><strong>Site Total Reportlet</strong></td> 
   <td class="chdesc stentry"> Presents a count of the Site Total for the real-time report's selected metric for the last N minutes. "N" is configurable through the Time Range selector. <p>The arrow color and direction are based on the following algorithm: 
      <ul id="ul_9F40CEA33798467393CB1266BB36D500"> 
      <li id="li_CCD01A44F912487DA5681EA50113643C">Significant Gain (Up arrow): &gt; 100% </li> 
      <li id="li_7402491A9A614851B7F2AE0C77BD9A97">Gain (Up Right arrow): between 5 % and 100% </li> 
      <li id="li_BCA79C08B5714D4B9315068112C66107"> Flat (Right arrow): between 5% and -5% </li> 
      <li id="li_234ECBD7D83A4AE680E4A70BF288681F"> Loss (Down Right arrow): between -5% and -100% </li> 
      <li id="li_10C5EA8803604C1CA714D3DB27478B31"> Significant Loss (Down arrow): &lt; -100% </li> 
      </ul> </p> <p>If the site total is reported in "instances", these instances reflect the dimension in the primary reportlet. If an instance-specific name exists (such as "Page Views",) the site total reports that name. </p> </td> 
   </tr> 
   <tr class="chrow strow"> 
   <td class="choption"><strong>Primary Reportlet</strong></td> 
   <td class="chdesc stentry"> Report for the Real-Time report's primary dimension and for its metric. Presents a trend line for that element for the selected time range. The metric total represents the sum for the full trend line. The arrow indicates if the item is strongly gaining, gaining, flat, losing or strongly losing. </td> 
   </tr> 
   <tr class="chrow strow"> 
   <td class="choption"><strong>Search Dialog</strong></td> 
   <td class="chdesc stentry"> The search impacts all reportlets. Search persists as you view the report. </td> 
   </tr> 
   <tr class="chrow strow"> 
   <td class="choption"><strong>Sort by... Most Popular/Gainers/ Losers</strong></td> 
   <td class="chdesc stentry"> You can toggle to sort by <span class="uicontrol"> Most Popular </span>(default), <span class="uicontrol"> Gainers </span> (dimensions showing the most growth), and <span class="uicontrol"> Losers </span> (dimensions that are on a downward trajectory.) <p>Here is the formula that is used to determine gainers or losers: Real-Time looks at the earliest sample and the next-to-latest sample and does a simple "% change" calculation. So if "Last 15 minutes" is selected, and n represents the current minute, n-1 is compared to n-15. Real-Time does not currently do any weighting. The current minute is ignored because it is not complete and would likely produce a false % change. </p> <p>This formula is consistent across all metrics used in the real-time report. </p> </td> 
   </tr> 
   <tr class="chrow strow"> 
   <td class="choption"><strong>Secondary 1 Reportlet</strong></td> 
   <td class="chdesc stentry"> Presents Real-Time Reports for the second provisioned report's dimension and for the metric. <p>The secondary 1 reportlet shows the top 4 categories; the 5th one is an aggregation of all remaining values. For each category, the total raw view of that category is provided. In addition, the total for all categories is shown in the center. </p> <p> Hovering on a section highlights the associated category, and displays the category trend line below the donut. </p> <p> Hovering on a line item highlights the line item plus the associated section and displays the category trend line below the donut. </p> </td> 
   </tr> 
   <tr class="chrow strow"> 
   <td class="choption"><strong>Secondary 2 Reportlet</strong></td> 
   <td class="chdesc stentry"> Presents Real-Time Reports for the third provisioned report's dimension and for the metric. Hovering on top of the item label slides the label to the right and reveals a trend line for the hovered item. </td> 
   </tr> 
   </table>    
   
1. Click a list item in the Primary Reportlet to launch the **[!UICONTROL Details]** view for that list item:  ![](assets/rtr_detail_report.png)

   | **Item Trend Reportlet** | Presents the trend line of the item that was selected in the Overview Report for the last N minutes. N is configurable through the Time Range selector.  |
   |---|---|
   | **Item Total Reportlet** | Presents a total metric count for the item that was selected in the Overview Report for the last N minutes. N is configurable through the Time Range selector.  |
   | **Correlated Secondary 1 Reportlet** | This reportlet is very similar to the Secondary 1 Reportlet. The only difference is the data source used to populate this report: in this example, it shows the correlation (or breakdown) between a specific page (the one you selected in the primary reportlet of the Overview report) and the instances viewed.  |
   | **Correlated Secondary 2 Reportlet** | This reportlet is very similar to the Secondary 2 Reportlet. The only difference is the data source used to populate this report: in this example, it shows the correlation (or breakdown) between a specific page (the one you selected in the primary reportlet of the Overview report) and the language dimension.  |
