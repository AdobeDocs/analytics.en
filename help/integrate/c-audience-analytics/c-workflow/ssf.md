---
description: Server-side forwarding is designed for customers who want to share data from Analytics to other Experience Cloud Solutions in real time. When enabled, server-side forwarding also allows Analytics to push data to other Experience Cloud solutions and for those solutions to push data to Analytics during the data collection process.
seo-description: Server-side forwarding is designed for customers who want to share data from Analytics to other Experience Cloud Solutions in real time. When enabled, server-side forwarding also allows Analytics to push data to other Experience Cloud solutions and for those solutions to push data to Analytics during the data collection process.
seo-title: Server-side forwarding overview
solution: Audience Manager
title: Server-side forwarding overview
uuid: 32ef4bb0-a43b-42db-8738-6f8c0280b6c4
index: y
internal: n
snippet: y
---

# Server-side forwarding overview

Server-side forwarding is designed for customers who want to share data from Analytics to other Experience Cloud Solutions in real time. When enabled, server-side forwarding also allows Analytics to push data to other Experience Cloud solutions and for those solutions to push data to Analytics during the data collection process.

Server-side forwarding improves upon data collection because it:

* Reduces calls from the page. With server-side forwarding, customers of Audience Manager no longer need to use DIL for data collection because it is being forwarded from Analytics. Removing DIL means eliminating a&nbsp;"/event"&nbsp;call. Fewer calls helps improve page load times, which makes for a better customer experience on your site. 
* Lets you take advantage of data sharing among Experience Cloud solutions. 
* Conforms with our best practices for Audience Manager code implementation and deployment.

>[!TIP]
>
>Current Audience Manager customers who use Analytics should migrate to server-side forwarding. New Adobe Analytics and Audience Manager customers should implement server-side forwarding (instead of DIL) as the default data collection and transfer method.

