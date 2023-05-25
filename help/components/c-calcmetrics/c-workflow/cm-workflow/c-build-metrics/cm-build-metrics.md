---
description: The Calculated Metrics Builder provides a canvas to drag and drop Dimensions, Metrics, Segments, and Functions to create custom metrics based on container hierarchy logic, rules, and operators. This integrated development tool lets you build and save simple calculated metrics or complex advanced calculated metrics.
title: Build metrics
feature: Calculated Metrics
exl-id: 12bb3734-e25d-4c67-8c62-e1226d9aef94
---
# Build metrics

Adobe Analytics provides a canvas to drag and drop dimensions, metrics, segments, and functions to create custom metrics based on container hierarchy logic, rules, and operators. This integrated development tool lets you build and save simple or complex calculated metrics.

You can begin creating a calculated metric in any of the follows ways:

* In Analysis Workspace, open a project, then select **[!UICONTROL Components]** > **[!UICONTROL Create metric]**.
* In Analysis Workspace, open a project, then select the **Plus** icon next to the [!UICONTROL **Metrics**] section in the left rail.
* In [!DNL Analytics], go to **[!UICONTROL Components]** > **[!UICONTROL Calculated metrics]**, then select **[!UICONTROL + Add]** at the top of the Calculated metrics page.

![](assets/cm_builder_ui.png)

## Available fields and areas {#section_9382AEEBA4244DD6A9F6C1DD3F6D076B}

