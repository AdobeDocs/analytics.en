---
description: Adobe Analytics offers various Time Spent metrics and dimensions. Find out what they are and how they are calculated.
seo-description: Adobe Analytics offers various Time Spent metrics and dimensions. Find out what they are and how they are calculated.
seo-title: Time Spent
solution: Analytics
title: Time Spent
topic: Metrics
uuid: a9f63da3-7e79-49c3-9b0b-6dcd2ae6aadc
index: y
internal: n
snippet: y
---

# Time Spent

Adobe Analytics offers various Time Spent metrics and dimensions. Find out what they are and how they are calculated.

* [Time Spent Metrics](../../../components/c-variables/c-metrics/metrics-time-spent.md#section_4F54D70300944748A62088F5870E4B6C) 
* [Time Spent Dimensions](../../../components/c-variables/c-metrics/metrics-time-spent.md#section_D51606544CB046FC902E2E317318892C) 
* [How Time Spent is Calculated](../../../components/c-variables/c-metrics/metrics-time-spent.md#section_90A3882638974969A4B8B674FFDB7624) 
* [FAQs about Time Spent](../../../components/c-variables/c-metrics/metrics-time-spent.md#section_51C2735BACAB42CCBA1DD3CBF238E2F7) 
* [Calculation Examples](../../../components/c-variables/c-metrics/metrics-time-spent.md#section_3D63D6A601F34E42AD5366435CB610D5)

## Time Spent Metrics {#section_4F54D70300944748A62088F5870E4B6C}

This table lists the various Time Spent metrics, their definition, and where in Adobe Analytics you can use them. 

<table id="table_7095406DF1614F3CAD5E437B919598D1"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Metric </th> 
   <th colname="col2" class="entry"> Definition </th> 
   <th colname="col3" class="entry"> Available in </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Total seconds spent </p> </td> 
   <td colname="col2"> <p>Represents the total amount of time visitors interact with a specific dimension item. </p> <p>Includes the instance of a value and persistence across all subsequent hits. In the case of props, time spent is counted across subsequent link events as well. </p> </td> 
   <td colname="col3"> <p>Analysis Workspace </p> <p>Reports &amp; Analytics </p> <p>Report Builder (called ‘total time spent’) </p> <p>Data Warehouse </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Time spent per visit (Seconds) </p> </td> 
   <td colname="col2"> <p><i>Total seconds spent / (visit-bounces)</i> </p> <p>Represents the average amount of time visitors interact with a specific dimension item during each visit. </p> </td> 
   <td colname="col3"> <p>Analysis Workspace </p> <p>Reports &amp; Analytics </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Time spent per visitor (Seconds) </p> </td> 
   <td colname="col2"> <p><i>Total seconds spent / (unique visitor - bounce unique visitors)</i> </p> <p>Represents the average amount of time visitors interact with a specific dimension item across the visitor’s lifetime (length of their cookie). </p> </td> 
   <td colname="col3"> <p>Analysis Workspace </p> <p>Reports &amp; Analytics </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Average time spent on site (Seconds) </p> </td> 
   <td colname="col2"> <p>Represents the total amount of time visitors interact with a specific dimension item, per sequence with a dimension item. It is not just limited to “site” averages as the name suggests. See How Time Spent is Calculated section for more information on sequences. </p> <p>Note:  This metric will very likely differ from Time Spent per Visit at a dimension item level due to the differences in the denominator in the calculation. </p> </td> 
   <td colname="col3"> <p>Analysis Workspace </p> <p>Reports &amp; Analytics (shown in minutes) </p> <p>Report Builder (shown in minutes) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Average time spent on page </p> </td> 
   <td colname="col2"> <p><b>Deprecated metric. </b> </p> <p>We recommend that you use ‘Average time spent on site’ if average time for a dimension item is needed. </p> </td> 
   <td colname="col3"> <p>Report Builder (when a dimension is in the request) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Total session length </p> <p>(Also known as: Previous session length) </p> </td> 
   <td colname="col2"> <p>Mobile App SDK only. Determined the next time the app is launched, for the previous session. Calculated in seconds, this metric does not count when the app is in the background, only when in use. This is a session-level metric. </p> <p>For example: You install app ABC and launch and use it for 2 minutes and then close the app. No data is sent about it this session time. The next time you launch it, Total Session Length will be sent with a value of 120. </p> </td> 
   <td colname="col3"> <p>Analysis Workspace </p> <p>Reports &amp; Analytics </p> <p>Report Builder </p> <p>Mobile Services UI </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Average session length (mobile) </p> </td> 
   <td colname="col2"> <p>Total Session Length / (Launches - First Launches) </p> <p>Mobile App SDK only. This is a session-level metric. </p> </td> 
   <td colname="col3"> <p>Report Builder </p> <p>Mobile Services UI </p> </td> 
  </tr> 
 </tbody> 
</table>

## Time Spent Dimensions {#section_D51606544CB046FC902E2E317318892C}

This table lists the various Time Spent dimensions, their definition, and where in Adobe Analytics you can use them. 

<table id="table_BF1B7B8620714105BFB5C1AC37ABE02C"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Dimension </th> 
   <th colname="col2" class="entry"> Definition </th> 
   <th colname="col3" class="entry"> Available in </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Time spent per visit - granular </p> </td> 
   <td colname="col2"> <p>The total time spent during the visit truncated to the nearest second, and applied to every hit that was part of the visit. This a visit-level dimension. </p> </td> 
   <td colname="col3"> <p>Analysis Workspace </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Time spent per visit - bucketed </p> </td> 
   <td colname="col2"> <p>The granular dimension bucketed into 9 different ranges. This is a visit-level dimension. Ranges include: </p> 
    <ul id="ul_BC909A2D22ED4D48A3F7CE6A666F26E5"> 
     <li id="li_0FB28A1F0D894B7C95724A8C6BD5B00B">Less than 1 minute </li> 
     <li id="li_10223656420A475AAB3443981D49D10E">1-5 minutes </li> 
     <li id="li_0DEE723B81C64EAFB5BD1125D48D3AD2">5-10 minutes </li> 
     <li id="li_B736AC970E0049EB8844480702F345A6">10-30 minutes </li> 
     <li id="li_21B8ECC3EE66497E8D870A004351B04B">30-60 minutes </li> 
     <li id="li_79FB658128FD4F97AAE1A803F1687BD1">1-2 hours </li> 
     <li id="li_CCC0746FEB954BECB9E670ECCDBF30F3">2-5 hours </li> 
     <li id="li_BD7AFC524C814F9FAE423A4E301661D4">5-10 hours </li> 
     <li id="li_C9B5F1A83F99437A98A61756EE286687">10-15 hours </li> 
     <li id="li_8CC5A279D5804C5EA34C1B3589EF07BA">15+ hours </li> 
    </ul> <p>Note:  Visits longer then 12 hours can occur when hits are received out of order. </p> </td> 
   <td colname="col3"> <p>Analysis Workspace </p> <p>Reports &amp; Analytics </p> <p>Report Builder </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Time spent on page - granular </p> </td> 
   <td colname="col2"> <p>The total time spent on each hit, truncated to the nearest second. It is a hit-level dimension and includes both page views and link events. It is not just limited to the “page” dimension, as the name suggests. </p> </td> 
   <td colname="col3"> <p>Analysis Workspace </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Time spent on page - bucketed </p> </td> 
   <td colname="col2"> <p>The granular dimension bucketed into 10 different ranges; however, the bucketed dimension only counts page views (and excludes link events). This is a hit-level dimension. Ranges include: </p> 
    <ul id="ul_D5F067A2520646A99AA261F9A4625C03"> 
     <li id="li_82307DE66EC548F0AD79DB1505A21F0D">less than 15 seconds </li> 
     <li id="li_585965B82C4D43B6870978A5CE63B5B6">15 to 29 seconds </li> 
     <li id="li_5C20DC78E126472A838818EBA1D954D0">30 to 59 seconds </li> 
     <li id="li_2579C0B9279340ABA3AD4A527D758239">1 to 3 minutes </li> 
     <li id="li_E0FD800E948049A48DB4329A3E7A2478">3 to 5 minutes </li> 
     <li id="li_D9DBBFE6004F42BD80BB4F9268DF7DA7">5 to 10 minutes </li> 
     <li id="li_20F146799679456E8D6434D79EE12C31">10 to 15 minutes </li> 
     <li id="li_A38951A553A14AE7A0F23A904EEE35DE">15 to 20 minutes </li> 
     <li id="li_D44D773A344E47BFAA771302A49D8BD4">20 to 30 minutes </li> 
     <li id="li_8766683DB29147CD8470D2317F750E97">more than 30 minutes </li> 
    </ul> </td> 
   <td colname="col3"> <p>Analysis Workspace </p> <p>Reports &amp; Analytics </p> </td> 
  </tr> 
 </tbody> 
</table>

## How Time Spent is Calculated {#section_90A3882638974969A4B8B674FFDB7624}

Adobe Analytics uses explicit values (including link events and video views) to calculate [!UICONTROL Time Spent].

>[!NOTE]
>
>Without link events like [!UICONTROL Video Views] or [!UICONTROL Exit Links], time spent on the last hit of a visit cannot be known. Additionally, for similar reasons, [!UICONTROL Bounce Visits] (i.e. [!UICONTROL Visits] with a single hit) will not have a [!UICONTROL Time Spent]associated.

The **numerator** in all time spent calculations is&nbsp;"Total seconds spent".

The **denominator** is not available as a separate metric in Analytics. For hit-level time spent metrics, the denominator is sequences. A sequence is a consecutive set of hits where a given variable contains the same value (whether by being set, spread forward, or persisted). "Spread forward" refers to the persistence of props between page views (i.e. across subsequent link events), for the purpose of calculating time spent.

* For example, in the case of [!UICONTROL Page Name] or other dimensions at the hit level, the denominator is essentially [!UICONTROL Instances] or [!UICONTROL Page Views], but with reloads and unset values (e.g. link events) counted as a single interaction (a sequence). 

* [!UICONTROL Bounce] and [!UICONTROL Exit] hits are also removed from the denominator because time spent cannot be known.

## FAQs about Time Spent {#section_51C2735BACAB42CCBA1DD3CBF238E2F7}

<table id="table_D8BA825412B6420390CA78D77A5E57C2"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Question </th> 
   <th colname="col2" class="entry"> Answer </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Can all Time Spent metrics be applied to any dimension? </p> </td> 
   <td colname="col2"> <p>These Time Spent metrics can be applied to any dimension: </p> 
    <ul id="ul_FC9513D0184B4A74BA1F4CCEA8BC1940"> 
     <li id="li_669156CC549040E08AB4977AF4B8AECB">Total seconds spent </li> 
     <li id="li_3CCD7E7D127448689228E98A5EE854CB">Time spent per visit (Seconds) </li> 
     <li id="li_1F61C157EC414C7F8702BC3F365AA2D7">Time spent per visitor (Seconds) </li> 
     <li id="li_A3EF959A9BAB4872915F1A5C1A86D48E">Average time spent on site (Seconds) </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Which time spent dimension is best used in breakdowns with other dimensions? </p> </td> 
   <td colname="col2"> <p>The “Time Spent on Page - granular” dimension is a hit-level dimension. Breaking this down by another dimension will tell you the seconds that a hit lasted where the breakdown dimension was also present. </p> <p>In the example below, the search term “classifieds” is associated with hit times of 54 seconds, 59 seconds, etc, perhaps indicating that visitors are spending time reading content returned for that search term. </p> <p style="text-align: center;"> <img placement="break" align="center" href="assets/time-spent1.png" id="image_99FB62DCADDA4F8887B14333E65FF8FA" width="500px" /> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>What metric is appropriate against the dimension of “Time Spent on Page - granular”? </p> </td> 
   <td colname="col2"> <p>Any metric. The dimension shows the time spent on the exact hit where the event occurred. Higher time spent means a visitor stayed longer on a page (hit) where the event occurred. </p> <p style="text-align: center;"> <img placement="break" align="center" href="assets/time-spent2.png" id="image_A741C1BA52254124B5C28D030FE20EFF" width="500px" /> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> How does <span class="wintitle"> Average Time Spent on Site </span> differ from <span class="wintitle"> Time Spent per Visit </span>? </td> 
   <td colname="col2"> <p>The difference is the denominator in the metric: </p> 
    <ul id="ul_E9D7B4D3EDCC4691B2C724E0FE5480D2"> 
     <li id="li_CA34D84A3164473A8737D258425CA468"> <span class="wintitle"> Average Time Spent on Site </span> uses the sequences that include a dimension item. </li> 
     <li id="li_2F2639480BE24927919732D00364EECA"> <span class="wintitle"> Time Spent per Visit </span> uses the visit count </li> 
    </ul> <p>As a result, these metrics may yield similar results at a visit level, but will be different at a hit level. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Calculation Examples {#section_3D63D6A601F34E42AD5366435CB610D5}

Assume the following set of server calls are for a single visitor within a single visit:

<table id="table_63CBB5097E5A46659877E2CA3C94D81C"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Visit hit # </th> 
   <th colname="col2" class="entry"> 1 </th> 
   <th colname="col3" class="entry"> 2 </th> 
   <th colname="col4" class="entry"> 3 </th> 
   <th colname="col5" class="entry"> 4 </th> 
   <th colname="col6" class="entry"> 5 </th> 
   <th colname="col7" class="entry"> 6 </th> 
   <th colname="col8" class="entry"> 7 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <b>Visit elapsed time (sec)</b> </td> 
   <td colname="col2"> 0 </td> 
   <td colname="col3"> 30 </td> 
   <td colname="col4"> 80 </td> 
   <td colname="col5"> 180 </td> 
   <td colname="col6"> 190 </td> 
   <td colname="col7"> 230 </td> 
   <td colname="col8"> 290 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Seconds spent</b> </td> 
   <td colname="col2"> 30 </td> 
   <td colname="col3"> 50 </td> 
   <td colname="col4"> 100 </td> 
   <td colname="col5"> 10 </td> 
   <td colname="col6"> 40 </td> 
   <td colname="col7"> 60 </td> 
   <td colname="col8"> - </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Hit type</b> </td> 
   <td colname="col2"> Page </td> 
   <td colname="col3"> Link </td> 
   <td colname="col4"> Page </td> 
   <td colname="col5"> Page </td> 
   <td colname="col6"> Page </td> 
   <td colname="col7"> Page </td> 
   <td colname="col8"> Page </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Page Name</b> </td> 
   <td colname="col2"> Home </td> 
   <td colname="col3"> - </td> 
   <td colname="col4"> Product </td> 
   <td colname="col5"> Home </td> 
   <td colname="col6"> Home <p>(reload) </p> </td> 
   <td colname="col7"> Cart </td> 
   <td colname="col8"> Order Confirmation </td> 
  </tr> 
 </tbody> 
</table>

#### eVar Example:
<table id="table_6D0CF0C53DC145D3A53C06EC3012BCC0">  
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Visit hit # </th> 
   <th colname="col2" class="entry"> 1 </th> 
   <th colname="col3" class="entry"> 2 </th> 
   <th colname="col4" class="entry"> 3 </th> 
   <th colname="col5" class="entry"> 4 </th> 
   <th colname="col6" class="entry"> 5 </th> 
   <th colname="col7" class="entry"> 6 </th> 
   <th colname="col8" class="entry"> 7 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <b>eVar1</b> </td> 
   <td colname="col2"> Red <p>(set) </p> </td> 
   <td colname="col3"> Red <p>(persisted) </p> </td> 
   <td colname="col4"> (expired) </td> 
   <td colname="col5"> Blue <p>(set) </p> </td> 
   <td colname="col6"> Blue <p>(set) </p> </td> 
   <td colname="col7"> Blue <p>(persisted) </p> </td> 
   <td colname="col8"> Red <p>(set) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>eVar seconds spent</b> </td> 
   <td colname="col2"> 30 </td> 
   <td colname="col3"> 50 </td> 
   <td colname="col4"> - </td> 
   <td colname="col5"> 10 </td> 
   <td colname="col6"> 40 </td> 
   <td colname="col7"> 60 </td> 
   <td colname="col8"> - </td> 
  </tr> 
 </tbody> 
</table>

#### Prop Example:
<table id="table_1CB4D24A6CAA479C8E59A7C77FFB8226">  
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Visit hit # </th> 
   <th colname="col2" class="entry"> 1 </th> 
   <th colname="col3" class="entry"> 2 </th> 
   <th colname="col4" class="entry"> 3 </th> 
   <th colname="col5" class="entry"> 4 </th> 
   <th colname="col6" class="entry"> 5 </th> 
   <th colname="col7" class="entry"> 6 </th> 
   <th colname="col8" class="entry"> 7 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <b>prop1</b> </td> 
   <td colname="col2"> A <p>(set) </p> </td> 
   <td colname="col3"> A <p>(spread forward) </p> </td> 
   <td colname="col4"> (not set) </td> 
   <td colname="col5"> B <p>set) </p> </td> 
   <td colname="col6"> B <p>(set) </p> </td> 
   <td colname="col7"> A <p>(set) </p> </td> 
   <td colname="col8"> C <p>(set) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>prop1 seconds spent</b> </td> 
   <td colname="col2"> 30 </td> 
   <td colname="col3"> 50 </td> 
   <td colname="col4"> - </td> 
   <td colname="col5"> 10 </td> 
   <td colname="col6"> 40 </td> 
   <td colname="col7"> 60 </td> 
   <td colname="col8"> - </td> 
  </tr> 
 </tbody> 
</table>

Based on the table above, Time Spent metrics are calculated as follows: 

|  prop1  | Total Seconds Spent  | Time Spent Per Visit  | Time Spent Per Visitor  | Count of Sequences  | Average Time Spent on Site  |
|---|---|---|---|---|---|
|  A  | 30+50+60=140  | 140/1=140  | 140/1=140  | 2  | 140/2=70  |
|  B  | 10+40=50  | 50/1=50  | 50/1=50  | 1  | 50/1=50  |
|  C  | 0  | 0  | 0  | 0  | 0  |
|  Unattributed time  | 100  | -  | -  | -  | -  |

|  eVar1  | Total Seconds Spent  | Time Spent Per Visit  | Time Spent Per Visitor  | Count of Sequences  | Average Time Spent on Site  |
|---|---|---|---|---|---|
|  Red  | 30+50=80  | 80/1=80  | 80/1=80  | 1  | 80/1=80  |
|  Blue  | 10+40+60=110  | 110/1=110  | 110/1=110  | 1  | 110/1=110  |
|  Unattributed time  | 100  | -  | -  | -  | -  |

For Time Spent dimensions, the following rows will appear in the associated reports:

* Time spent per visit (granular): 290 
* Time spent on page (granular): 10, 30, 40, 50, 60, 100

Some additional notes in support of the example:

* All Time Spent calculations are based on the visit elapsed time which starts at zero on the first hit of the visit. 
* “Seconds Spent” is the difference between the timestamp of the current hit and the timestamp of the next hit. As a result, the last hit of the visit (and bounces) have no time spent. 
* A “sequence” is a consecutive set of hits where a given variable contains the same value (whether by being set, spread forward, or persisted). For example, prop1 “A” has two sequences: hits 1 & 2 and hit 6. Values on the last hit of the visit do not start a new sequence because the last hit has no time spent. Average time spent on site uses sequences in the denominator.

    * For the purposes of Time Spent only, props are “spread forward” from page hits to subsequent link hits as shown above for prop1 on hit 2. This allows the value that was set for prop1 on hit 1 (“A”) to accumulate time spent on hit 2. 
    * eVars accumulate Time Spent on any hit where the eVar is set or persisted. eVar persistence is defined by the eVar settings in Analytics Admin.

