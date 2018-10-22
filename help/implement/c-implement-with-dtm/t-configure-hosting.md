---
description: You can deploy Dynamic Tag Management using one or more of the available hosting options.
keywords: Analytics Implementation;implementation method;dynamic tag management;dtm;hosting;hosting options;akamai;self hosting;self-hosting;ftp delivery;ftp hosting;library download
seo-description: You can deploy Dynamic Tag Management using one or more of the available hosting options.
seo-title: Configure hosting options
solution: Analytics
title: Configure hosting options
topic: Developer and implementation
uuid: dbf52c04-40b8-4f83-8f14-67a1d32559de
index: y
internal: n
snippet: y
---

# Configure hosting options

You can deploy Dynamic Tag Management using one or more of the available hosting options.

Dynamic Tag Management provides a number of options to host the required JavaScript files.

For detailed information about hosting, see [Embed Code and Hosting Options](https://marketing.adobe.com/resources/help/en_US/dtm/deployment.html) in the Dynamic Tag Management Product Documentation. 

1. On the Embed tab, select a hosting option.

<table id="table_229298207DB64838B6F2477DFFAE073F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Hosting Option </th> 
   <th colname="col2" class="entry"> Description </th> 
   <th colname="col3" class="entry"> Implementation </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Akamai </p> </td> 
   <td colname="col2"> <p> The simplest hosting option to implement. </p> <p>Globally distributed delivery network. </p> <p>Adds additional third-party infrastructure dependencies (DNS lookup, Akamai availability). </p> <p>For more detailed information, see <a href="https://marketing.adobe.com/resources/help/en_US/dtm/akamai.html" format="html" scope="external"> Akamai</a> in the Dynamic Tag Management Product Documentation. </p> </td> 
   <td colname="col3"> 
    <ol id="ol_EF148EF091A645B3962B084963B3C0B0"> 
     <li id="li_7ECE0C331EEE4907A563D581DF1DFEFE">Dynamic Tag Management generates custom JavaScript libraries. </li> 
     <li id="li_8E2C858290EF4665B2F45ACAFA121CB3">Dynamic Tag Management exports the custom JavaScript libraries to Akamai. </li> 
     <li id="li_CE88B10B6E844A56BBB8C575A9363BA9">The target website references the Akamai-hosted Dynamic Tag Management libraries directly at the page level. </li> 
    </ol> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Self-hosting: FTP Delivery </td> 
   <td colname="col2"> <p>A <span class="term"> push</span> approach, whereby Dynamic Tag Management exports custom JavaScript libraries directly to the web content server host via the FTP protocol. </p> <p>This solution requires an FTP server and credentials to be available on the web content server to publish changes to the custom Dynamic Tag Management libraries. </p> <p>For more detailed information, see <a href="https://marketing.adobe.com/resources/help/en_US/dtm/deployment_ftp.html" format="html" scope="external"> FTP</a> in the Dynamic Tag Management Product Documentation. </p> </td> 
   <td colname="col3"> 
    <ol id="ol_60348F9C991D4F2B9457006B0F98C834"> 
     <li id="li_24A141C3C7074BF9897C022A22CAE78C">Dynamic Tag Management generates custom JavaScript libraries. </li> 
     <li id="li_E1E0843060F7447E853EA416A0B033BE">Dynamic Tag Management exports the custom JavaScript libraries to host server via FTP. </li> 
     <li id="li_EAF5D2ABD03B4911A0CFA464AD8791CE">The target website locally references the custom Dynamic Tag Management libraries. </li> 
    </ol> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Self-hosting: Library Download </td> 
   <td colname="col2"> <p>A <span class="term"> pull</span> approach, whereby the application exports custom JavaScript libraries
     <!-- to Amazon S3-->. There, the libraries can be accessed by a hosted server-side process. </p> <p>Additionally, the libraries are available via web download directly from the Dynamic Tag Management interface. </p> <p>This solution requires either a manual retrieval and publication of the Dynamic Tag Management libraries or the creation of an automated process that pulls the libraries from Akamai onto the web content server. </p> <p>This approach takes the most time to set up, but is also the most secure and flexible option. </p> <p>To check if the latest version of your library file is being referenced, use the command </p> <p>For more detailed information, see<a href="https://marketing.adobe.com/resources/help/en_US/dtm/deployment_download.html" format="html" scope="external"> Library Download</a> in the Dynamic Tag Management Product Documentation. </p> </td> 
   <td colname="col3"> 
    <ol id="ol_F40B721306FE473496BD657262DFD585"> 
     <li id="li_4EA4D6B555CE4E9CA476C7550C18C061">Dynamic Tag Management generates custom JavaScript libraries. </li> 
     <li id="li_BA40EBD7AD1546F29D8A209034D06477">Dynamic Tag Management exports the custom JavaScript libraries to Akamai. </li> 
     <li id="li_E107E69E386A40F3B067F9991C2979AF">Custom Dynamic Tag Management libraries are manually or programmatically moved to the web content server. </li> 
     <li id="li_0809038453B544168A20CE09D7E5AC59">The target website locally references the custom Dynamic Tag Management libraries. </li> 
    </ol> </td> 
  </tr> 
 </tbody> 
</table>

   You can use more than one hosting option. For example, you might host your staged files using Akamai, but self-host your production site. Note that each hosting type has its own embed code, and only one embed code can be added to a page. 
