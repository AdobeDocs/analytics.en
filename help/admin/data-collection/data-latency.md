---
description: The Include Current Data option in reports & analytics lets you view the latest Analytics data, often before data is fully processed and finalized. Current data displays most metrics within minutes, providing actionable data for quick decision making.
keywords: missing data;slow
seo-description: The Include Current Data option in reports & analytics lets you view the latest Analytics data, often before data is fully processed and finalized. Current data displays most metrics within minutes, providing actionable data for quick decision making.
seo-title: Current Data
solution: Analytics
subtopic: Current data
title: Current Data
topic: Reports
uuid: b0415201-118c-4e4c-9fc6-f20843eb00a6
index: y
internal: n
snippet: y
---

# Current Data

The Include Current Data option in reports & analytics lets you view the latest Analytics data, often before data is fully processed and finalized. Current data displays most metrics within minutes, providing actionable data for quick decision making.

Current Data is enabled by default on all reports that support it. When enabled, metrics appear in reports in one of three time frames, as explained in [Typical Latency](../data-collection/data-latency.md#section_E0ACA69D5CBE4CEDAB3688F39ABE7803). If you would rather view all metrics after the data is fully processed, you can disable Current Data by removing users from the Current Data Users group.

Keep the following in mind as you view current data:

* Applying a segment to a report turns the current data view off. Segments are applied to finalized data. 
* Classifications are not applied to current data. 
* Correlation, subrelation, and pathing reports do not provide current data. When you run these reports, the current data toggle is disabled. 
* Metrics introduced in v15, such as Total Time Spent and Bounces, do not provide current data.

## Typical Current Data Latency {#section_E0ACA69D5CBE4CEDAB3688F39ABE7803}

Metrics appear in one of the following three time frames. Click the clock icon next to the Include Current Data toggle to see the actual latency value for each metric on a report. 

<table id="table_17C8732F72AD442D87F61DEA919FB3C9"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Time Frame </th> 
   <th colname="col2" class="entry"> Metrics </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> under 10 minutes </td> 
   <td colname="col2"> 
    <ul id="ul_17842ECA228041ECA52530660F2F3883"> 
     <li id="li_9600BD79A130471491203B58DAD8211A">Instances on props </li> 
     <li id="li_6DAFCD8CABBD49479F6311D470FEECC3">Page views on pages </li> 
     <li id="li_6FA887313D8545B28BE0D9406ACA7785">searches </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Between 10 and 35 minutes </td> 
   <td colname="col2"> 
    <ul id="ul_7EEC3D74CB8F48EAA5A8A8C5721D224F"> 
     <li id="li_5EB6C2A2C7E1477AA24C606542EB3783">Custom events </li> 
     <li id="li_954DC0A1D00C462AA6F7A3794BBE75D0">Revenue, orders, units </li> 
     <li id="li_146D4147A9E944FB93CFB03E310BB4B1">Instances and click-throughs on conversion variables </li> 
     <li id="li_0A6BC530455846A8BE4EB888F339FC7A">Daily Unique Visitors on Site Metrics Report </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Between 45 and 120 minutes </td> 
   <td colname="col2"> 
    <ul id="ul_378552EF78B94DFCB12A34E73095989C"> 
     <li id="li_8C18460A685A480EB6679FA5F5967F5D">Visits </li> 
     <li id="li_E661193463CC475F81DA5810B1C41A05">Unique Visitors </li> 
     <li id="li_C8B819E09C014A1CB6D6CF8B771B7925">Participation </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

Because some of the data that is displayed on the current data view has not been fully processed, you will see a slight difference between values reported on the current data view and the finalized view. On trended reports, the data difference is typically within 1%.

If you experience latency that is consistently outside of this range, see [Latency Troubleshooting](../data-collection/latency.md#concept_9EEBF15433E3490FBA099925FCAEB1D1).

## Data Latency and Time-Stamped Hits {#section_465A470D11DE4AC3A559E278C1159E3B}

Data is time stamped when offline data is enabled in the mobile SDK (default setting) or anytime a report suite is [configured to accept time-stamped data](https://marketing.adobe.com/resources/help/en_US/sc/implement/timestamp.html). Data collected offline on mobile devices may be sent hours or weeks after the date when it happened. These hits may be queued within the Analytics platform for minutes or hours longer than hits without time stamps:

* For time-stamped data sent in very near current time, the probable delay is 10-15 minutes. 
* For time-stamped data sent in from yesterday, the probable delay is about 2 hours. 
* For time-stamped data sent in that is older than yesterday, every day adds about 1 hour of delay, up to 15 days ago, when the delay stops going up.

## Data Latency as a Result of A4T Configuration {#section_806CE36354FC4C539A0DED9266A5C704}

After the A4T integration is enabled in Adobe Target, you will experience an additional 5-10 minutes of latency in Adobe Analytics. This latency increase allows data from Analytics and Target to be stored on the same hit, allowing you to break down tests by page and site section.

This increase is reflected in all Adobe Analytics services and tools, including the live stream and real-time reporting, and applies in the following scenarios:

* For live stream, real-time reports & API requests, and current data for traffic variables, only hits with a supplemental data ID are delayed. 
* For current data on conversion metrics, finalized data, and data feeds, all hits are delayed an additional 5-7 minutes.

Be aware that the latency increase starts after you implement the Experience Cloud ID service, even if you have not fully implemented this integration.

## Calculated Metrics {#section_C582289D236C42D6B3C6495A92A5D18A}

Since calculated metrics can be created using metrics that have different latency, some recent values might be calculated using incomplete data in the current data view. For example, let's say you created a "Page Views per Visit" calculated metric with the following formula:

```
Page Views/Visits
```

Since Page Views typically appear within 10 minutes, and Visits typically appear within 2 hours, calculated metrics within this latency window are calculated using incomplete metrics. If you post a new page that gets 4000 hits from 4000 different visits over a 2 hour time frame, the latency difference between these metrics can cause incomplete calculations for the latest hour or two: 

|  Time Frame  | Page Views (10 min latency)  | Visits (90 minute latency)  | Page Views Per Visit  |
|---|---|---|---|
|  past 30 minutes  | 700 page views  | 0 visits  | 0  |
|  past 1 hour  | 1600 page views  | 0 visits  | 0  |
|  past 2 hours  | 1900 page views  | 1000 visits  | 1.9  |
|  2 or more hours ago (finalized data)  | 4000 page views  | 4000 visits  | 1  |

This is most visible when reporting on new values, or on very short time frames. When you are reporting over longer periods, the latency differences that occur in the last few hours of reporting are unlikely to have any noticeable impact on calculated metrics.

If you have calculated metrics that might be impacted by these differences, either turn current data off, or add the metrics used in the calculation directly to the report so you can see the latency values for each metric.

## Downloaded Reports {#section_0FFF8B23966F49069021225A2CA4D011}

When you download a report with the current data view enabled, the report is queued, generated, and then returned to the browser. If additional metrics are reported while the report is generating, these metrics appear in the report. This might lead to the downloaded report being slightly more up-to-date.

## Control User Access to Current Data {#section_E7492A84197A49188E3E3555849288DB}

The Include Current Data option is displayed for all members of the **[!UICONTROL Current Data Users]** group. All users are added to this group by default. 
