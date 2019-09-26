---
description: Describes how to calculate common metrics using data feeds.
keywords: Data Feed;job;metrics;pre column;post column;bots;date filtering;event string;common;formulas
seo-description: Describes how to calculate common metrics using data feeds.
seo-title: Calculate metrics
solution: Analytics
title: Calculate metrics
topic: Reports and analytics
uuid: a45ea5bb-7c83-468f-b94a-63add78931d7
---

# Calculate metrics

Describes how to calculate common metrics using data feeds.

<!--Meike, I commented out this heading because it contains no content, and I'm troubleshooting a dita error-Bob
## Pre vs. Post column {#section_19967AF2FD9D44D6A8EC30F77E71F2ED}
-->

## Bots {#section_06753B95800F47668AAF52E7227F27C8}

Bots are excluded from data feeds according to the [bot rules](https://marketing.adobe.com/resources/help/en_US/reference/bot_rules.html) defined for your report suite.

## Date filtering {#section_3BFF4F7EED1F4FA69EBF12BF98B347E8}

Include rows from the date range you want included by filtering the `date_time` field. The `date_time` field is human readable (for example, `YYYY-MM-DD HH:MM:SS`) and is adjusted to the time zone of the report suite. For example, `date_time starts with "2013-12"` includes hits from December 2013.

## Event string {#section_87B686512EFD4A6CA072165CB28A130A}

The event string in `event_list` and `post_event_list` contains a comma-delimited list of events, which may have a value and/or a unique ID. We recommend doing all processing on the `post_event_list` because it is de-duplicated and has already applied logic to remove duplicate events with the same ID (see [Event Serialization](https://marketing.adobe.com/resources/help/en_US/sc/implement/c_event_serialization.html)).

For event ID to name mapping, see the event lookup delivered with your data feed.

For more information on events, see [Events](https://marketing.adobe.com/resources/help/en_US/sc/implement/c_events.html).

## Formulas for common metrics {#section_E26A01C234484857BF8C74443222AE41}

The following table contains instructions to calculate several common metrics.

<table id="table_814EA73C01EE4B2CA3CEB2839E19ADF9"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Metric </th> 
   <th colname="col2" class="entry"> How to calculate </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Page Views </td> 
   <td colname="col2"> <p> Page views can be calculated by counting when there is either a value in <code> post_pagename </code> or <code> post_page_url </code>. </p> 
    <p>You can use similar logic to count custom links: </p> 
    <ul id="ul_8DFBEE3ED30C465D8E55B1F3880D5263"> 
     <li id="li_009F2B7E3F9443889AE95B3358169444"> <code> post_page_event = 100 </code> to count custom links. </li> 
     <li id="li_866DA2F5C2404347863CD1417F822FE8"> <code> post_page_event = 101 </code> to count download links. </li> 
     <li id="li_4BC6E62CE8B1474DB22448FA32C9EE01"> <code> post_page_event = 102 </code> to count exit links. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Visits </td> 
   <td colname="col2"> 
    <ol id="ol_FE1831195A474650B07D7820DCD38728"> 
     <li id="li_274590E937A142D19B204768B1F10325">Exclude all rows where <code> exclude_hit &gt; 0 </code>. </li> 
     <li id="li_038B8FF66EA44E138C8A8932DA7B39E5">Exclude all rows with <code> hit_source = 5,7,8,9 </code>. 5, 8, and 9 are summary rows uploaded using data sources. 7 represents transaction ID data source uploads that should not be included in visit and visitor counts. See <a href="../../../export/analytics-data-feed/c-df-contents/datafeeds-hit-source.md#concept_FE4C114F6A524F7593D5CAC944C36C42" format="dita" scope="local"> Hit Source Lookup </a>. </li> 
     <li id="li_7FCD9BDF4D8547719420B34BA48BFA2D">Combine <code> post_visid_high </code>, <code> post_visid_low </code>, <code> visit_num </code>, and <code> visit_start_time_gmt </code>*. Count unique number of combinations. </li> 
    </ol> <p>*In rare circumstances, internet irregularities, system irregularities, or the use of custom visitor IDs can result in duplicate <code> visit_num </code> values for the same visitor ID that are not the same <a href="https://marketing.adobe.com/resources/help/en_US/reference/?f=metrics_visit" format="http" scope="external"> visit </a>. To avoid resulting issues, also include <code> visit_start_time_gmt </code> when counting visits. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Visitors </td> 
   <td colname="col2"> 
    <ol id="ol_E2BC9235A3164EF5936EFC5D9E9327D0"> 
     <li id="li_2C145CA54EBF4B358FC7DC78D8DA577D">Exclude all rows where <code> exclude_hit &gt; 0 </code>. </li> 
     <li id="li_9EF364652A214A4D9B66552BC6BBE527">Exclude all rows with <code> hit_source = 5,7,8,9 </code>. 5, 8, and 9 are summary rows uploaded using data sources. 7 represents transaction ID data source uploads that should not be included in visit and visitor counts. See <a href="../../../export/analytics-data-feed/c-df-contents/datafeeds-hit-source.md#concept_FE4C114F6A524F7593D5CAC944C36C42" format="dita" scope="local"> Hit Source Lookup </a> </li> 
     <li id="li_4AB5129315644A29987E8FCB9C9F9C39">Combine <code> post_visid_high </code> with <code> post_visid_low </code>. Count unique number of combinations. </li> 
    </ol> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Event instances </td> 
   <td colname="col2"> <p>When an event is set on a hit, <code> post_event_list </code> contains the event. The <code> post_event_list </code> is de-duplicated and is recommended to determine event instances. </p> <p>For example: </p> 
    <code>
      post_event_list = 1,200 
    </code> <p>Indicates an instance of <code> purchase </code> and <code> event1 </code>. </p> 
    <ol id="ol_84B529A668A54686957D1EB36D944467"> 
     <li id="li_F953D7668C704C1AB7970123E369472A">Exclude all rows where <code> exclude_hit &gt; 0 </code>. </li> 
     <li id="li_65B0B504DB654479844EAE490D9283EB">Exclude all rows with <code> hit_source = 5,8,9 </code>. These are summary rows uploaded using data sources. See <a href="../../../export/analytics-data-feed/c-df-contents/datafeeds-hit-source.md#concept_FE4C114F6A524F7593D5CAC944C36C42" format="dita" scope="local"> Hit Source Lookup </a>. </li> 
     <li id="li_FB1C31048EC7415088F41E8CDC01AEBD">Count the number of times the event lookup value appears in <code> post_event_list </code>. </li> 
    </ol> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> eVar instances </td> 
   <td colname="col2"> <p>When an eVar is set on a hit, <code> event_list </code> contains an instance of that eVar. </p> <p>For example: </p> 
    <code>
      post_event_list&amp;nbsp;=&amp;nbsp;100,101,106 
    </code> <p>Indicates an instance of <code> eVar1 </code>, <code> eVar2 </code>, and <code> eVar7 </code>. This means that a value for these three eVars was set on the hit. </p> <p>To calculate instances for eVars, use the same logic explained in <i>Event instances</i> above, but count the number of times the eVar lookup appears in the <code> post_event_list </code>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Time Spent </td> 
   <td colname="col2"> <p>To calculate time spent, you must group hits by visit, then order them according to the hit number within the visit. </p> 
    <ol id="ol_946E7CD6005A42EB9A4B79268BF84066"> 
     <li id="li_D109FAF4686D4935B7A6DCA5D383612F">Exclude all rows where <code> exclude_hit &gt; 0 </code>. </li> 
     <li id="li_D88F3691DB6746EBA84AA52841E56803">Group hits for a visit by concatenating <code> visid_high </code>, <code> visid_low </code>, and <code> visit_num </code>. </li> 
     <li id="li_08792F3BDFEA4DA29E0983C4BE65D73B">Order hits for each visit by <code> visit_page_num </code>. </li> 
     <li id="li_4B956734DBB84603B86DDA6A2B0B41A0">Using <a href="../../../export/analytics-data-feed/c-df-contents/datafeeds-page-event.md#concept_A3AC076C3728445EB4CC572A6EDA5263" format="dita" scope="local"> page_event </a>, filter the types of hits you want. </li> 
     <li id="li_2C5AC0477CFC409B8F169079354C8226">Find hits where the value you want to track time spent is set. For example: 
      <code>
        hit&nbsp;1:&nbsp;post_prop1=red hit&nbsp;2:&nbsp;post_prop1=blue 
      </code> </li> 
     <li id="li_20106B322F7B45CE8D2FBD9B0CB3D60D">Subtract the <code> post_cust_hit_time </code> for hit 1 from the <code> post_cust_hit_time </code> for hit 2 to determine the seconds between these two hits. The result is the time spent for <code> post_prop1=red </code>. If this results in a negative number, it indicates that the hit was received out-of-order and the calculation should be discarded. </li> 
    </ol> <p>This logic can be extended to calculate time spent for other values. When calculating time spent, Analytics calculates time spent based on the time the value was set in a <code> track </code> ( <code> page_event=0 </code>) or <code> trackLink </code> ( <code> page_event=10|11|12 </code>) call, to the time of the next page view ( <code> track </code> call). </p> <p>When reporting time spent for a specific period, marketing reports &amp; analytics and ad hoc analysis evaluate hits beyond the reporting period to determine time spent for values within the reporting period, except when the start and/or end date of the time period is on a monthly boundary. Due to the complexity of these calculations, it might be difficult to match the time spent metrics exactly. Data warehouse does not evaluate hits beyond the reporting period. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Revenue, orders, units </td> 
   <td colname="col2"> <p>Currency conversion is applied to the <code> post_product_list </code> according to the settings for the report suite, so using that column is recommended. </p> 
    <ol id="ol_03D62086EDDE42AD82049830D85FDC69"> 
     <li id="li_2A5B8205EA30492986C35DC382B91F16">Exclude all rows where <code> exclude_hit &gt; 0 </code>. </li> 
     <li id="li_6417C228AC414B01A30F85BE4842ED3C">Exclude all rows with <code> hit_source = 5,8,9 </code>. 5-9 represent summary rows uploaded using data sources. See <a href="../../../export/analytics-data-feed/c-df-contents/datafeeds-hit-source.md#concept_FE4C114F6A524F7593D5CAC944C36C42" format="dita" scope="local"> Hit Source Lookup </a>. </li> 
     <li id="li_C48F91C74F5E4286B5F0B285E33AF733">Ignore purchase data for rows where <code> duplicate_purchase = 1 </code>. This flag indicates that the purchase is a duplicate (meaning that a hit with the same <code> purchaseID </code> was already recorded). </li> 
     <li id="li_FA1639FEF516419BA1BFDC37B063B346"> <p>The <code> post_product_list </code> uses the same syntax as <a href="https://marketing.adobe.com/resources/help/en_US/sc/implement/?f=c_products" format="http" scope="external"> s.products </a>, so you can parse this string to calculate metrics. For example: </p> 
      <code>
        ;Cross Trainers;1;69.95,;Athletic Socks;10;29.99 
      </code> <p>By parsing this string, you can determine that 1 pair of cross trainers were purchased for $69.95, and that total revenue from this purchase was $99.94. </p> </li> 
    </ol> <p>Note:  Analytics allows currency events that contain product revenue to be passed in through the events string, so you might need to account for revenue that is not in the products string. See <i>Numeric/Currency Events</i> in <a href="https://marketing.adobe.com/resources/help/en_US/sc/implement/?f=c_events" format="http" scope="external"> s.events </a>. </p> </td> 
  </tr> 
 </tbody> 
</table>