<table id="table_60A82936321047D1A335331BF83B0972"> 
 <thead> 
  <tr> 
   <th colname="col2" class="entry"> Field </th> 
   <th colname="col3" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col2"> <span class="uicontrol"> Title </span> </td> 
   <td colname="col3"> <p>Naming the metric is mandatory. You cannot save the metric unless it is named. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <span class="uicontrol"> Description </span> </td> 
   <td colname="col3"> <p>Give it a user-friendly description to show what it's used for and to distinguish it from similar ones. </p> <p>The description also appears within a report. It's best NOT to put the formula into the description - instead, describe what this metric should and should not be used for. (The formula is generated as you build the metric, underneath the Summary heading. As a result, there is no need to add the formula to the description.) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <span class="uicontrol"> Format </span> </td> 
   <td colname="col3"> <p>Choices include Decimal, Time, Percent, and Currency. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <span class="uicontrol"> Decimal Places </span> </td> 
   <td colname="col3"> <p>Shows how many decimal places will be shown in the report. The maximum number of decimal places you can specify is 10. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <span class="uicontrol"> Show Upward Trend As... </span> </td> 
   <td colname="col3"> <p>This metric polarity setting shows whether Analytics should consider an upward trend in the metric as good (green) or bad (red). As a result, the report's graph will show as green or red when it's going up. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <span class="uicontrol"> Tags </span> </td> 
   <td colname="col3"> <p>Tagging is a good way to organize metrics. All users can create tags and apply one or more tags to a metric. However, you can see tags only for those segments that you own or that have been shared with you. What kinds of tags should you create? Here are some suggestions for useful tags: 
     <ul id="ul_9A6CE5F179424687A39F2D5C1A953258"> 
      <li id="li_A8815F2D8D284874AD701A7B103D82A3">Tags based on <b>team names</b>, such as Social Marketing, Mobile Marketing. </li> 
      <li id="li_A51A4515A541488E9D90296A955E9F4F"><b>Project</b> tags (analysis tags), such as Entry-page analysis. </li> 
      <li id="li_B4605470A7094026AC168420B64BBCC3"><b>Category</b> tags: Men's; geography. </li> 
      <li id="li_B6EAB0F2A96C41209C4EC97B9E64390B"><b>Workflow</b> tags: To be approved; Curated for (a specific business unit) </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <span class="uicontrol"> Summary </span> </td> 
   <td colname="col3"> <p>The <span class="uicontrol"> Summary </span> formula updates anytime you make a change to the metric definition. This formula also shows up in the metrics rail on the left when you hover over a metric and click the <img placement="inline"  src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_Info_18_N.svg" id="image_BDA0EAF89C19440CB02AE248BA3F968E" /> icon. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <span class="uicontrol"> Definition </span> </td> 
   <td colname="col3"> <p>This is where you drag in metrics/calculated metrics, segments, and/or functions to build the calculated metric. </p> <p> 
     <ul id="ul_B13401A266354DC594C6176025DB61CB"> 
      <li id="li_01776C32C7C5440AA1F847096CBED92B">If you drag in a calculated metric, it will expand its metric definition automatically. </li> 
      <li id="li_A483D352522E4572AB43042473053359">You can nest definitions with containers. However, unlike segment containers, these containers function like a math expression and determine the order of operations. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <span class="uicontrol"> Operator </span> </td> 
   <td colname="col3"> <p>Divided by ( <img placement="inline"  src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_Divide_18_N.svg" width="15" id="image_320D7363DE024BDEB21E44606C8B367F" width="25px" /> ) is the default operator, plus there are the +, -, and x operators. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <span class="uicontrol"> Preview </span> </td> 
   <td colname="col3"> <p>Provides a quick read on any possible errors. The preview covers the last 90 days. This is a way of initially gauging whether you have selected the right components for your metric. An unexpected result would mean you need to take a second look at the metric definition. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <span class="uicontrol"> Product Compatibility </span> </td> 
   <td colname="col3"> <p>Product compatibility shows you whether the metric is compatible with <a href="https://experienceleague.adobe.com/docs/analytics/analyze/reports-analytics/current-data.html"  > Current Data </a>, with Fully Processed Data, or only with Marketing Channel reports (first-touch allocation). <p>Note:  Current Data does not support all metrics. Metrics that contain segments or functions are not compatible with current data. <a href="/help/components/c-calcmetrics/cm-compatibility.md"  > More... </a> </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <span class="uicontrol"> Add </span> </td> 
   <td colname="col3"> <p>For all types of calculated metrics, you can add containers and static numbers to the definition. For advanced calculated metrics, you can also add segments and functions. </p> <p> 
     <ul id="ul_607C1B303F334062BC620317667DE490"> 
      <li id="li_53462789B8AF4F1AA9B45565D37CF22B">Containers function like a math expression and determine the order of operations. So anything in a container will get processed before the next operation. </li> 
      <li id="li_401A9E0D8B3B468990289DBF66A06F63">Dragging a segment onto a container segments everything in that container. (Advanced calculated metrics only) </li> 
      <li id="li_F191B200D7A944F9ADC0573A9A82A6DA">You can stack multiple segments in a container. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> Gear icon ( <span class="uicontrol"> Metric Type </span>, <span class="uicontrol"> Attribution </span>) </td> 
   <td colname="col3"> <p>Selecting the gear icon next to a metric lets you specify the <a href="/help/components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/m-metric-type-alloc.md"  > metric type and attribution models </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <span class="uicontrol"> + New </span> </td> 
   <td colname="col3"> <p>Lets you create a new component, such as a new segment (which takes you to the <a href="/help/components/segmentation/segmentation-workflow/seg-build.md"  > Segment Builder </a>.) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>Search Components </p> </td> 
   <td colname="col3"> <p>This search bar lets you search for dimensions, metrics, segments (advanced calculated metrics only), and functions (advanced calculated metrics only). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>List of Dimensions </p> </td> 
   <td colname="col3"> <p>Rather than leaving the Calculated Metric Builder in order to build a simple segment (in the Segment Builder), e.g. "Page = Homepage", you can drag in Page and select Homepage directly from the Calculated Metric Builder. </p> <p>This results in a much more streamlined workflow for creating segmented calculated metrics. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>List of Metrics </p> </td> 
   <td colname="col3"> <p>Metrics come in 3 categories: </p> 
    <ul id="ul_7BF50F4964EF45858FBA1634FBFA45CF"> 
     <li id="li_90F2312927A6499CA1CE04F8FFC912CF">Standard metrics ( <img placement="inline"  src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_Event_18_N.svg" id="image_65A80F54D73443E78542FE0B31CC3F20" />) </li> 
     <li id="li_A3F59083E79B4AC780D6F8CEDFFD20C9">Calculated metrics ( <img placement="inline"  src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_Calculator_18_N.svg" id="image_C5674AB9B9EB4DA9A56782D15822C319" />) </li> 
     <li id="li_8735E76637ED4C3F983731A66E04C93E">Metrics templates ( <img placement="inline"  src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_Folder_18_N.svg" id="image_D236601511CC4DD3828F223431E27E88" />) - at the bottom of the list. </li> 
    </ul> <p>When you hover over a metric, you can see the Info icon to the right of it: <img placement="inline"  src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_Info_18_N.svg" width="15px" id="image_5A65E772A68A4B94ACAD6552CCF21F5F" />. Clicking this icon gives you the following information: </p> 
    <ul id="ul_DF35DDB9FBFA40C8A93FA0F2286A0BBE"> 
     <li id="li_4215AA9BF93F4C8B941002A7A4D2F50B">The formula of how it is calculated. </li> 
     <li id="li_6A8E39EB6DCE4377B0B594B6D4FC0294">A preview trend of the metric. </li> 
     <li id="li_44C1595E4BE64ED69D1DB3BB6655ED55">An edit (pencil) icon <img placement="break" align="center"  src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_Edit_18_N.svg" width="15px" id="image_7D5B2F026A034118BE4DA81B9215A883" /> at the top right that will take you to the Calculated Metrics Builder where you can edit this calculated metric. </li> 
    </ul> <p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>List of Segments </p> </td> 
   <td colname="col3"> <p>(Advanced calculated metrics only) As an Admin, this list shows all segments created in your login company. If you are a non-Admin user, this list shows segments you own and those shared with you. <a href="https://experienceleague.adobe.com/docs/analytics/components/segmentation/segment-reference/seg-rights.html"  > More... </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>List of Functions </p> </td> 
   <td colname="col3"> <p>(Advanced calculated metrics only) Functions are divided into two lists: <a href="/help/components/c-calcmetrics/cm-reference/cm-functions.md"  > Basic </a> (used most often) and <a href="/help/components/c-calcmetrics/cm-reference/cm-adv-functions.md"  > Advanced </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>Report Suite selector </p> </td> 
   <td colname="col3"> <p>Lets you switch to a different report suite. </p> </td> 
  </tr> 
 </tbody> 
</table>
