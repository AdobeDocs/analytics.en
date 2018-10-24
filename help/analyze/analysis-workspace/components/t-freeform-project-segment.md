---
description: null
seo-description: null
seo-title: Segments
title: Segments
uuid: ef7a750f-88a3-4275-9d79-c99e11a9f3f1
index: y
internal: n
snippet: y
---

# Segments

## Segments {#topic_DC2917A2E8FD4B62816572F3F6EDA58A}

* [Segment Rail](../../../analyze/analysis-workspace/components/t-freeform-project-segment.md#section_3B07D458C43E42FDAF242BB3ACAF3E90) 
* [Create Segments](../../../analyze/analysis-workspace/components/t-freeform-project-segment.md#section_693CFADA668B4542B982446C2B4CF0F5) 
* [Other Methods for Applying Segments](../../../analyze/analysis-workspace/components/t-freeform-project-segment.md#section_10FF2E309BA84618990EA5B473015894)

## Segment rail {#section_3B07D458C43E42FDAF242BB3ACAF3E90}

The segment rail under the Components menu shows segments as well as segment templates, as signified by these icons:

![](assets/segment_icons.png)

## Create segments {#section_693CFADA668B4542B982446C2B4CF0F5}

You can create instant segments by dropping any component type (dimension, dimension item, event, metric, segment, segment template, date range) into the segment drop zone at the top of a panel.

Component types are auto-converted into segments. Alternatively, you can click the “+" sign in the Add Segment drop box.

Keep in mind that:

* You **cannot** drop the following component types into the segment zone: calculated metrics and dimensions/metrics from which you cannot build segments. 
* For full dimensions and events, Analysis Workspace creates "exists" hit segments. Examples: "Hit where eVar1 exists" or "hit where event1 exists". 
* If "unspecified" or "none" is dropped in the segment drop zone, it is automatically converted to a "does not exist" segment so that it is treated correctly in segmentation.

![](assets/segment-dropzone.png)

>[!NOTE]
>
>Segments created this way are internal to the project.

You can choose to make these segments public (global) by following these steps:

1. Hover over the segment in the drop zone and click the "i" icon. 
1. In the information panel that displays, click **[!UICONTROL Make public]**.

   ![](assets/segment-info.png)

## Other methods for applying segments {#section_10FF2E309BA84618990EA5B473015894}

Several other methods exist for applying segments to a freeform project. 

<table id="table_45B3839D70674430AF3AC5AA3134F825"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Action </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Create segment from selection </p> </td> 
   <td colname="col2"> <p>Create an inline segment. Select rows, right-click the selection, then create an inline segment. This segment applies only to the open project and is not saved as an Analytics segment. </p> <p> 
     <ol id="ol_1D1E661387354EBF992CC150915F642E"> 
      <li id="li_B96666FD426F4AEE8EAB61B2C00A07FB">Select rows </li> 
      <li id="li_C2245B3EA81F4FAC88A33647922535AF">Right-click the selection </li> 
      <li id="li_AB4F8988B9A84920ABA06A91094625F6">Click <span class="uicontrol"> Create segment from selection</span>. </li> 
     </ol> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="uicontrol"> Components</span> &gt; <span class="uicontrol"> New Segment</span> </td> 
   <td colname="col2"> <p>Displays the <span class="wintitle"> Segment Builder</span>. See <a href="https://marketing.adobe.com/resources/help/en_US/analytics/?f=segment/seg_build" format="https" scope="external"> Building Segments</a> for more information about segmentation. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="ignoretag"><span class="uicontrol"> Share</span> &gt; <span class="uicontrol"> Share Project </span></span>or </p> <p> <span class="ignoretag"><span class="uicontrol"> Share</span> &gt; <span class="uicontrol"> Curate Project Data </span></span> </p> </td> 
   <td colname="col2"> <p>In <a href="../../../analyze/analysis-workspace/curate-share/curate.md#concept_4A9726927E7C44AFA260E2BB2721AFC6" format="dita" scope="local"> Curate &amp; Share</a>, segments that you apply to the project are available in shared analysis for the recipient. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Use Segments as Dimensions </p> </td> 
   <td colname="col2"> <p>Video: <a href="https://www.youtube.com/watch?v=WmSdReKTWto&amp;list=PL2tCx83mn7GuNnQdYGOtlyCu0V5mEZ8sS&amp;index=39" format="https" scope="external"> Using Segments as Dimensions in Analysis Workspace</a> </p> </td> 
  </tr> 
 </tbody> 
</table>

