---
description: By tracking and recording the visitors’' referring sites for each visit, you can determine how visitors found out about your site for each visit.
seo-description: By tracking and recording the visitors’' referring sites for each visit, you can determine how visitors found out about your site for each visit.
seo-title: Referrer Type
solution: Analytics
title: Referrer Type
topic: Reports
uuid: 7f63d327-d223-4537-a722-4780aae05c2b
index: y
internal: n
snippet: y
---

# Referrer Type

By tracking and recording the visitors’' referring sites for each visit, you can determine how visitors found out about your site for each visit.

The list below defines the various types of referrers:

**Other websites**: referrers are recorded when visitors click a link located on a page on another website (not defined as part of your site) and arrive at your website.

**Search engines**: Search engine referrers are recorded when visitors use a search engine to access your site. The referring value must be considered by Adobe to be a search engine, and cannot be a subdomain that is not considered a search engine (e.g. [!DNL mail.yahoo.com] is not a search engine since this domain is used for email).

**[!UICONTROL Social networks]**: The referring value must be considered by Adobe to be a social network. See [List of social networks](https://helpx.adobe.com/analytics/kb/list-social-networks.html).

**Email**: A referring domain is considered as an email referring domain when visitors click an emailed message link containing the protocol [!DNL imap://] or [!DNL mail://] and arrive at your site. For example, anything coming from [!DNL http://mail.yahoo.com] is not counted as an email referrer because the protocol is [!DNL http://]. Emails from Outlook are reported in the Typed/Bookmarked line, while any referrer with an HTTP protocol where the domain is a known search engine is reported in the Search Engine line.

**Typed/Bookmarked**: referrers are recorded when visitors type your site’s URL directly into their browser, or if they access your site by selecting bookmarks. Mobile devices report a referrer type of *`typed/bookmarked`* if there is no referrer on the first hit of the visit.

**[!UICONTROL Inside Your Site]**: These items are URLs that are tagged by the internal URL filters. These items are not counted as *`referrer instances`* but can be seen when reporting on other metrics.

## Referrer Types by Interface {#section_4D8CE5E111DD48FBBDCF9B5A1F16E92E}

<table id="table_EC7423532C7E44DE97B7FC0321585A2B"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> </th> 
   <th colname="col2" class="entry"> Marketing reports &amp; analytics (SiteCatalyst) </th> 
   <th colname="col3" class="entry"> Ad hoc analytics </th> 
   <th colname="col4" class="entry"> Data warehouse </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Reported referrer types </td> 
   <td colname="col2"> 
    <ul id="ul_EFC8E81EC6DF4CC2AC0E290244FD5859"> 
     <li id="li_686FCAEB04054B9F8A7D2434E8C49F04">Other websites </li> 
     <li id="li_C232868230AA4A54958B524F3D8FDA35"> Search engines </li> 
     <li id="li_A89BFD0468F74ED7822F64BE4A7332AE"> Social </li> 
     <li id="li_C824E6F7F6E748DD827A95B105ADBADD"> Typed/Bookmarked </li> 
    </ul> <p> This report displays only two predefined metrics: Instances and Unique Visitors. </p> </td> 
   <td colname="col3"> 
    <ul id="ul_FD81EB3C1BD949A39C5A9E9688D25271"> 
     <li id="li_6099E7E03F3843D484808258A332BBE9">Other websites </li> 
     <li id="li_5AABC02DA7964D578BF8404DA819245D"> Search engines </li> 
     <li id="li_B18907AC7FA1429A893B57634EB7DC6F"> Social </li> 
     <li id="li_7674B67897994E1FA99BCD9B604BCB6E"> Typed/Bookmarked </li> 
    </ul> </td> 
   <td colname="col4"> 
    <ul id="ul_C37ADBEC31D04295BF5CDEA25DB5191A"> 
     <li id="li_81A642C96C674669BA00B2DACA534B8A">Other websites </li> 
     <li id="li_29B9DA9F2AAD46A69886D34D5E6E43D4"> Search engines </li> 
     <li id="li_E381EEF111F248F99EE39600D616B7C2"> Social </li> 
     <li id="li_596377F4D3C248BEA5191EE2985A2B13"> Typed/Bookmarked </li> 
     <li id="li_A7A72D3D6B9A4CCFB43EDA77ABFDEDBC"> Inside your site </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

## Notes {#section_B83A3571D64E4E7792712FAF740D7955}

* The referrer, referrer type, and referring domain are set on the first hit of the visit, or during a visit when the referrer is external (for example, if a visitor leaves your site, uses a search engine, then returns to your site before the first visit expires). These values are set at the same time and persist across the visit. 
* Not all referrer types are listed on this report. This means that site wide Visits don't match visits on this report.

## Report History {#section_6C0FCEA9DAF04D97BA056E153B7E4628}

|  Date  | Change  |
|---|---|
|  1/16/2014  | Data warehouse was updated to match the logic used by marketing reports & analytics. Before this date, referrer type did not persist across the visit.  |

