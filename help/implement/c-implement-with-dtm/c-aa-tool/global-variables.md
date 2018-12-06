---
description: Field descriptions and information about variables when using Dynamic Tag Management to deploy Adobe Analytics.
keywords: Dynamic Tag Management;global variables;server variable;evar;props;dynamic variable prefix;dynamic variable
seo-description: Field descriptions and information about variables when using Dynamic Tag Management to deploy Adobe Analytics.
seo-title: Global variables
solution: Marketing Cloud,Analytics,Dynamic Tag Management
title: Global variables
uuid: d759320a-96ee-4073-b5fd-5257b7033003
index: y
internal: n
snippet: y
---

# Global variables

Field descriptions and information about variables when using Dynamic Tag Management to deploy Adobe Analytics.

These variables fire on all page load rule beacons. You can accomplish the same effect by using a [Page-Load rule](../../../implement/c-implement-with-dtm/c-rules/t-rules-page-conditions.md#task_69B41CB230EE4530A755D91233F73706) set to fire on all pages. These variables might not fire in [Direct-Call](../../../implement/c-implement-with-dtm/c-rules/t-rules-direct-conditions.md#task_85EB8F01775A402BA53B8298F0AADA09) and [Event-Based](../../../implement/c-implement-with-dtm/c-rules/t-rules-event-conditions.md#task_A122DE72110F4579A91F9D96D92D39FC) rules.

## Global Variables - Field Descriptions {#section_2917F62FCC8D43F982B2612A702DEF81}

**[!UICONTROL  *`Property`*]** > **[!UICONTROL   ![](assets/settings_gear.png)

Edit Tool]** > **[!UICONTROL Global Variables]** 

<table id="table_04BEB6895A4F4D46A2F0B202179173AF"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Element </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Server </p> </td> 
   <td colname="col2"> <p>The predefined variable populates the <span class="wintitle"> Servers</span> dimension in Adobe Analytics. See [Page Variables](/help/implement/js-implementation/c-variables/page-variables.md)</p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>eVars </p> </td> 
   <td colname="col2"> <p>[eVar variables](/help/implement/js-implementation/c-variables/page-variables.md) are used for building custom conversion reports. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p>Props </p> </td> 
   <td colname="col2"> <p>[Prop variables](/help/implement/js-implementation/c-variables/page-variables.md) are used for building custom traffic reports. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Dynamic Variable Prefix </p> </td> 
   <td colname="col2"> <p> A special prefix to the start of the value. The default prefix is "D=". See [Dynamic Variables](/help/implement/js-implementation/c-variables/dynvars-overview.md)</p> </td> 
  </tr> 
 </tbody> 
</table>

