---
description: null
seo-description: null
seo-title: Implementation roadmap
title: Implementation roadmap
uuid: 988bcca5-67ae-4e3f-97e6-6a42030b1962
---

# Implementation roadmap

## New Users {#section_77433E4FC5ED4C6BAFC1E72EB61C4503}

If you are new to Adobe Analytics, you can quickly create your first Analytics report suite (data repository) using the [Getting Started with Adobe Analytics](https://marketing.adobe.com/resources/help/en_US/analytics/getting-started/) guide. Then, you can deploy Analytics code using [Experience Platform Launch](https://docs.adobelaunch.com/).

## Implementation Roadmap {#section_E3DD8D199B744FFB9E9B386A44220206}

<table id="table_1683413EA0E34DBC9291832647B68E96"> 
 <thead> 
  <tr> 
   <th colname="col01" class="entry"> Step </th> 
   <th colname="col1" class="entry"> Task </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col01"> <img  src="assets/step1_icon.png" id="image_21F30BBFC0A249F8B0E1A50EBBEED77D" /> </td> 
   <td colname="col1"> Choose an implementation method. </td> 
   <td colname="col2"> <p>Common ways to implement Analytics include: </p> <p> 
     <ul id="ul_A7475867861540EFBD77AEE8C6DAD418"> 
      <li id="li_035E2619670F4D04A7F708625A9C01EF"> <a href="https://docs.adobelaunch.com/" format="https" scope="external"> Experience Platform Launch </a> (Recommended) <p>This guide tells you everything you need to know about using Adobe's website tag and mobile SDK management capabilities and how to implement them. </p> </li> 
      <li id="li_996FA2F5B0E149399CED391AB5235D8A"> <a href="../../implement/c-implement-with-dtm/dtm-implementation-overview.md" format="dita" scope="local"> Dynamic Tag Management </a> <p>This guide contains Analytics-specific information to guide you through a Dynamic Tag Management implementation. </p> </li> 
      <li id="li_18E6AD6D864246D0BA26DAA1D91DD811"> <a href="../../implement/js-implementation/javascript-implementation-overview.md" format="dita" scope="local"> JavaScript </a> <p>This guide contains a description of data collection variables and details on implementing data collection code in JavaScript, including <a href="https://marketing.adobe.com/resources/help/en_US/sc/appmeasurement/video/video_js.html" format="https" scope="external"> video </a>. </p> </li> 
      <li id="li_85EC7A0AC5E04EE6981ED72A88C5D1FD"> <a href="https://marketing.adobe.com/resources/help/en_US/reference/developer.html" format="html" scope="external"> Analytics SDKs </a> <p>Use Analytics SDKs to manage: </p> <p> 
        <ul id="ul_F67F2E1964724800A84445A36DFB8E86"> 
         <li id="li_9C43F051EB5B4EA7A4C14EC1513DB824"> <a href="https://marketing.adobe.com/resources/help/en_US/mobile/ios/analytics_main.html" format="html" scope="external"> Mobile apps on iOS </a> </li> 
         <li id="li_4354E44EB8B3494A88578C1621EF5BAC"> <a href="https://marketing.adobe.com/resources/help/en_US/mobile/android/analytics_main.html" format="html" scope="external"> Mobile apps on Android </a> </li> 
        </ul> </p> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <img  src="assets/step2_icon.png" id="image_02CFDC007BF1486AA312698EBFFA79F7" /> </td> 
   <td colname="col1"> Set up the Identity Service. </td> 
   <td colname="col2"> <p>(Formerly <span class="term"> Visitor ID service </span>.) See <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid-setup-analytics.html" format="https" scope="external"> Set Up the Identity Service for Analytics </a>. </p> 
    <draft-comment> 
     <p>In <code> VisitorAPI.js </code>, add the following visitor ID initialization code at the beginning of the file: </p> 
     <code class="syntax javascript">
       var&nbsp;visitor&nbsp;=&nbsp;Visitor.getInstance("INSERT-MCORG-ID-HERE"); 
      visitor.trackingServer&nbsp;=&nbsp;"INSERT-TRACKING-SERVER-HERE";&nbsp;//&nbsp;same&nbsp;as&nbsp;s.trackingServer 
      visitor.trackingServerSecure&nbsp;=&nbsp;"INSERT-SECURE-TRACKING-SERVER-HERE";&nbsp;//same&nbsp;as&nbsp;s.trackingServerSecure 
      /* 
      &nbsp;==============&nbsp;DO&nbsp;NOT&nbsp;ALTER&nbsp;ANYTHING&nbsp;BELOW&nbsp;THIS&nbsp;LINE&nbsp;!&nbsp;============
     </code> 
     <ul id="ul_769BA118CC244308A805079C2CBECC12"> 
      <li id="li_D366EBDE24CB433EA523DB228CB2FAF1"> <code> "INSERT-MCORG-ID-HERE" </code> - (Required) This Adobe Experience Cloud Organization ID is sent to your administrator when your company is provisioned for the Adobe Experience Cloud. </li> 
      <li id="li_4F9704A6A6EA4334A3758F99B8D67C9D"> <code> "INSERT-TRACKING-SERVER-HERE" </code> - (Required) Your Analytics tracking server. </li> 
      <li id="li_C578420458D649228E54D9809AF62627"> <code> "INSERT-SECURE-TRACKING-SERVER-HERE" </code> - (Required if ssl is enabled) Your Analytics secure tracking server. </li> 
     </ul> 
    </draft-comment> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <img  src="assets/step3_icon.png" id="image_76B61DEABE3849CCB39135FDD7399EAA" /> </td> 
   <td colname="col1"> Use the chosen implementation method to update and deploy page code. </td> 
   <td colname="col2"> <p>Place the page code just after the opening <code> &lt;body&gt; </code> tag on each page you want to track. At a minimum, update the following variables: </p> 
    <ul id="ul_29200A6E8DA14386BDA242AD8B270FEB"> 
     <li id="li_FB24D2CB9241401A83BD13EE342A7810"> <code> var s=s_gi("INSERT-RSID-HERE") </code> </li> 
     <li id="li_463A35BA06CC4618B4AF17CD7E83AED5"> <code> s.pageName="INSERT-NAME-HERE" // for example, s.pageName=document.title </code> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <img  src="assets/step4_icon.png" id="image_B255E5EAE7BB43FC946D0E9DFCA83003" /> </td> 
   <td colname="col1"> Validate the implementation. </td> 
   <td colname="col2"> <p> <a href="../../implement/impl-testing/impl-validation/impl-validation.md" format="dita" scope="local"> Testing and Validation </a> Provides information about validating your implementation. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <img  src="assets/step5_icon.png" id="image_844E896941E2489A943BE10AD710ED36" /> </td> 
   <td colname="col1"> Use the Adobe Experience Cloud debugger to verify that data is being sent. </td> 
   <td colname="col2"> <p>Install the <a href="../../implement/impl-testing/debugger.md#topic_E05CEAF0682E483A9AB147D774CF2188" format="dita" scope="local"> Experience Cloud Debugger </a>. After it is installed, load a page where you have deployed page code and then open the debugger. The debugger displays details about the collection data that was sent. </p> </td> 
  </tr> 
 </tbody> 
</table>

## More Information {#section_64B6A948DF4A4B5E9E1D22549F8C508B}

For information about the differences between [!UICONTROL Experience Platform Launch], [!UICONTROL Dynamic Tag Management], and JavaScript methods, see [Choose an Implementation Method](../../implement/c-implementation-methods/choose-implementation-method.md#concept_97CE27B16410422EB28B4B9CE3B9529B).

For a concise overview of the getting started process and help on quickly setting up your first Analytics report suite, see [Getting Started with Analytics Implementation](https://marketing.adobe.com/resources/help/en_US/dtm/get_started.html) in the Getting Started with Analytics guide. 
