---
description: The Activity Map Setting Panel lets you modify the settings and properties for all types of overlay visualizations.
seo-description: The Activity Map Setting Panel lets you modify the settings and properties for all types of overlay visualizations.
seo-title: Configure Activity Map settings
solution: Analytics
title: Configure Activity Map settings
topic: Activity map
uuid: 84ff9b45-2773-4382-8477-98090928f5cd
index: y
internal: n
snippet: y
translate: y
---

# Configure Activity Map settings

Access the Activity Map Settings panel accessed by clicking the gear icon on the Activity Map toolbar. 

The Settings panel displays different content based on the selected application mode. The Other tab contains general settings. 

|  Standard  | ** [!UICONTROL  Gradient] ** or ** [!UICONTROL  Bubble] ** overlays  |
|---|---|
|  Live  | ** [!UICONTROL  Gainers &amp;amp; Losers] **, ** [!UICONTROL  Gradient] **, ** [!UICONTROL  Bubble] ** overlays  |
|  Other  | Report Suite selection and Language selection  |


## Settings for standard mode overlay {#section_24DB95376E1A448494ECF3F57743FC19}

![](../assets/settings_standard.png) 

<table id="table_0244107DE6D142F2A1DA4882E0ED9826"> 
 <thead> 
  <tr> 
   <th colname="col2" class="entry"> Settings </th> 
   <th colname="col3" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col2"> <span class="uicontrol"> Label Overlays With </span> </td> 
   <td colname="col3"> 
    <ul id="ul_13AD02789F2D4904A35215A8FA230F3E"> 
     <li id="li_8DB71636D2074C69B0D94D3FB0CAFE28"> <b>No Label</b>: only applicable for the Gradient overlay. In this case the color of the overlay will convey a sense for the ranking of the link </li> 
     <li id="li_39C98D7EA9514C1D8731B9D21C0E73A6"> <b>Value</b>: the raw metric total for that link </li> 
     <li id="li_A5F583E45BCD4F2399398F9DCC7FE382"> <b>Percent</b>: percentage of the metric for this link on the total metric for the page. </li> 
     <li id="li_E4BF7D3B863E4B6C8E737CF29ADA9D67"> <b>Rank</b>: rank of this link across all links present in the rendered page </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <span class="uicontrol"> Label Font Size </span> </td> 
   <td colname="col3"> Lets you increase/decrease the overlay label font size, using a slider, for better readability. </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <span class="uicontrol"> Display </span> </td> 
   <td colname="col3"> Select <span class="uicontrol"> Top </span>, <span class="uicontrol"> Bottom </span>, or <span class="uicontrol"> All Links </span> to display in the overlay. If you select Top or Bottom, you must also select the number of links to display. </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <span class="uicontrol"> Hide overlays for links that received no hits. </span> </td> 
   <td colname="col3"> This checkbox lets you hide overlays for links that received no hits, to reduce clutter in the interface. </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <span class="uicontrol"> Gradient Color / Bubble Color </span> </td> 
   <td colname="col3"> Select among a range of colors to display overlay link rankings for <span class="uicontrol"> Gradient </span> or <span class="uicontrol"> Bubble </span> overlay visualizations. </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <span class="uicontrol"> Color Gradient Based On </span> </td> 
   <td colname="col3"> 
    <ul id="ul_1B5C2A44A9EB465D8B8E9AD91AF79D69"> 
     <li id="li_C983CB68B90B492BB0774254292B5961"> <span class="uicontrol"> Top 30 Rankings </span>: Color intensity is normalized for the top 30 values. </li> 
     <li id="li_1E83431C8C734AB0BC82B5A66AED1189"> <span class="uicontrol"> Absolute Metric Value </span>: Color intensity is a function of the absolute metric value. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <span class="uicontrol"> Gradient Transparency </span> </td> 
   <td colname="col3"> Select the level of transparency for the Gradient overlays. <p>This setting does not affect the Bubble overlays. </p> </td> 
  </tr> 
 </tbody> 
</table>


## Settings for live mode overlays {#section_D30F6E62FB5D404090B588F396A460AF}

![](../assets/settings_live.png) 

|  Settings  | Description  |
|---|---|
|  ** [!UICONTROL  Display Top] ** | Select number of links to display (or all) and the ** [!UICONTROL  Gainers] ** or ** [!UICONTROL  Losers] ** (or both) to display as overlays.  |
|  ** [!UICONTROL  Exclude bottom (%)] ** | Select to eliminate Gainers-Losers links with sparse data. Filter out the bottom percentage of link changes to view only the links with enough data to show relevant gains or losses. The percentage is computed based on the number of links on that page. For example, filtering out the bottom 10% of a list of 200 links would filter out the last 20 links.  |
|  ** [!UICONTROL  Auto Update Data] ** | Lets you decide whether the Analytics data shown in the interface should automatically update when a new period is computed, or not.  |
|  ** [!UICONTROL  Auto Update Period] ** | When checked, refreshes the web page with each new data retrieval so the links in the page can be more closely synced with the collected data.  |


## Other settings {#section_697A12F099494D699A4BF498598178C5}

![](../assets/settings_other.png) 

<table id="table_0F560236F8844FA0928CBB9C50D5ABEF"> 
 <tbody> 
  <tr> 
   <td colname="col1"> Report Suite </td> 
   <td colname="col2"> <p>The list of report suites that are accessible to you is no longer limited to the report suites defined in the web page tag. You can now substitute the selected report suite (corresponding to one of the tags on the page) with another report suite. This new report suite does not need to be linked to a tag on the page. If you change the selected report suite in the Activity Map Settings, the <span class="uicontrol"> Save </span> process will cause all affected Analytics reports to be refreshed. </p> <p> <p type="important">Note:  Virtual Report Suites are not compatible with Live Mode, only with Standard mode. If you are in Live Mode for a Standard Report Suite, but select a Virtual Report Suite in this dialog, once you click <span class="uicontrol"> OK </span> here, the Standard Mode will be displayed. </p> </p> <p>In addition, the Calendar control will be reinitialized to match the report suite's calendar type (Gregorian, retail, custom...). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Language </td> 
   <td colname="col2"> The selection corresponds to the languages offered for Adobe Analytics. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> About </td> 
   <td colname="col2"> Indicates the application's name and version number. </td> 
  </tr> 
 </tbody> 
</table>

