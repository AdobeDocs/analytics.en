---
description: Developer and implementation documentation for Adobe Analytics.
keywords: android;api;appmeasurement;blackberry;flash;ios;java;livestream;php;REST;sdk;SOAP;video;web services;WSDL;hardcoded;image tag
seo-description: Developer and implementation documentation for Adobe Analytics.
seo-title: Developer
solution: Analytics
title: Developer
topic: Developer and implementation
uuid: 0fd7a504-33b5-4431-b8d0-1d21e8a495dc
---

# Developer

Developer and implementation documentation for Adobe Analytics.

The following table outlines the libraries available to collect Analytics data across all available platforms. For more information, see [Data Collection in Analytics](../../admin/data-collection/usecase-sending-data-to-sc.md#concept_FB8E8398CF9845E6842642361AEA03F8). 

<table id="table_B01E5B7E5DEB42A28AB851E640A6F08E"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Platform </th> 
   <th colname="col2" class="entry"> Data Collection Options </th> 
   <th colname="col3" class="entry"> How to Download </th>
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Web Browser </td> 
   <td colname="col2"> <p>All Experience Cloud customers have access to <a href="https://docs.adobelaunch.com/getting-started" format="http" scope="external"> Launch</a>, which is the standard for deploying JavaScript and HTML page tags for all solutions to your website. </p> <p>Other ways of implementing JavaScript and HTML measurement are described in the <a href="https://marketing.adobe.com/resources/help/en_US/sc/implement/index.html" format="http" scope="external"> Analytics Implementation Guide</a>. </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Web Server </td> 
   <td colname="col2"> <p>You can use native PHP and Java libraries on your web server to send analytics data. </p> <p>The Data Insertion API lets you send XML data directly to the data collection server using HTTP POST and GET, and Data Sources lets you send delimited hit data to an FTP server where it is imported directly to Analytics. </p> 
    <ul id="ul_B602F4D6610D46D6BA65F943E5BA296C"> 
     <li id="li_4F0A3CC0E5CD4F5AAEECF60A3D81C737"> <a href="https://marketing.adobe.com/resources/help/en_US/sc/appmeasurement/php/oms_sc_appmeasure_php.pdf" format="http" scope="external"> PHP AppMeasurement</a> </li> 
     <li id="li_D2431479035F45F4AB4CE0AF11B4C89C"> <a href="https://marketing.adobe.com/resources/help/en_US/sc/appmeasurement/java/oms_sc_appmeasure_java.pdf" format="http" scope="external"> Java AppMeasurement</a> </li> 
     <li id="li_74B5B70A2E7349EE9FB9721442D0C845"> <a href="https://github.com/AdobeDocs/analytics-1.4-apis/blob/master/docs/data-insertion-api/index.md" format="https" scope="external"> Data Insertion API</a> </li> 
     <li id="li_45F309B87FFC40DF9EF0F263C3FB416A"> <a href="https://marketing.adobe.com/resources/help/en_US/sc/datasources/" format="http" scope="external"> Data Sources</a> </li> 
    </ul> </td> 
   <td colname="col3"> <p> <b>PHP</b>: <a href="https://sc.omniture.com/login/" format="https" scope="external"> Log in to Analytics</a> &gt; Admin &gt; Code Manager. </p> <p> <b>Java</b>: <a href="https://sc.omniture.com/login/" format="https" scope="external"> Log in to Analytics</a> &gt; Admin &gt; Code Manager. </p> <p> <b>Data Insertion API</b>: No download, data is sent using web services API. </p> <p> <b>Data Sources</b>: No download, data is uploaded using FTP or web services API. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Mobile Device </td> 
   <td colname="col2"> <p> <p>Important:  As of April 30, 2017, Adobe Bloodhound has been sunset. Starting on May 1, 2017, no additional enhancements and no additional Engineering or Adobe Expert Care support will be provided. </p> </p> <p>Native libraries are provided for iOS, Android, Windows Phone 8, Blackberry, Symbian, and others. </p> 
    <ul id="ul_DB6A44A2FF724B5BB36973FDFB8353A5"> 
     <li id="li_798176C5BBEA440E928D1D7185CAF2C2"><a href="https://marketing.adobe.com/resources/help/en_US/mobile/bloodhound_win_2x/" format="https" scope="external"> Bloodhound 2.2 for Windows</a> </li> 
     <li id="li_C045969CE5784191B4233686FE967E11"><a href="https://marketing.adobe.com/resources/help/en_US/mobile/bloodhound/" format="https" scope="external"> Bloodhound 3.x for Mac</a> </li> 
     <li id="li_B08653F5576D4BC6AAA18D0F31385F0D"><a href="https://marketing.adobe.com/resources/help/en_US/mobile/unity/" format="https" scope="external"> Unity Plug-in for iOS and Android 4.x SDK</a> </li> 
     <li id="li_B33DD2412BC64432812397DEBF216545"><a href="https://marketing.adobe.com/resources/help/en_US/mobile/winu/win_vse_4x.html" format="https" scope="external"> Windows Visual Studio Extensions for Experience Cloud Solutions 4.x SDK</a> </li> 
     <li id="li_98650B809F2645C3B6B1202F40902EDF"><a href="https://marketing.adobe.com/resources/help/en_US/mobile/xamarin/" format="https" scope="external"> Xamarin Components for Experience Cloud Solutions 4.x SDK</a> </li> 
     <li id="li_2B97BA81591747638D620A23881411F6"> <a href="https://marketing.adobe.com/resources/help/en_US/mobile/ios/" format="http" scope="external"> iOS SDK 4.x for Experience Cloud Solutions</a> </li> 
     <li id="li_6323CE2240FD490292B39884BB00559C"> <a href="https://marketing.adobe.com/resources/help/en_US/mobile/android/" format="http" scope="external"> Android SDK 4.x for Experience Cloud Solutions</a> </li> 
     <li id="li_75CE892A178D4BD0A0707579ED3FE97D"><a href="https://marketing.adobe.com/resources/help/en_US/mobile/winu/" format="https" scope="external"> Windows 8.1 Universal App Store</a> </li> 
     <li id="li_C6FDFB0B34A24E979D4C0987D9C9EE0F"><a href="https://marketing.adobe.com/resources/help/en_US/mobile/bb/" format="https" scope="external"> BlackBerry 10 SDK 4.x for Experience Cloud Solutions</a> </li> 
    </ul> </td> 
   <td colname="col3"> <p> Configure your app in Adobe Mobile services so you can download a customized package that includes a pre-populated version of the configuration file. <a href="https://marketing.adobe.com/resources/help/en_US/mobile/ios/?f=requirements" format="https" scope="external"> iOS instructions</a> | <a href="https://marketing.adobe.com/resources/help/en_US/mobile/android/?f=requirements" format="https" scope="external"> Android instructions</a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Flash </td> 
   <td colname="col2"> <p>Flash apps using ActionScript can be measured on the desktop and on the web. </p> <p> <a href="https://marketing.adobe.com/resources/help/en_US/sc/appmeasurement/flash/oms_sc_appmeasure_flash.pdf" format="http" scope="external"> Flash, Flex, and OSMF AppMeasurement</a> </p> </td> 
   <td colname="col3"> <p> <b>Flash/Flex/OSMF</b>: <a href="https://sc.omniture.com/login/" format="https" scope="external"> Log in to Analytics</a> &gt; Admin &gt; Code Manager. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Desktop </td> 
   <td colname="col2"> 
    <ul id="ul_44CAE5F5DEA94EAF9743DDB2863E906F"> 
     <li id="li_02BB8027E4F84E5986066ACCCC3CF261"><a href="https://marketing.adobe.com/resources/help/en_US/mobile/winu/" format="https" scope="external"> Windows 8.1 Universal App Store</a> </li> 
     <li id="li_A3613B71AD2E47CD96C8943117D75B0B"> <a href="https://marketing.adobe.com/resources/help/en_US/sc/appmeasurement/osx/" format="http" scope="external"> OS X AppMeasurement 3.x</a> </li> 
     <li id="li_2FBE124EF9C943E092C1C5FDA5CDDEB8"> <a href="https://marketing.adobe.com/resources/help/en_US/sc/appmeasurement/java/oms_sc_appmeasure_java.pdf" format="http" scope="external"> Java AppMeasurement</a> </li> 
     <li id="li_ED11FA429E70488A80C27455401887DF"> <a href="https://marketing.adobe.com/resources/help/en_US/sc/appmeasurement/dotnet/oms_sc_appmeasure_dotnet.pdf" format="http" scope="external"> Silverlight, .NET, XBOX, and Windows Phone 7 AppMeasurement</a> </li> 
    </ul> </td> 
   <td colname="col3"> <p> <b>4.x Windows 8.1 Universal App Store</b>: Configure your app in Adobe Mobile services so you can download a customized package that includes a pre-populated version of the configuration file. </p> <p> <b>3.x Windows 8</b>: See <a href="https://marketing.adobe.com/developer/en_US/get-started/mobile/c-measuring-mobile-applications" format="https" scope="external"> Measuring and Optimizing Mobile Applications</a> on Developer Connection for download links. Make sure you log in to see the downloads. </p> <p> <b>3.x OS X</b>: See <a href="https://marketing.adobe.com/developer/en_US/get-started/mobile/c-measuring-mobile-applications" format="https" scope="external"> Measuring and Optimizing Mobile Applications</a> on Developer Connection for download links. Make sure you log in to see the downloads. </p> <p> <b>Java</b>: <a href="https://sc.omniture.com/login/" format="https" scope="external"> Log in to Analytics</a> &gt; Admin &gt; Code Manager. </p> <p> <b>Silverlight, .NET, XBOX</b>: <a href="https://sc.omniture.com/login/" format="https" scope="external"> Log in to Analytics</a> &gt; Admin &gt; Code Manager. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Image Tags </td> 
   <td colname="col2"> <p>You can insert image tags directly into HTML content when using a library is not possible. </p> 
    <ul id="ul_D406BCF91A40405F8F4408DCD2CBF8F1"> 
     <li id="li_B8BE3752096F4273B4B71816267ADCDD"> <a href="https://marketing.adobe.com/resources/help/en_US/sc/implement/?f=implscwojs" format="http" scope="external"> Implement Analytics without JavaScript</a> </li> 
    </ul> </td> 
   <td colname="col3"> <p>No additional code required. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Video </td> 
   <td colname="col2"> <p>Video measurement across all platforms is available in the following guides: </p> 
    <ul id="ul_5C56F82F45264F63ABA184C48B27EE18"> 
     <li id="li_140B692CA3BE476BA024C37E7AE4872F"> <a href="https://marketing.adobe.com/resources/help/en_US/sc/appmeasurement/hbvideo/" format="http" scope="external"> Heartbeat video measurement</a> (latest version) </li> 
     <li id="li_021D77CB25A54647A71F4AE7144EE788"> <a href="https://marketing.adobe.com/resources/help/en_US/sc/appmeasurement/video/" format="http" scope="external"> Milestone video measurement</a> </li> 
    </ul> </td> 
   <td colname="col3"> <p> <b>Heartbeat Video</b>: See <a href="https://marketing.adobe.com/resources/help/en_US/sc/appmeasurement/hbvideo/?f=video_implementation" format="http" scope="external"> Video Heartbeat Developer Guide</a> and follow the instructions for your platform. </p> <p> <b>Milestone Video</b>: See <a href="https://marketing.adobe.com/resources/help/en_US/sc/appmeasurement/video/?f=video_developer" format="http" scope="external"> Measuring Video for Developers</a> and follow the instructions for your platform. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Release Notes {#section_3BFF38D0A20443E089F795CB04ADE093}

Release notes for all libraries are available at [AppMeasurement and Mobile Release History](https://marketing.adobe.com/resources/help/en_US/sc/appmeasurement/release/).

## Analytics REST and SOAP Web Services {#section_3EF70897B7874CFCBC93724651FBBD93}

Additional developer documentation is available [here](https://github.com/AdobeDocs/analytics-2.0-apis). 

|  API  | Description  |
|---|---|
|  [Reporting API](https://marketing.adobe.com/developer/en_US/documentation/analytics-reporting-1-4)  | Run custom reports on your Analytics data.  |
|  [Admin API](https://marketing.adobe.com/developer/en_US/documentation/analytics-administration-1-4)  | Manage report suites, permissions, and company settings.  |
|  [Classifications API](https://marketing.adobe.com/developer/en_US/documentation/classifications-1-4-saint)  | Import and export your classification data  |
|  [Data Feeds API](https://marketing.adobe.com/developer/en_US/documentation/data-feeds)  | Retrieve configuration details and the status of data feed processing.  |
|  [Data Insertion API](https://marketing.adobe.com/developer/en_US/documentation/data-insertion)  | Import data into Analytics without JavaScript beacons.  |
|  [Data Sources API](https://marketing.adobe.com/developer/en_US/documentation/data-sources)  | Import data from external sources to enhance Analytics reporting.  |
|  [Data Warehouse API](https://marketing.adobe.com/developer/en_US/documentation/data-warehouse)  | Request reports that display advanced data relationships.  |
|  [Data Workbench Query API](https://marketing.adobe.com/developer/en_US/documentation/data-workbench-query-api)  | Access processed results of a dataset.  |
|  [Segments API](https://marketing.adobe.com/developer/en_US/documentation/segments-1-4)  | Create, get, and delete segments.  |
|  [Analytics Livestream](https://marketing.adobe.com/developer/en_US/documentation/analytics-live-stream)  | Provides a live stream of partially-processed Analytics data.  |