>[!IMPORTANT]
>
>Prompted by the [EU cookie compliance](https://ec.europa.eu/ipg/basics/legal/cookies/index_en.htm) regulation, data controllers (Analytics customers) now have the option to restrict pre-consent data to Adobe Analytics, and prevent it from being server-side forwarded to Adobe Audience Manager (AAM). A new implementation context variable lets you flag hits where consent has not been received. The variable, when set, prevents these hits from being sent to AAM until consent has been received. For more information, see [GDPR_ePrivacy compliance and server-side forwarding](../../../integrate/c-audience-analytics/c-workflow/ssf-gdpr.md#concept_86B216635E9A49F9B3DBBBD4DFD8AAF6).

To understand where your organization is in terms of implementing server-side forwarding, go through these validation steps: 

<table id="table_1202921AB8D34AC58C0FED2E665AA8EF"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Step # </th> 
   <th colname="col2" class="entry"> Task Description </th> 
   <th colname="col3" class="entry"> Notes </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><img href="assets/step1_icon.png" id="image_9E7E759DF38A4AF584FB87171AA954D2" /> </p> </td> 
   <td colname="col2"> <p>Verify whether Experience Cloud ID (MID)service is implemented, by inspecting the <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid-test-verify.html" format="html" scope="external"> Analytics tracking request </a>. </p> </td> 
   <td colname="col3"> <p>On the <span class="uicontrol"> Request </span> tab, verify that a MID value is being set. This tells you that Experience Cloud ID service is implemented correctly, which is a pre-requisite for server-side forwarding. </p> 
    <ul id="ul_BB3331B9E4294C8483A9E54908B3BDD8"> 
     <li id="li_875DCD2EB2144EB48788349D2A263982">If you see a MID value, continue to step 2. </li> 
     <li id="li_938CE41E171A4B7BB56F37AB165C2A44">If you do not see a MID value, <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid-implementation-guides.html" format="html" scope="external"> implement Experience Cloud ID Service </a> before proceeding to step 2. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><img href="assets/step2_icon.png" id="image_F83BEDD80FE343E6A1F4010F5D9C3F57" /> </p> </td> 
   <td colname="col2"> <p>Verify whether you already have a version of server-side forwarding implemented, by <a href="../../../integrate/c-audience-analytics/c-workflow/ssf-verify.md#concept_E2E585082D91422296924B9B6FCA97CC" format="dita" scope="local"> inspecting the Analytics tracking request </a>. </p> </td> 
   <td colname="col3"> <p>In the “Response” tab, check that the response contains Audience Manager data. If you see: </p> 
    <ul id="ul_155BD7A4AE334E82B77C4CA1AC3AA8BF"> 
     <li id="li_0E4C3C95BC594A05909289A2D8AD28B3">A <b>JSON response from Audience Manager that includes items such as “postbacks” or “dcs_region”</b>: you have some form of server-side forwarding already enabled. Continue to step 3. </li> 
     <li id="li_050B15A614364581AEAD50A61110D493">The <b>“status":"SUCCESS”</b>: you have the Audience Management Module implemented, but do not have server side forwarding properly configured. Continue to step 3. </li> 
     <li id="li_39F0E95ABAC34483A058420CFA021E3B">A <b>2 x 2 image</b>: you do not have server-side forwarding or the Audience Management Module implemented. To correct this: 
      <ul id="ul_DFFDEEFDD5F048D4BD8DE84091D10191"> 
       <li id="li_BF2207217328467CA42696DBF99D7ECD"><b>AAM Customers with DIL</b>: coordinate the following 2 items in close conjunction: 
        <ol id="ol_B93D1A47FB9F43908FA6C45C93D45CD7"> 
         <li id="li_0F670A41BED44E09B07E696365B9FE08">Remove the DIL code and install the <a href="https://marketing.adobe.com/resources/help/en_US/aam/c_profiles_audiences.html" format="html" scope="external"> Audience Management Module </a> page code. </li> 
         <li id="li_F68F1C1D637F4AEA8349109D7B7B8F36">Enable server-side forwarding in the Analytics Admin UI as described in step 3. Enabling this setting before removing DIL code will duplicate data and create additional billed server calls to Audience Manager. </li> 
        </ol> </li> 
       <li id="li_E146966CF75C4229AABB9E8FCEA32F50"><b>New AAM customers</b> - install the <a href="https://marketing.adobe.com/resources/help/en_US/aam/c_profiles_audiences.html" format="html" scope="external"> Audience Management Module </a> page code and continue to step 3. Data will not be sent to Audience Manager until server-side forwarding is turned on in step 3. </li> 
      </ul> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><img href="assets/step3_icon.png" id="image_FA535B68EF684D82A3FFEE67771EFFF9" /> </p> </td> 
   <td colname="col2"> <p>Verify whether you have server-side forwarding implemented at the report-suite level, rather than the legacy tracking server approach. </p> </td> 
   <td colname="col3"> <p>Server-side forwarding at the report-suite level is recommended over the legacy tracking server approach because you can control at a finer level what data gets shared from Analytics. It is also a pre-requisite for this Audience Analytics integration. </p> <p>Go to <span class="ignoretag"> <span class="uicontrol"> Analytics </span>  &gt; <span class="uicontrol"> Admin </span>  &gt; <span class="uicontrol"> Report Suites </span>  &gt; <span class="uicontrol"> (select report suites) </span>  &gt; <span class="uicontrol"> Edit Settings </span>  &gt; <span class="uicontrol"> General </span>  &gt; <span class="uicontrol"> Server Side Forwarding </span> </span>. If the checkbox is: </p> 
    <ul id="ul_C394EBED4763431CB16095B54EA6C267"> 
     <li id="li_D5BF3D103AA3486FA3556FE94753E5C3"><b>Inactive</b> (You are unable to make a selection or the menu does not exist): you do not have the selected report suites mapped to your Experience Cloud Org. Make sure that your applicable report suites are mapped to the proper Experience Cloud Org using the <a href="https://marketing.adobe.com/resources/help/en_US/mcloud/report-suite-mapping.html" format="html" scope="external"> Report Suite Mapping UI </a>. </li> 
     <li id="li_43EBF40BBEC741D3AEA8262F21248902"><b>Disabled</b>: You do not have the new server-side forwarding turned on. Read the content on the page and then proceed with enabling the feature. </li> 
     <li id="li_767FCC14BCF04C0CBCD2B0B4459EE68A"><b>Enabled</b>: You are provisioned for new server-side forwarding. You are also able to set up this Audience Analytics integration. </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>Data will not appear in&nbsp;other Experience Cloud solutions, such as [Audience Manager](https://marketing.adobe.com/resources/help/en_US/aam/c_aam_home.html)&nbsp;or [Audiences](https://marketing.adobe.com/resources/help/en_US/mcloud/audience_library.html),&nbsp;until all 3 steps are complete. Once enabled, it will take several hours for these settings to take effect.

