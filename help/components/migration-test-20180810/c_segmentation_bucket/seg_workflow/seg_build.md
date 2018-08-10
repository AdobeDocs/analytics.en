---
description: The Segment Builder provides a canvas to drag and drop Metric Dimensions, Segments, and Events to segment visitors based on container hierarchy logic, rules, and operators. This integrated development tool lets you build and save simple or complex segments that identify visitor attributes and actions across visits and page hits.
seo-description: The Segment Builder provides a canvas to drag and drop Metric Dimensions, Segments, and Events to segment visitors based on container hierarchy logic, rules, and operators. This integrated development tool lets you build and save simple or complex segments that identify visitor attributes and actions across visits and page hits.
seo-title: Building Segments
solution: Analytics
title: Building Segments
topic: Segments
uuid: ced21344-a128-4aa3-9e19-a2e72d6cef17
index: y
internal: n
snippet: y
translate: y
---

# Building Segments


* [ Segment Builder User Interface ](seg_build.md#concept_643F2DF74C544796B58F4656ABC5F726)
* [ Build Segments ](seg_build.md#section_050E3343533E45C3923242398E0E0213)
* [ Build and Nest Containers ](seg_build.md#section_1C38F15703B44474B0718CEF06639EFD)
* [ Use Date Ranges in Segments ](seg_build.md#concept_252A83D43B6F4A4EBAB55F08AB2A1ACE)
* [ Stack Segments ](seg_build.md#concept_40C299B60B354E10B344702EA3138B34)
* [ Use Segment Templates ](seg_build.md#concept_8C017A4A04404A0BAAD710569FAAEFCB)
* [ Create Segments from a Fallout Report ](seg_build.md#concept_4D671BE863A64A22B8EE702E333C0470)
* [ Example: Campaign Visitors Segment ](seg_build.md#concept_61AC6115097B4EB3AEFE8CE98F38315D)
* [ Ad Hoc Analysis Features ](seg_build.md#section_0C6917B396444E91A54370FFB4AE74A5)
* [ Build Segments in Ad Hoc Analysis ](seg_build.md#section_E440630183D64999BA2369D1B8048AA6)
There are several ways to access the Segment Builder: 



<table id="table_DF88713820B0448A85707C665A1DD00A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Analytics Tool </th> 
   <th colname="col2" class="entry"> Path </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Analytics top navigation </p> </td> 
   <td colname="col2"> <p> 
     <ignoretag> 
      <span class="uicontrol"> Analytics </span>  &gt; 
      <span class="uicontrol"> Components </span>  &gt; 
      <span class="uicontrol"> Segments </span> 
     </ignoretag> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Analysis Workspace </p> </td> 
   <td colname="col2"> <p> 
     <ignoretag> 
      <span class="uicontrol"> Analytics </span>  &gt; 
      <span class="uicontrol"> Workspace </span> 
     </ignoretag>, open a project and click 
     <ignoretag> 
      <span class="uicontrol"> + New </span>  &gt; 
      <span class="uicontrol"> Create Segment </span> 
     </ignoretag> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Reports &amp;amp; Analytics </p> </td> 
   <td colname="col2"> <p> 
     <ignoretag> 
      <span class="uicontrol"> Analytics </span>  &gt; 
      <span class="uicontrol"> Reports </span> 
     </ignoretag>, open an existing report and click the Segments icon <img placement="inline" href="graphics/segment_icon.png" width="30px" id="image_BDB37383C57D41A48CD50CA8BB9415EC" /> in the left navigation, then click <span class="uicontrol"> Add </span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Ad Hoc Analysis </p> </td> 
   <td colname="col2"> <p> <a href="seg_build.xml#concept_4D671BE863A64A22B8EE702E333C0470/section_E440630183D64999BA2369D1B8048AA6" format="dita" scope="local"> Build Segments in Ad Hoc Analysis </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Report Builder </p> </td> 
   <td colname="col2"> <p> <a href="https://marketing.adobe.com/resources/help/en_US/arb/segmentation.html" format="html" scope="external"> Add or edit segments in Report Builder </a> </p> </td> 
  </tr> 
 </tbody> 
</table>


## Web UI Features {#section_F61C4268A5974C788629399ADE1E6E7C}

The [!UICONTROL  Segment Builder] lets you build and edit segments in the web UI (or in a [ Java UI in Ad Hoc Analysis ](seg_workflow.md#section_E440630183D64999BA2369D1B8048AA6)). You can add rule definitions and containers to refine your segments, stack segments, and nest them to refine them. You can also validate how many page views, visits, and unique visitors result from your current segment definition. Then save the segment for future needs. 

Access the Segment Builder by 

* Displaying an existing report and clicking the Segments icon  ![](graphics/segment_icon.png) in the left navigation. In the segment rail that displays, click ** [!UICONTROL  Add] **.
* From within the Segment Manager, clicking ** [!UICONTROL  + Add] **.
* Clicking an existing segment title in the Segment Manager to edit the segment in Segment Builder.
![](graphics/segment_builder_ui.png) 

<table id="table_FE6396F0BFDF4B7A9695CBD614F65654"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> </th> 
   <th colname="col2" align="center" class="entry"> Feature </th> 
   <th colname="col3" align="center" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1" valign="top" align="center"> <b>1</b> </td> 
   <td colname="col2" valign="top"> <p> <span class="wintitle"> Title </span> field </p> </td> 
   <td colname="col3"> <p>Let you name or rename the segment. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1" valign="top" align="center"> <b>2</b> </td> 
   <td colname="col2" valign="top"> <p> <span class="wintitle"> Description </span> field </p> </td> 
   <td colname="col3"> <p>This is where you provide a description for the segment. You must provide a description if you want to share the segment. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1" valign="top" align="center"> <b>3</b> </td> 
   <td colname="col2" valign="top"> <p>Tagging interface </p> </td> 
   <td colname="col3"> <p>Lets you <a href="seg_workflow.xml#concept_CD892CEB326C4986A1B67487052DBA50" format="dita" scope="local"> tag the segment </a>you are creating by picking from a list of existing tags or creating a new tag. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1" valign="top" align="center"> <b>4</b> </td> 
   <td colname="col2" valign="top"> <p> <span class="wintitle"> Definitions </span> canvas </p> </td> 
   <td colname="col3"> <p>This is where you <a href="seg_workflow.xml#concept_BD4C17B01C5B4E378D0C14C852D055D4" format="dita" scope="local"> build and configure segments </a>, add rules, and nest and sequence containers. Allows you to provide a description for the new segment by selecting the container and dragging and dropping dimensions, segments, or metrics into the definition. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1" valign="top" align="center"> <b>5</b> </td> 
   <td colname="col2" valign="top"> <p> <span class="wintitle"> Top Container </span> selector </p> </td> 
   <td colname="col3"> <p>Lets you select the top-level <a href="seg_overview.xml#concept_A38E7000056547399E346559D85E2551" format="dita" scope="local"> container </a> ( <span class="wintitle"> Visitor </span>, <span class="wintitle"> Visit </span>, <span class="wintitle"> Hit </span>). The default top-level container is the Hit container. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1" valign="top" align="center"> <b>6</b> </td> 
   <td colname="col2" valign="top"> <p>Options (gear) icon </p> </td> 
   <td colname="col3"> 
    <ul id="ul_D637774239584D20AD1CD028E1F8BE12"> 
     <li id="li_3C790B7C8E714B34917E0F6BFF073404"> <span class="wintitle"> + Add container </span>: Lets you add a new container (below the top-level container) to the segment definition. </li> 
     <li id="li_E96D3E38E2F0407389AC51ADA1131498"> <span class="wintitle"> + Add container from selection </span>: Lets you create a new container from the element/s that you (multi-) selected in the Definitions field. </li> 
     <li id="li_D16A38564F484425812F19727088B3FC"> <span class="wintitle"> Exclude </span>: Lets you define the segment by excluding one or more dimensions, segments, or metrics. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1" valign="top" align="center"> <b>7</b> </td> 
   <td colname="col2" valign="top"> <p>Dimension (orange sidebar) </p> </td> 
   <td colname="col3"> <p>Dimension that was dragged and dropped from the Dimensions list. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1" valign="top" align="center"> <b>8</b> </td> 
   <td colname="col2" valign="top"> <p> <span class="wintitle"> Comparison operator </span> </p> </td> 
   <td colname="col3"> <p>You can compare and constrain values using selected operators. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1" valign="top" align="center"> <b>9</b> </td> 
   <td colname="col2" valign="top"> <p>Value </p> </td> 
   <td colname="col3"> <p>The value you entered or selected for the dimension or segment or metric. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1" valign="top" align="center"> <b>10</b> </td> 
   <td colname="col2" valign="top"> <p> <span class="wintitle"> And/Or/Then </span> operators </p> </td> 
   <td colname="col3"> <p>Assigns the <span class="wintitle"> AND/OR/THEN </span> operators between containers or rules. The THEN operator lets you <a href="seg_sequential_build.xml#concept_83AEC78CD25F442EBEE364856A889560" format="dita" scope="local"> define sequential segments </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1" valign="top" align="center"> <b>11</b> </td> 
   <td colname="col2" valign="top"> <p>Metric (green sidebar) </p> </td> 
   <td colname="col3"> <p>Metric that was dragged and dropped from the Metrics list. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1" valign="top" align="center"> <b>12</b> </td> 
   <td colname="col2" valign="top"> <p> <span class="wintitle"> Comparison operator </span> </p> </td> 
   <td colname="col3"> <p>You can compare and constrain values using selected operators </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1" valign="top" align="center"> <b>13</b> </td> 
   <td colname="col2" valign="top"> <p>Value </p> </td> 
   <td colname="col3"> <p>The value you entered or selected for the dimension or segment or metric. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1" valign="top" align="center"> <b>14</b> </td> 
   <td colname="col2" valign="top"> <p>X (Delete) </p> </td> 
   <td colname="col3"> <p>Lets you delete this part of the segment definition. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1" valign="top" align="center"> <b>15</b> </td> 
   <td colname="col2" valign="top"> <p> <span class="wintitle"> Save </span> or <span class="wintitle"> Cancel </span> </p> </td> 
   <td colname="col3"> <p>Saves or cancels the segment. After clicking <span class="uicontrol"> Save </span>, you are taken to the Segment Manager where you can manage the segment. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1" valign="top" align="center"> <b>16</b> </td> 
   <td colname="col2" valign="top"> <p>Search bar </p> </td> 
   <td colname="col3"> <p>Searches the list of dimensions, segments, or metrics. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1" valign="top" align="center"> <b>17</b> </td> 
   <td colname="col2" valign="top"> <p>List of dimensions </p> </td> 
   <td colname="col3"> <p>Click the header to expand. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1" valign="top" align="center"> <b>18</b> </td> 
   <td colname="col2" valign="top"> <p>List of metrics </p> </td> 
   <td colname="col3"> <p>Click the header to expand. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1" valign="top" align="center"> <b>19</b> </td> 
   <td colname="col2" valign="top"> <p>List of segments </p> </td> 
   <td colname="col3"> <p>Click the header to expand. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1" valign="top" align="center"> <b>20</b> </td> 
   <td colname="col2" valign="top"> <p>Report suite selector </p> </td> 
   <td colname="col3"> <p>Lets you select the reports suite that this segment will be saved under. You can still utilize the segment in all report suites. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1" valign="top" align="center"> <b>21</b> </td> 
   <td colname="col2" valign="top"> <p>Segment Preview </p> </td> 
   <td colname="col3"> <p>Lets you preview the key metrics to see whether you have a valid segment and how broad the segment is. Represents the breakdown of the data set you can expect to see if you apply this segment. Shows 3 concentric circles and a list to show the number and percentage of matches for <span class="wintitle"> Hits </span>, <span class="wintitle"> Visits </span>, and <span class="wintitle"> Visitors </span> for a segment run against a data set. This chart is updated immediately after you create or make changes to your segment definition. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1" valign="top" align="center"> <b>22</b> </td> 
   <td colname="col2" valign="top"> <p> <span class="wintitle"> Product Compatibility </span> </p> </td> 
   <td colname="col3"> <p>Provides a list of which Adobe Analytics products (Analysis Workspace, Reports &amp; Analytics, Ad Hoc Analysis, Data Warehouse) with which the segment you created is compatible. Most segments are compatible with all products. However, not all operators and dimensions are compatible with all Analytics products, especially <a href="seg_compatibility.xml#concept_7A2CC00352274A75ACD4949CA3C144D4" format="dita" scope="local"> Data Warehouse </a>. This chart is updated immediately after you make changes to your segment definition. </p> <p>Note:  Segments with embedded date ranges continue to operate differently in Analysis Workspace versus Reports &amp;amp; Analytics: In Workspace, a segment with an embedded date range overrides the panel date range. By contrast, Reports &amp;amp; Analytics gives you the intersection of the report date range and the segment's embedded date range. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1" valign="top" align="center"> (not shown in screen shot) </td> 
   <td colname="col2" valign="top"> <p> <span class="wintitle"> Publish to Experience Cloud (for &amp;lt;report suite name&amp;gt;) </span> </p> </td> 
   <td colname="col3"> <p>This option appears only if the report suite that you are saving this segment to is <a href="seg_workflow.xml#concept_1E9FC92437D748C392546542B6511D01" format="dita" scope="local"> enabled for the Experience Cloud </a>. By publishing a segment to the Experience Cloud, you can use the segment for marketing activity in the Audience library, Target, and Audience Manager. A segment title and description are required. </p> <p>Note:  In Analytics, you can edit or delete a published segment. If the segment is in use, a warning message is issued when you edit a segment. You cannot delete a published segment that is in use by Adobe Target. </p> <p style="text-align: center;"> <img placement="break" align="center" href="graphics/segment_publish_to_mac copy.png" id="image_389C00CDF56C4CDA960C7FEF8816CFD7" /> </p> <p> <p type="important">Note:  You must limit the number of audiences shared from Analytics to 20 to avoid additional processing delays. Audiences shared to the Experience Cloud from Analytics cannot exceed 20 million unique members. Also, due to caching, deleted report suites in Analytics require 12 hours before the deletion is shown in the Experience Cloud. </p> </p> <p> <p type="important">Note:  Once a visitor qualifies for the audience shared from Analytics, there is a 24 - 48 hour delay before that information is actionable in Target, Media Optimizer, and Campaign. </p> </p> </td> 
  </tr> 
 </tbody> 
</table>


## Build Segments {#section_050E3343533E45C3923242398E0E0213}


1. Simply drag a Dimension, Segment, or Metric Event from the left pane to the [!UICONTROL  Definitions] field. 

   ![](graphics/drag_n_drop_dimension.png) 

   The default top-level [!UICONTROL  Hit] container is shown after dragging an element to [!UICONTROL  Definitions]. You can change the container type to Visit or Visitor from the ** [!UICONTROL  Show] ** drop-down menu. 

1. Set the [ operator ](seg_reference.md#concept_A010909595454633B4FDC54C97A9CFFA) from the drop-down menu.
1. Enter or select a value for the item selected.
1. Add additional containers if needed, using ** [!UICONTROL  And] **, ** [!UICONTROL  Or] **, or ** [!UICONTROL  Then] ** rules.
1. After placing the containers and setting the rules, see the results of the segment in the validation chart at the top right. The validator indicates the percentage and absolute number of page views, visits, and unique visitors that match the segment you created.
1. Under ** [!UICONTROL  Tags] **, [ tag ](seg_tag.md#concept_CD892CEB326C4986A1B67487052DBA50) the container by selecting an existing tag or creating a new one.
1. Click ** [!UICONTROL  Save] ** to save the segment.
You are now taken to the [ Segment Manager ](seg_manage.md#concept_7A2E019317864065B7C641DC3315928F), where you can tag, share, and manage your segment in multiple ways. 

## Build and Nest Containers {#section_1C38F15703B44474B0718CEF06639EFD}

You can[ build a framework of containers ](seg_overview.md#concept_82653C7E29FE49F5A4B5E5E93B0A6399) and then place logic rules and operators between. 
1. Click ** [!UICONTROL  Options &amp;gt; Add Container] **. ![](graphics/add_container.png) 

   A new [!UICONTROL  Hit] container opens without a [!UICONTROL  Hit] (Page View) identified. 

   ![](graphics/new_container.png) 

1. Change the container type as needed.
1. Drag a Dimension, Segment, or Event from the left pane to the container.
1. Continue to add new containers from the top-level ** [!UICONTROL  Options] ** > ** [!UICONTROL  Add container] ** button at the top of the definition, or add containers from within a container to nest logic. **OR** 

   Select one or more rules and then click ** [!UICONTROL  Options] ** > ** [!UICONTROL  Add container from selection] **. This turns your selection into a separate container. 

For example, you can easily build a segment that includes “everyone who has made a purchase over the past 60 days”. 

You create a Visit container and within it, add the [!UICONTROL  Last 60 days] time range and the metric [!UICONTROL  Orders is greater than or equal to 1], with an AND operator: 

![](graphics/date-ranges.png) 
For example, stacking a "mobile phone users" segment and a "US geography" segment would return data only for mobile phone users in the US. 

Think of these segments as building blocks or modules that you can include in a segment library, for users to use as they see fit. That way, you can dramatically reduce the number of segments needed. For example, assume you have 40 segments: 
* 20 for mobile phone users in different countries (US_mobile, Germany_mobile, France_mobile, Brazil_mobile, etc.)
* 20 for tablet users in different countries (US_tablet, Germany_tablet, France_tablet, Brazil_tablet, etc.)
By using segment stacking, you can reduce your segment count to 22 and stack them as needed. You would need to create these segments:
* one segment for mobile users
* one segment for tablet users
* 20 segments for the different geographies

>[!NOTE]
>
>When stacking two segments, they are by default joined by an AND statement. This cannot be changed to an OR statement.



1. Go to the Segment Builder.
1. Provide a title and description for the segment.
1. Click ** [!UICONTROL  Show Segments] ** to bring up the list of segments in the left navigation.
1. Drag and drop the segments you want to stack to the segment definition canvas. Here is an example of a segment that stacks the existing segments "Visits from Tablets" and "US Geo": ![](graphics/seg_stack2.png) 

1. Save the segment.
In the Segment Manager, click ** [!UICONTROL  Add] **, which takes you to the Segment Builder. Now click the Segments icon  ![](graphics/segment_icon.png) to bring up the segment rail. The segment templates appear at the bottom of the segment list. They are distinguishable by a folder icon to the left of the template name: 

![](graphics/seg_template.png) 

You can drag these templates into the Definitions canvas and use them as they have been defined, or modify them. 

<table id="table_98B87D807E9344C9BEBF072C65D87B1B"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Template Name </th> 
   <th colname="col2" class="entry"> Definition </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Abandon Cart </td> 
   <td colname="col2"> View data for visitors that added items to their carts but did not order anything. In the Segment Definition, the container is Visit. The rule for this sequential segment is <p> Cart Additions is not null </p> <p>Then </p> <p>Orders equals 0. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> First Time Visits </td> 
   <td colname="col2"> View data for visitors that have visited a maximum of one [1] times. In the Segment Definition, the container is Visit. The rule is <p>Visit Number equals 1. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Non-Purchasers </td> 
   <td colname="col2"> View data for visitors that have not participated in an order event. In the Segment Definition, the container is Visitor. This segment uses the Exclude logic. The rule is <p>Orders is not null. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Non-Single Page Visit (Non-Bounces) </td> 
   <td colname="col2"> View data for visitors that visited more than once. In the Segment Definition, the container is Visitor. This segment uses the Exclude logic. The rule is <p>Single Access is not null. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Paid Search </td> 
   <td colname="col2"> View data from visitors originating from a paid search. In the Segment Definition, the container is Visit. The rule is <p>Paid Search equals 1. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Purchasers </td> 
   <td colname="col2"> View data for visitors that have participated in an order event. In the Segment Definition, the container is Visitor. The rule is <p>Orders is not null. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Return Visits </td> 
   <td colname="col2"> View data from visitors that have visited at least once. In the Segment Definition, the container is Visit. The rule is <p>Visit Number is greater than 1. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Single Page Visits </td> 
   <td colname="col2"> View data from visits in which you see a single page value, even though you may submit multiple page views during that visit. Single-page visits with exit link events are included in the segment. In the Segment Definition, the container is Visit. The rule is <p>Single Page Visits equals 1. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Viewed Product Didn't Add to Cart </td> 
   <td colname="col2"> View data for visitors that viewed products but had no cart additions. In the Segment Definition, the container is Visit. The rule for this sequential segment is <p>Product Views is not null </p> <p>Then </p> <p> Cart Additions equals 0. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Visits from Campaign </td> 
   <td colname="col2"> View data from visitors referred by campaigns. In the Segment Definition, the container is Visit. The rule is <p>Tracking Code is not null. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Visits from Mobile Devices </td> 
   <td colname="col2"> View data from visitors using mobile devices. In the Segment Definition, the container is Visit. The rule is <p>Mobile Device is not null. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Visits from Natural Search </td> 
   <td colname="col2"> View data from visitors not originating from a paid search. In the Segment Definition, the container is Visit. The rule is <p>Paid Search equals 0. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Visits from Non-Mobile Device </td> 
   <td colname="col2"> View data from visitors not using mobile devices. In the Segment Definition, the container is Visit. This segment uses the Exclude logic. The rule is <p>Mobile Device Type equals Mobile Phone </p> <p>Or </p> <p>Mobile Device Type equals Tablet. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Visits from Phones </td> 
   <td colname="col2"> View data from visitors using phones. In the Segment Definition, the container is Visit. The rule is <p>Device Type equals Mobile Phone. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Visits from Search Engines </td> 
   <td colname="col2"> View data from visitors referred by search engines. In the Segment Definition, the container is Visit. The rule is <p>Referrer Type equals Search Engines. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Visits from Social Sites </td> 
   <td colname="col2"> View data from visitors referred by social sites. In the Segment Definition, the container is Visit. The rule is <p>Referrer Type equals Social Networks. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Visits from Tablets </td> 
   <td colname="col2"> View data from visitors using tablets. In the Segment Definition, the container is Visit. The rule is <p>Device Type equals Tablet. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Visits with Visitor ID Cookie </td> 
   <td colname="col2"> View data from visitors to your site, where a persistent cookie is required. In the Segment Definition, the container is Visit. The rule is <p>Persistent Cookie equals 1. </p> </td> 
  </tr> 
 </tbody> 
</table>

Many customers want to see metrics from visitors who responded to specific campaigns. Creating a campaign visitors segment is an easy way of getting this data. 

Building this segment in the Segment Builder means that from a top-level Visit container, you drag in a campaign dimension, in this case Campaign Name: 

![](graphics/seg_campaign_visitor.png) 

(Optional) You can also apply a Campaigns tag to this segment, if you wish to easily filter on all your campaign-related segments. 
For a more detailed example with screenshots, go [ here ](https://marketing.adobe.com/resources/help/en_US/analytics/analysis-workspace/fallout_flow.html). 

1. In Analysis Workspace, create a Fallout report that includes the dimension you want to use for your segment.
1. Right-click the dimension in the Fallout report and select ** [!UICONTROL  Create segment from touchpoint] **.
1. In the [!UICONTROL  Segment Builder], name the segment, enter a description, change rules, add to logic, and then save.

## Ad Hoc Analysis Features {#section_0C6917B396444E91A54370FFB4AE74A5}

The [!UICONTROL  Segment Builder] for Ad Hoc Analysis includes features built on Java libraries but contains the same features as the web console. Like the web console, it allows you to drop elements from the left panes to the [!UICONTROL  Segment canvas] and then run against the data set. 

![](graphics/UI_overview.png) 

|   | Feature  | Description  |
|---|---|---|
|  ** 1 ** | [!UICONTROL  Dimensions] pane  | Lists dimensions.  |
|  ** 2 ** | Dimension element tabs  | Drills into Dimension attributes and displays Dimension element values, such as a list of Pages, Languages, or Campaigns. For example, if you select the [!UICONTROL  Page] in the [!UICONTROL  Dimension] pane, a [!UICONTROL  Pages] pane will appear with a list of web pages for your site.  |
|  ** 3 ** | [!UICONTROL  Search] box  | Searches across the pane.  |
|  ** 4 ** | [!UICONTROL  Events] tab  | Lists metric events to apply to the segment.  |
|  ** 5 ** | [!UICONTROL  Segments] tab  | Lists pre-configured segments.  |
|  **6** | Templates tab  | Lists pre-configured segments to build from.  |
|  ** 7** | [!UICONTROL  Segment Title]  | Allows you to name or rename the segment.  |
|  ** 8** | [!UICONTROL  Segment Description]  | Allows you to provide a title for the new segment.  |
|  ** 9** | [!UICONTROL  Add Container] menu  | Lets you add a new container to the [!UICONTROL  Segment canvas].  |
|  ** 10** | [!UICONTROL  Move handle]  | Highlights a section and lets you reposition it within the [!UICONTROL  Segment canvas].  |
|  ** 11 ** | [!UICONTROL  And/Or] menu  | Assigns the [!UICONTROL  AND/OR] operator between containers.  |
|  ** 12** | [!UICONTROL  Segment Canvas]  | The work area is where you build and configure segments, add rules, and nest and sequence containers.  |
|  ** 13 ** | [!UICONTROL  Execute] button  | Click the [!UICONTROL  Run] icon  ![](graphics/update icon.png) to run the segment against the data set. If invalid, the button will not be active and the tool tip will define the error.  |
|  ** 14** | [!UICONTROL  Report visuals]  | Presents a pie chart to show number and percentage of [!UICONTROL  Page Views], [!UICONTROL  Visits], and [!UICONTROL  Visitors] for a segment run against a data set.  |
|  ** 15 ** | [!UICONTROL  Save] button  | Saves the segment for reuse or lets you [!UICONTROL  Save As] from the drop-down menu.  |


## Build Segments in Ad Hoc Analysis {#section_E440630183D64999BA2369D1B8048AA6}

See [ About Segments ](seg_overview.md#concept_82653C7E29FE49F5A4B5E5E93B0A6399) for additional information. 

1. Open the Segment Builder from the Segments panel in the left sidebar. Click the wrench icon and select ** [!UICONTROL  New Segment] ** from the menu. 

   ![](graphics/seg_new.png) 

   The Segment Builder will open. 

1. Drag entities from the Dimension, Dimension element, Event, Templates, or Segment panels from the left sidebar to the Segment Canvas. ![](graphics/seg_drag.png) 

1. Enter a value for the dimension.  ![](graphics/seg_value.png) Enter a value or select value by clicking the magnifying glass icon. A menu will open to select possible value for the dimension. 

1. Set the operator from the list of [ operators ](seg_reference.md#concept_A010909595454633B4FDC54C97A9CFFA). ![](graphics/seg_AND.png) 

1. Resolve any errors identified by the [!UICONTROL  Error] icon  ![](graphics/error_icon.png). Mousing over the [!UICONTROL  Error] icon brings up a message identifying the error. 

1. After placing the containers and setting the rules, click the [!UICONTROL  Run] icon  ![](graphics/update icon.png) to run the segment against the selected dataset.
1. View a preview of the results in applying the segment at the bottom of the pane. ![](graphics/seg_preview.png) 

1. Click the ** [!UICONTROL  Save] ** button to save the segment in the [!UICONTROL  Segments] pane for future use.
