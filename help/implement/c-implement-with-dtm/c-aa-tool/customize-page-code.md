---
description: Use field descriptions in Dynamic Tag Management to customize page code when deploying Analytics.
keywords: Dynamic Tag Management;customize page code;open editor;execute
seo-description: Use field descriptions in Dynamic Tag Management to customize page code when deploying Analytics.
seo-title: Customize page code
solution: Marketing Cloud,Analytics,Target,Dynamic Tag Management
title: Customize page code
uuid: b7cad069-3eb8-4388-b0b0-34f54001e05f
---

# Customize page code

Use field descriptions in Dynamic Tag Management to customize page code when deploying Analytics.

 Add plugins to ensure that the code runs at the same time as the Analytics tool. For more information about the Analytics plugins, see [Implementation Plug-ins](../../../implement/js-implementation/c-mplementation-plug-ins/impl-plugins.md#concept_021F5E4A6BD745AE91E85E7138BE930F).

**[!UICONTROL  `Property`]** > **[!UICONTROL   ![](assets/settings_gear.png)Edit Tool]** > **[!UICONTROL Customize Page Code]** 

<table id="table_A4676A5FEE814DF9A05DA0E56F8B4C6D"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Element </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Open Editor </p> </td> 
   <td colname="col2"> <p>You can insert any JavaScript call that must be triggered before the final <span class="codeph"> s.t()</span> call, which is contained in the <span class="codeph"> s_code</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Execute </p> </td> 
   <td colname="col2"> <p> <b>Before UI settings</b>: Interface settings take precedence over the custom code (for example, if you want to override an eVar if a setting in the interface was enabled). </p> <p> <b>After UI settings</b>: Custom code takes precedence over interface settings. </p> </td> 
  </tr> 
 </tbody> 
</table>

