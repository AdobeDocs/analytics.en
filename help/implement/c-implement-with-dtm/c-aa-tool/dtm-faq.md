---
description: A FAQ about the automatic configuration of the Adobe Analytics deployment. The automatic configuration method manages the AppMeasurement code for you.
keywords: Dynamic Tag Management;plugins;staging;effect on current settings;revision history;potential pitfalls;report suite id;currency code;tracking server;ssl tracking server;custom code;library management
seo-description: A FAQ about the automatic configuration of the Adobe Analytics deployment. The automatic configuration method manages the AppMeasurement code for you.
seo-title: FAQs about the Adobe Analytics Tool
solution: Marketing Cloud,Analytics,Target,Dynamic Tag Management
title: FAQs about the Adobe Analytics Tool
uuid: 8fcef893-e305-4a95-a033-9066a56b09cd
index: y
internal: n
snippet: y
---

# FAQs about the Adobe Analytics Tool

A FAQ about the automatic configuration of the Adobe Analytics deployment. The automatic configuration method manages the AppMeasurement code for you.

<table id="table_A50D00E2C47A473B92DA800FB08FE640"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Question </th> 
   <th colname="col2" class="entry"> Answer </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> Where do I put my plugins when implementing Adobe Analytics via DTM? </p> </td> 
   <td colname="col2"> <p> If using DTM to manually host the <span class="codeph"> s_code</span>, plugins can be added in the same editor as the hosted <span class="codeph"> s_code</span>, just as it would be in a typical Adobe Analytics implementation. </p> <p>However, it is also an option to place the plugins in the editor within the <span class="term"> Customize Page Code</span> section of the tool settings. Both implementation methods should be equally effective. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>If I make configuration changes in the new version of the tool, can I test in staging before publishing to production? </p> </td> 
   <td colname="col2"> <p>Yes. </p> <p>All changes can be tested in staging just like you normally would before deploying to a production environment. If you choose not to publish, because you notice issues in staging, the production code will continue to function as it did before the new integration was released. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>If I switch from manual configuration (the default setting for existing tools) to automatic configuration, will my current settings be affected? </p> </td> 
   <td colname="col2"> <p>No. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>If I switch from manual library management to Managed by Adobe, will my current settings or code be affected? </p> </td> 
   <td colname="col2"> <p>Any user code that you have specified is overwritten with the base <span class="keyword"> AppMeasurement</span> library. You must move this code to the new <span class="wintitle"> Custom Page Code</span> section at the end of the tool configuration so that the code continues executing. This method allows the <span class="keyword"> AppMeasurement</span> library to be managed (and upgraded) separately from the user's custom code. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Will the revision history for the <span class="keyword"> Adobe Analytics</span> tool be retained when the new integration is released? </p> </td> 
   <td colname="col2"> <p>Yes. </p> </td> 
  </tr> 
 </tbody> 
</table>

See [Add Adobe Analytics Tool](../../../implement/c-implement-with-dtm/c-aa-tool/analytics-dtm.md#concept_FBA6679A0B79490F8296437F11E5E4F8) for configuration information.

## Potential Pitfalls {#section_201BF9E0EB7D4BC2B72A617543C2030B}

There is a small chance that the integration could cause data collection issues if you currently use [!DNL Adobe Analytics]. These issues could arise only if you publish your library to production subsequent to the release. (Production code remains intact until publishing occurs.)

To avoid these issues, ensure that:

* Report suite IDs are correctly entered in the tool. 
* Report suite IDs in the tool match the IDs in the [!DNL AppMeasurement] code. 
* The currency code, character set, tracking server, and SSL tracking server configuration fields are correctly set with supported values. 
* Custom code is defined in [!DNL Library Management].

