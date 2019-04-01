---
description: Paid Search Detection differentiates paid from natural searches in the Search Engines and Search Keywords reports. You can specify the search engines where you use paid ads, and specify a character string found in the URL of a visit from a paid ad.
seo-description: Paid Search Detection differentiates paid from natural searches in the Search Engines and Search Keywords reports. You can specify the search engines where you use paid ads, and specify a character string found in the URL of a visit from a paid ad.
seo-title: Paid Search Detection
solution: Analytics
title: Paid Search Detection
topic: Admin tools
uuid: 41aadf17-7b8b-49ce-84ca-dc3293660205
---

# Paid Search Detection

Paid Search Detection differentiates paid from natural searches in the Search Engines and Search Keywords reports. You can specify the search engines where you use paid ads, and specify a character string found in the URL of a visit from a paid ad.

## Paid Search Detection - Descriptions {#section_0C2CFA0AF77B47098BE37CB024665D0D}

The following table describes the fields and options you use to [configure paid search detection](../../../admin/admin/paid-search-detection/t-paid-search-detection.md#task_D0BBDB78771E4BDBB495A004A080D647). 

<table id="table_E609632569EB499184E56618C2CEF742"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Elements </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Search Engine</span> </td> 
   <td colname="col2">Select a search engine from the drop-down list. You specify the engine if you use different query string parameters for different search engines. Usually, the value <span class="uicontrol"> Any</span> is sufficient. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Query string</span> </td> 
   <td colname="col2"> <p>Specifies a case-sensitive rule set to either contain or not contain a specific value. This value should be the query string parameter, omitting the <code> ?</code>. </p> <p>Note: Paid Search Detection is case sensitive. For example, a rule that specifies <span class="term"> PID</span> as a query string parameter does not display <span class="term"> pid</span> in reporting. If your organization uses mixed cases, place the exact values as separate rules, so all desired query string parameters can be caught. </p> </td> 
  </tr> 
 </tbody> 
</table>

