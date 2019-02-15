---
description: The following table contains a list of tasks you need to perform to migrate your implementation.
keywords: Analytics Implementation;appmeasurement;migrate;migrating;javascript
seo-description: The following table contains a list of tasks you need to perform to migrate your implementation.
seo-title: Migrating to AppMeasurement for JavaScript
solution: Analytics
subtopic: JavaScript AppMeasurement
title: Migrating to AppMeasurement for JavaScript
topic: Developer and implementation
uuid: 5be345a8-5a95-4176-a2e6-97139b9b46ce
---

# Migrating to AppMeasurement for JavaScript

The following table contains a list of tasks you need to perform to migrate your implementation.

>[!NOTE]
>
>We recommend migrating to the [Experience Cloud ID Service](../../../implement/js-implementation/c-unique-visitors/visid-service.md#concept_230F8759826E47789EA8DEE08FA09B07) when you migrate to [!DNL AppMeasurement] for JavaScript.

<table id="table_9CB8D4441B294A6485C00A515338CA47"> 
 <thead> 
  <tr> 
   <th colname="col01" class="entry"> Step </th> 
   <th colname="col1" class="entry"> Task </th> 
   <th colname="col2" class="entry"> Where </th> 
   <th colname="col3" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col01"> <img  src="assets/step1_icon.png" id="image_21F30BBFC0A249F8B0E1A50EBBEED77D" width="26px" height="21px" /> </td> 
   <td colname="col1"> Check plug-in compatibility </td> 
   <td colname="col2"> <span class="filepath"> s_code.js</span> </td> 
   <td colname="col3">Some plug-ins are longer supported. See <a href="../../../implement/js-implementation/c-appmeasurement-js/plugins-support.md#concept_E31A189BC8A547738666EB5E00D2252A" format="dita" scope="local"> AppMeasurement Plug-in Support</a> . </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <img  src="assets/step2_icon.png" id="image_FEC5908E05B8457F828A2BCBCE079061" width="26px" height="21px" /> </td> 
   <td colname="col1"> Download the new AppMeasurement </td> 
   <td colname="col2"> Admin Console &gt; Code Manager </td> 
   <td colname="col3"> <p> The download zip contains a minified <span class="filepath"> AppMeasurement.js</span> file, and Javascript files for the Media and Integrate modules. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <img  src="assets/step3_icon.png" id="image_543F5EC1759741FCB02C110B45C41867" width="26px" height="21px" /> </td> 
   <td colname="col1">Copy your <span class="filepath"> s_code.js</span> customization to <span class="codeph"> AppMeasurement.js</span>. </td> 
   <td colname="col2"> <span class="filepath"> s_code.js</span> and <span class="filepath"> AppMeasurement.js</span> </td> 
   <td colname="col3"> <p>Move all code that appears before the <span class="codeph"> DO NOT ALTER ANYTHING BELOW THIS LINE</span> section in <span class="filepath"> s_code.js</span> to the beginning of <span class="filepath"> AppMeasurement.js</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <img  src="assets/step4_icon.png" id="image_C65A6858FB294E2796B93054BEA72BBD" width="26px" height="21px" /> </td> 
   <td colname="col1"> (Optional) Update plug-ins </td> 
   <td colname="col2"> <span class="filepath"> AppMeasurement.js</span> </td> 
   <td colname="col3"> <p>If you are using the getQueryParam plug-in, update these calls to use the new utility, <a href="../../../implement/js-implementation/util-getqueryparam.md#concept_763AD2621BB44A3990204BE72D3C9FA5" format="dita" scope="local"> Util.getQueryParam</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <img  src="assets/step5_icon.png" id="image_3D0FEDBE7FD8481E8E5F9054F742187E" width="26px" height="21px" /> </td> 
   <td colname="col1"> (Optional) Update Media and Integrate modules </td> 
   <td colname="col2"> <p> <span class="filepath"> AppMeasurement.js</span> </p> </td> 
   <td colname="col3"> <p>If you are using either of these modules, copy and paste the code from <span class="filepath"> AppMeasurement_Module_Media.js</span> and/or <span class="filepath"> AppMeasurement_Module_Integrate.js</span> and paste it just before the <span class="codeph"> DO NOT ALTER ANYTHING BELOW THIS LINE</span> in <span class="filepath"> AppMeasurement.js</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <img  src="assets/step6_icon.png" id="image_FCA028848A374C4BA1AF88C6141C9778" width="26px" height="21px" /> </td> 
   <td colname="col1"> Deploy new JavaScript </td> 
   <td colname="col2"> Your website </td> 
   <td colname="col3"> <p>The new JavaScript file can be deployed according to your standard process. Your existing page code is compatible with this version. </p> </td> 
  </tr> 
 </tbody> 
</table>

