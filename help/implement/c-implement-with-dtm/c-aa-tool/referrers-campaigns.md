---
description: Field descriptions in Dynamic Tag Management for referrers and campaign options when deploying Dynamic Tag Management in Adobe Analytics.
keywords: Dynamic Tag Management;referrers;campaigns;referrer override;campaign variable;query param
seo-description: Field descriptions in Dynamic Tag Management for referrers and campaign options when deploying Dynamic Tag Management in Adobe Analytics.
seo-title: Referrers and campaigns
solution: Marketing Cloud,Analytics,Dynamic Tag Management
title: Referrers and campaigns
uuid: 56580206-a382-4993-9bba-a488da65cf89
index: y
internal: n
snippet: y
---

# Referrers and campaigns

Field descriptions in Dynamic Tag Management for referrers and campaign options when deploying Dynamic Tag Management in Adobe Analytics.

 **[!UICONTROL  *`Property`*]** > **[!UICONTROL   ![](assets/settings_gear.png)

Edit Tool]** > **[!UICONTROL Referrers & Campaigns]**

<table id="table_09AE3BFF0F12442F9C19CD96451F93E4"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Element </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Referrer Override </td> 
   <td colname="col2"> <p>Overrides the value set in the <span class="varname"> s.referrer</span> variable, which is typically populated by the referrer set in the browser. </p> <p>See <a href="referrer.md#concept_3D8E6A5D30DC4D92982EFA34D4C7F81B" format="dita" scope="local"> referrer</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Campaign </td> 
   <td colname="col2"> <p>A variable that identifies marketing campaigns used to bring visitors to your site. The value of campaign is usually taken from a query string parameter. </p> <p>See <a href="campaign.md#concept_C7BF7B8A69D048A6AB482052A98A91F8" format="dita" scope="local"> campaign</a>. </p> </td> 
  </tr> 
 </tbody> 
</table>

Use the DTM interface to choose whether you want to use a Query String or Value (which could pull from a data element):

![](assets/dtm-queryparam.png)

You can either enter your query string directly in the interface, or you can reference a separate data element if you have other means of tracking a campaign. 
