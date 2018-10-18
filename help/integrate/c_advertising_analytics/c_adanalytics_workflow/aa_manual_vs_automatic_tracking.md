---
description: Tracking determines how Search Engine data is tracked by your Adobe Analytics implementation. This is a required step to properly augment the Adobe Analytics data with the Search Engine data.
seo-description: Tracking determines how Search Engine data is tracked by your Adobe Analytics implementation. This is a required step to properly augment the Adobe Analytics data with the Search Engine data.
seo-title: Tracking  Manual Mode and Auto Mode
title: Tracking  Manual Mode and Auto Mode
uuid: 57bcca2b-5d3d-448b-8e64-3012a53a744c
index: y
internal: n
snippet: y
---

# Tracking: Manual Mode and Auto Mode

Tracking determines how Search Engine data is tracked by your Adobe Analytics implementation. This is a required step to properly augment the Adobe Analytics data with the Search Engine data.

## Tracking: Manual Mode and Auto Mode {#topic_965B69533E6B4461A4A8A4F648CE6156}

Tracking determines how Search Engine data is tracked by your Adobe Analytics implementation. This is a required step to properly augment the Adobe Analytics data with the Search Engine data. 

Two tracking modes are supported: [Auto Mode](../../c_advertising_analytics/c_adanalytics_workflow/aa_manual_vs_automatic_tracking.md#concept_C4C6107838C947CFBB7F4E0CB94264F0) and [Manual Mode](../../c_advertising_analytics/c_adanalytics_workflow/aa_manual_vs_automatic_tracking.md#concept_87B28BA9E7F84BA5972F69E6F3482A33). 

## Auto Mode Tracking {#concept_C4C6107838C947CFBB7F4E0CB94264F0}

In Auto mode, you let the Advertising Cloud Engine decide how the Search Engine data should be handled. This is the simpler approach, but it may not result in the best integrated dataset.

As a consequence, you need to check an acknowledgment checkbox when you select Auto mode, before you can save the account setting.

>[!NOTE]
>
>To configure a search engine account in ‘Auto Mode’, you are responsible for taking the following actions: 
>
>* The "s_kwcid" parameter and value will be added to the account tracking templates or landing page URLs in the account being added. This will be inserted at the end of the URL. Additional action may be required on your part if your web server requires a certain key=value pair at the end of the URL OR an update to support any new key=value pair in the URL.**It is your responsibility to ensure that the added URL parameters persist correctly to the final landing page. ** 
>* In addition, keywords can be inserted into the landing URL as part of the "s_kwcid" value. If they contain special characters or symbols, please confirm that your web server can support these characters. Example: A common special characters is "+" which is used in "Broad Match Modified" keywords. 
>

## Manual Mode Tracking {#concept_87B28BA9E7F84BA5972F69E6F3482A33}

In Manual mode, you need to specify how the Search Engine data should be treated by the Advertising Analytics data integration process.

* [Add Manual Tracking to Google Account](../../c_advertising_analytics/c_adanalytics_workflow/aa_manual_vs_automatic_tracking.md#section_41C1EB1AEB034544A5BC291F53C05C67) 
* [Add Manual Tracking to Bing Account](../../c_advertising_analytics/c_adanalytics_workflow/aa_manual_vs_automatic_tracking.md#section_094F8ACA493C4D65B1F54A695558EBF2) 
* [Add Manual Tracking to Yahoo Gemini Account](../../c_advertising_analytics/c_adanalytics_workflow/aa_manual_vs_automatic_tracking.md#section_A45EA79F7DD04359984476002692D4EE)

## Add Manual Tracking to Google Account {#section_41C1EB1AEB034544A5BC291F53C05C67}

The string that needs to be added to your Google account is shown below. You need to add the string to all your tracking templates used throughout your account.

>[!IMPORTANT]
>
>The <Advertising Analytics ID> value (in **bold** below) is generic and **must be replaced with your specific account ID string**. You can get your specific account ID string from the account set up screen under the "Tracking" section.

**Tracking String for Campaigns:**

```
s_kwcid=AL! 
<b><Advertising Analytics ID></b>!3!{creative}!{matchtype}!{placement}!{network}!{product_partition_id}!{keyword}
```

![](assets/Google.png)

**Examples** of tracking codes in various tracking template formats: 

<table id="table_94171CCE70F84A599D044A26570A13C2"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Notes </th> 
   <th colname="col2" class="entry"> Tracking String </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>{lpurl} example </p> </td> 
   <td colname="col2"> 
    <codeblock>
      {lpurl}?s_kwcid=AL!9999!3!{creative}!{matchtype}!{placement}!network}!{product_partition_id}!{keyword} 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>{lpurl} with additional URL parameter example </p> </td> 
   <td colname="col2"> 
    <codeblock>
      {lpurl}?campaign=PPC&amp;s_kwcid=AL!9999!3!{creative}!{matchtype}!{placement}!network}!{product_partition_id}!{keyword}

    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>3rd-party (DoubleClick) {unescapedlpurl} example </p> </td> 
   <td colname="col2"> 
    <codeblock>
      http://clickserve.dartsearch.net/link/click?{_dssagcrid}&amp;{_dssftfiid}&amp;ds_e_adid={creative}&amp;ds_e_matchtype={ifsearch:search}{ifcontent:content}&amp;ds_e_device={device}&amp;ds_e_network={network}&amp;{ifpla:ds_e_product_group_id={product_partition_id}&amp;ds_e_product_id={product_id}&amp;ds_e_product_merchant_id={merchant_id}&amp;ds_e_product_country={product_country}&amp;ds_e_product_language={product_language}&amp;ds_e_product_channel={product_channel}&amp;ds_e_product_store_id={product_store_id}}&amp;ds_url_v=2&amp;ds_dest_url={unescapedlpurl}?s_kwcid=AL!9999!3!{creative}!{matchtype}!{placement}!{network}!{product_partition_id}!{keyword}

    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>3rd-party (DoubleClick) {lpurl} example </p> <p>If the URL goes through a redirect and is not using an “unescapedlpurl” value, you need to encode the string enough times so that it persists through the redirect to the final landing page URL. </p> </td> 
   <td colname="col2"> 
    <codeblock>
      http://clickserve.dartsearch.net/link/click?{_dssagcrid}&amp;{_dssftfiid}&amp;ds_e_adid={creative}&amp;ds_e_matchtype={ifsearch:search}{ifcontent:content}&amp;ds_e_device={device}&amp;ds_e_network={network}&amp;{ifpla:ds_e_product_group_id={product_partition_id}&amp;ds_e_product_id={product_id}&amp;ds_e_product_merchant_id={merchant_id}&amp;ds_e_product_country={product_country}&amp;ds_e_product_language={product_language}&amp;ds_e_product_channel={product_channel}&amp;ds_e_product_store_id={product_store_id}}&amp;ds_url_v=2&amp;ds_dest_url={lpurl}?s_kwcid%3DAL!9999!3!{creative}!{matchtype}!{placement}!{network}!{product_partition_id}!{keyword}

    </codeblock> </td> 
  </tr> 
 </tbody> 
</table>

## Add Manual Tracking to Bing Account {#section_094F8ACA493C4D65B1F54A695558EBF2}

The string that needs to be added to your Bing account is shown below. You need to add the string to all your tracking templates used throughout your account.

>[!IMPORTANT]
>
>The <Advertising Analytics ID> value (in **bold** below) is generic and **must be replaced with your specific account ID string**. You can get your specific account ID string from the account set up screen under the "Tracking" section.

**Tracking String for Campaigns:** 

```
s_kwcid=AL!<Advertising Analytics ID>!10!{AdId}!{OrderItemId} 

```

![](assets/Bing.png)

**Examples** of tracking codes in various tracking template formats: 

<table id="table_BF4B7C0039794F6AA454FD916A665092"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Notes </th> 
   <th colname="col2" class="entry"> Tracking String </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> {lpurl} example </p> </td> 
   <td colname="col2"> 
    <codeblock>
      {lpurl}? 
     <b>s_kwcid=AL!9999!10!{AdId}!{OrderItemId}</b>

    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>{lpurl} with additional URL parameter example </p> </td> 
   <td colname="col2"> 
    <codeblock>
      {lpurl}?campaign=PPC&amp; 
     <b>s_kwcid=AL!9999!10!{AdId}!{OrderItemId}</b>

    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>3rd-party (DoubleClick) {unescapedlpurl} example </p> </td> 
   <td colname="col2"> 
    <codeblock>
      http://clickserve.dartsearch.net/link/click?{_dssagcrid}&amp;{_dssftfiid}&amp;ds_e_adid={creative}&amp;ds_e_matchtype={ifsearch:search}{ifcontent:content}&amp;ds_e_device={device}&amp;ds_e_network={network}&amp;{ifpla:ds_e_product_group_id={product_partition_id}&amp;ds_e_product_id={product_id}&amp;ds_e_product_merchant_id={merchant_id}&amp;ds_e_product_country={product_country}&amp;ds_e_product_language={product_language}&amp;ds_e_product_channel={product_channel}&amp;ds_e_product_store_id={product_store_id}}&amp;ds_url_v=2&amp;ds_dest_url={unescapedlpurl}?s_kwcid=AL!9999!10!{AdId}!{OrderItemId}

    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>3rd-party (DoubleClick) {lpurl} example </p> <p>If the URL goes through a redirect and is not using an “unescapedlpurl” value, you need to encode the string enough times so that it persists through the redirect to the final landing page URL. </p> </td> 
   <td colname="col2"> 
    <codeblock>
      http://clickserve.dartsearch.net/link/click?{_dssagcrid}&amp;{_dssftfiid}&amp;ds_e_adid={creative}&amp;ds_e_matchtype={ifsearch:search}{ifcontent:content}&amp;ds_e_device={device}&amp;ds_e_network={network}&amp;{ifpla:ds_e_product_group_id={product_partition_id}&amp;ds_e_product_id={product_id}&amp;ds_e_product_merchant_id={merchant_id}&amp;ds_e_product_country={product_country}&amp;ds_e_product_language={product_language}&amp;ds_e_product_channel={product_channel}&amp;ds_e_product_store_id={product_store_id}}&amp;ds_url_v=2&amp;ds_dest_url={lpurl}?s_kwcid%3DAL!9999!10!{AdId}!{OrderItemId}

    </codeblock> </td> 
  </tr> 
 </tbody> 
</table>

## Add Manual Tracking to Yahoo Gemini Account {#section_A45EA79F7DD04359984476002692D4EE}

The string that needs to be added to your Yahoo Gemini account is shown below. Add the string to the end of all your destination URLs.

>[!IMPORTANT]
>
>The <Advertising Analytics ID> value (in **bold** below) is generic and **must be replaced with your specific account ID string**. You can get your specific account ID string from the account set up screen under the "Tracking" section.

```
s_kwcid=AL! 
<b><Advertising Analytics ID></b>!105!{adid}!{network}!{keywordid} 

```

![](assets/Yahoo.png)

**Examples of tracking codes in various destination URL formats:** 

<table id="table_2A457396F726434380272ED26DB2434B"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Notes </th> 
   <th colname="col2" class="entry"> Tracking String </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Landing page URL example </p> </td> 
   <td colname="col2"> 
    <codeblock>
      http://www.website.com? 
     <b>s_kwcid=AL!9999!105!{adid}!{network}!{keywordid}</b>

    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Landing page URL with additional URL parameter example </p> </td> 
   <td colname="col2"> 
    <codeblock>
      http://www.website.com?campaign=PPC&amp; 
     <b>s_kwcid=AL!9999!105!{adid}!{network}!{keywordid}</b>

    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>3rd-party (DoubleClick) landing page example </p> </td> 
   <td colname="col2"> 
    <codeblock>
      http://clickserve.dartsearch.net/link/click?{_dssagcrid}&amp;{_dssftfiid}&amp;ds_e_adid={creative}&amp;ds_e_matchtype={ifsearch:search}{ifcontent:content}&amp;ds_e_device={device}&amp;ds_e_network={network}&amp;{ifpla:ds_e_product_group_id={product_partition_id}&amp;ds_e_product_id={product_id}&amp;ds_e_product_merchant_id={merchant_id}&amp;ds_e_product_country={product_country}&amp;ds_e_product_language={product_language}&amp;ds_e_product_channel={product_channel}&amp;ds_e_product_store_id={product_store_id}}&amp;ds_url_v=2&amp;ds_dest_url=&nbsp;http://www.website.com?s_kwcid=AL!9999!105!{adid}!{network}!{keywordid}

    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> If the URL goes through a redirect, you need to encode the string enough times so that it persists through the redirect to the final landing page URL. </td> 
   <td colname="col2"> 
    <codeblock>
      http://clickserve.dartsearch.net/link/click?{_dssagcrid}&amp;{_dssftfiid}&amp;ds_e_adid={creative}&amp;ds_e_matchtype={ifsearch:search}{ifcontent:content}&amp;ds_e_device={device}&amp;ds_e_network={network}&amp;{ifpla:ds_e_product_group_id={product_partition_id}&amp;ds_e_product_id={product_id}&amp;ds_e_product_merchant_id={merchant_id}&amp;ds_e_product_country={product_country}&amp;ds_e_product_language={product_language}&amp;ds_e_product_channel={product_channel}&amp;ds_e_product_store_id={product_store_id}}&amp;ds_url_v=2&amp;ds_dest_url=&amp;nbsp;http%3A%2F%2Fwww.website.com%3Fs_kwcid%3DAL!9999!105!{adid}!{network}!{keywordid} 
    </codeblock> </td> 
  </tr> 
 </tbody> 
</table>

