---
description: Tracking type determines how the Adobe Analytics implementation tracks your search engine data. This tracking type is a required step to augment the Adobe Analytics data properly with search engine data.
title: Tracking Type
feature: Advertising Analytics
exl-id: 3e2ed26f-dfb2-43ea-8eb6-e332cd10fb29
---
# Tracking Type

Tracking type determines how the Adobe Analytics implementation tracks your search engine data. This tracking type is a required step to augment the Adobe Analytics data properly with search engine data.

<!--

Here is a video overview of how to implement the Advertising Analytics tracking template:

>[!VIDEO](https://video.tv.adobe.com/v/23120/?quality=12)

-->

Two tracking modes are supported: [!UICONTROL Auto] and [!UICONTROL Manual].

## [!UICONTROL Auto] Tracking {#concept_C4C6107838C947CFBB7F4E0CB94264F0}

[!UICONTROL Auto] tracking lets the Advertising Cloud engine decide how the search engine data should be handled. Auto tracking is the simpler approach, but may not result in the best integrated dataset.

As a consequence, you need to check an acknowledgment checkbox when you select **[!UICONTROL Auto]** before you can save the account setting.

Note that to configure a search engine account with **[!UICONTROL Auto]** type, you are responsible for taking the following actions: 

* The `s_kwcid` parameter and value is added to the account tracking templates or landing page URLs in the account being added. This parameter and value is inserted at the end of the URL. Additional action may be required on your part if your web server requires a certain `key=value` pair at the end of the URL. Or an update to support any new `key=value` pair in the URL. It is your responsibility to ensure that the added URL parameters persist correctly to the final landing page. 
* In addition, keywords can be inserted into the landing URL as part of the `s_kwcid` value. If they contain special characters or symbols, please confirm that your web server can support these characters. For example, a common special character is `+`, which is used in "Broad Match Modified" keywords.

>[!IMPORTANT]
>
>Learn more on whether you should add the `s_kwcid` parameter to your [Content Security Policy](https://experienceleague.adobe.com/en/docs/id-service/using/reference/csp).

## Manual Tracking {#concept_87B28BA9E7F84BA5972F69E6F3482A33}

Manual tracking enables you to specify how the Advertising Analytics data integration process should treat the search engine data.

### Add Manual tracking to Google Account {#section_41C1EB1AEB034544A5BC291F53C05C67}

The string that needs to be added to your Google account is shown below. You need to add the string to all your tracking templates used throughout your account.

>[!IMPORTANT]
>
>The *`<Advertising Analytics ID>`* value (in **bold** below) is generic and **must be replaced with your specific account ID string**. You can get your specific account ID string from the account screen under the [!UICONTROL Tracking] section.

**Tracking String for Campaigns:**

```
s_kwcid=AL! 
<b><Advertising Analytics ID></b>!3!{creative}!{matchtype}!{placement}!{network}!{product_partition_id}!{keyword}
```

![](assets/google.png)

Examples of tracking codes in various tracking template formats: 

**`{lpurl}`**

```
{lpurl}?s_kwcid=AL!9999!3!{creative}!{matchtype}!{placement}!network}!{product_partition_id}!{keyword}
```

**`{lpurl}` with additional URL parameter**

```
{lpurl}?campaign=PPC&s_kwcid=AL!9999!3!{creative}!{matchtype}!{placement}!network}!{product_partition_id}!{keyword}
```

**3rd-party (DoubleClick) `{unescapedlpurl}`**

```
https://clickserve.dartsearch.net/link/click?{_dssagcrid}&{_dssftfiid}&ds_e_adid={creative}&ds_e_matchtype={ifsearch:search}{ifcontent:content}&ds_e_device={device}&ds_e_network={network}&{ifpla:ds_e_product_group_id={product_partition_id}&ds_e_product_id={product_id}&ds_e_product_merchant_id={merchant_id}&ds_e_product_country={product_country}&ds_e_product_language={product_language}&ds_e_product_channel={product_channel}&ds_e_product_store_id={product_store_id}}&ds_url_v=2&ds_dest_url={unescapedlpurl}?s_kwcid=AL!9999!3!{creative}!{matchtype}!{placement}!{network}!{product_partition_id}!{keyword}
```

**3rd-party (DoubleClick) `{lpurl}`**

To ensure that the string persists through the redirect to the final landing page URL, you need to encode the string sufficiently:

* if the URL goes through a redirect, and
* is not using an "unescapedlpurl" value.
  

```
https://clickserve.dartsearch.net/link/click?{_dssagcrid}&{_dssftfiid}&ds_e_adid={creative}&ds_e_matchtype={ifsearch:search}{ifcontent:content}&ds_e_device={device}&ds_e_network={network}&{ifpla:ds_e_product_group_id={product_partition_id}&ds_e_product_id={product_id}&ds_e_product_merchant_id={merchant_id}&ds_e_product_country={product_country}&ds_e_product_language={product_language}&ds_e_product_channel={product_channel}&ds_e_product_store_id={product_store_id}}&ds_url_v=2&ds_dest_url={lpurl}?s_kwcid%3DAL!9999!3!{creative}!{matchtype}!{placement}!{network}!{product_partition_id}!{keyword}
```

### Add Manual tracking to Bing Account {#section_094F8ACA493C4D65B1F54A695558EBF2}

The string that needs to be added to your Bing account is shown below. You need to add the string to all the final URL suffixes used throughout your account.

>[!IMPORTANT]
>
>The _`<Advertising Analytics ID>`_ value (in **bold** below) is generic and **must be replaced with your specific account ID string**. You can get your specific account ID string from the account screen under the "Tracking" section.

**Tracking String for Campaigns:** 

```
s_kwcid=AL!<Advertising Analytics ID>!10!{AdId}!{OrderItemId} 
```

![](assets/bing.png)

Examples of tracking codes in various final URL suffix formats: 

**{lpurl}**

```
{lpurl}?s_kwcid=AL!9999!10!{AdId}!{OrderItemId}
```

**`{lpurl}` with additional URL parameter**

```
{lpurl}?campaign=PPC&
s_kwcid=AL!9999!10!{AdId}!{OrderItemId}
```

**3rd-party (DoubleClick) `{unescapedlpurl}`**

```
https://clickserve.dartsearch.net/link/click?{_dssagcrid}&{_dssftfiid}&ds_e_adid={creative}&ds_e_matchtype={ifsearch:search}{ifcontent:content}&ds_e_device={device}&ds_e_network={network}&{ifpla:ds_e_product_group_id={product_partition_id}&ds_e_product_id={product_id}&ds_e_product_merchant_id={merchant_id}&ds_e_product_country={product_country}&ds_e_product_language={product_language}&ds_e_product_channel={product_channel}&ds_e_product_store_id={product_store_id}}&ds_url_v=2&ds_dest_url={unescapedlpurl}?s_kwcid=AL!9999!10!{AdId}!{OrderItemId}
```

**3rd-party (DoubleClick) `{lpurl}`**

To ensure that the string persists through the redirect to the final landing page URL, you need to encode the string sufficiently:

* if the URL goes through a redirect, and
* is not using an "unescapedlpurl" value.

```
https://clickserve.dartsearch.net/link/click?{_dssagcrid}&{_dssftfiid}&ds_e_adid={creative}&ds_e_matchtype={ifsearch:search}{ifcontent:content}&ds_e_device={device}&ds_e_network={network}&{ifpla:ds_e_product_group_id={product_partition_id}&ds_e_product_id={product_id}&ds_e_product_merchant_id={merchant_id}&ds_e_product_country={product_country}&ds_e_product_language={product_language}&ds_e_product_channel={product_channel}&ds_e_product_store_id={product_store_id}}&ds_url_v=2&ds_dest_url={lpurl}?s_kwcid%3DAL!9999!10!{AdId}!{OrderItemId}
```
