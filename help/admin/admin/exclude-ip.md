---
description: You can exclude data from specific IP addresses, such as internal website activities, site testing and employee usage, from your reports. Excluding data improves report accuracy by excluding IP address data. Additionally, you can remove data from denial of service or other malicious events that can skew report data. You can configure exclusion or by using your firewall.
seo-description: You can exclude data from specific IP addresses, such as internal website activities, site testing and employee usage, from your reports. Excluding data improves report accuracy by excluding IP address data. Additionally, you can remove data from denial of service or other malicious events that can skew report data. You can configure exclusion or by using your firewall.
seo-title: Exclude By IP Address
solution: Analytics
title: Exclude By IP Address
topic: Admin tools
uuid: 1ed6105f-e7c5-4c4f-b8f4-e5f66d0824bb
index: y
internal: n
snippet: y
---

# Exclude By IP Address

You can exclude data from specific IP addresses, such as internal website activities, site testing and employee usage, from your reports. Excluding data improves report accuracy by excluding IP address data. Additionally, you can remove data from denial of service or other malicious events that can skew report data. You can configure exclusion or by using your firewall.

 **[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Exclude by IP]**

* [Exclude By Cookie](../../admin/admin/exclude-ip.md#section_FB5A20AB5E514DA6BC596CC67F6A3A4C) 
* [Exclude by IP Address](../../admin/admin/exclude-ip.md#section_609FB6461529409D840111A32FEF5C3D) 
* [Exclude by Firewall](../../admin/admin/exclude-ip.md#section_3E7BFB71ADD941D39F923DB9557AD9CD)

>[!NOTE]
>
>Hits marked as *`bots`* are billed as [server calls](https://marketing.adobe.com/resources/help/en_US/reference/primary_server_calls.html).

## Exclude By Cookie {#section_FB5A20AB5E514DA6BC596CC67F6A3A4C}

Lets you exclude this computer from being tracked in your account. If you choose to exclude your computer, any data generated from your computer is not counted.

This feature allows you and your colleagues to visit your site without skewing your traffic data. You may want to use this feature if you do not have a static IP address (such as having a dial-up Internet connection through a service provider) and would like to exclude yourself from your account data. 

<table id="table_FB1006D3073549ACA08B9F350CE1B859"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Element </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Add CNAME</span> </td> 
   <td colname="col2"> <p> Generates an opt-out link you can use to exclude your domain. For assistance, please contact your company's Supported Users. </p> <p>Your traffic can be excluded from reporting in your report suites by visiting your company's opt-out page and choosing to exclude your browser from measurement. </p> <p>If your implementation is using third party cookies, your opt-out page is <a href="https://democorp.112.2o7.net/optout.html?locale=en_US&amp;popup=true" format="https" scope="external"> here</a>. </p> 
    <!--verify if article is still valid<p>If your implementation is using first party cookies, the URL foryour opt-out page is described in <xref href="https://sitecatalyst.omniture.com/p/suite/1.3/index.html?a=HelpMenu.RedirectMenu&amp;node_id=1629&amp;cat=Knowledge_Base&amp;ssSession=31be843e17adaeeff7d4098ed8d05418&amp;jpj=93289933601243">Knowledge Base article 1629</xref></p>--> </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>Exclusion by computer works only if: >
>* You access your web site from the same work station. 
>* Your cookies are enabled in the browser you are using. 
>* Your cookies are not deleted. If cookies are deleted, you must exclude yourself again. 
>

## Exclude by IP Address {#section_609FB6461529409D840111A32FEF5C3D}

An IP address is an Internet address. All Internet users are assigned numerical IP addresses (typically through Internet service providers) that effectively act as electronic identifiers.

Page views are counted and unique page visitors are identified through IP addresses. By excluding IP addresses from being counted, you can prevent Adobe from tracking frequent visitors. This feature can allow you and your colleagues to visit your site without skewing your traffic data. You may exclude up to 50 different IP addresses.

You can use wildcard indicators (&#42;) to exclude a range of addresses. For example, [!DNL 0.0.*.0] would exclude all IP addresses between [!DNL 0.0.0.0] and [!DNL 0.0.255.0]. You may exclude up to 50 different IP addresses.

## Exclude by Firewall {#section_3E7BFB71ADD941D39F923DB9557AD9CD}

You can also block data collection from specific IP addresses via a firewall.

See the [IP Addresses Used in the Experience Cloud](https://marketing.adobe.com/resources/help/en_US/home/index.html#kb-adobe-ip-addresses) article.

## Impact of IP Obfuscation {#section_51B7529FFF16449CA016FDC51D87E2CA}

If IP obfuscation is enabled, IP exclusion happens before the IP address is obfuscated, so customers don’'t need to change anything when they enable IP obfuscation.

If the last octet is removed, that is done before IP filtering. As such, the last octet is replaced with a 0, and IP exclusion rules should be updated to match IP addresses with a zero on the end. Matching &#42; should match 0. 
