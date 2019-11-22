---
description: Page variables directly populate a report, such as pageName, List Props, List Variables, and so on.
keywords: Analytics Implementation
solution: Analytics
subtopic: Variables
title: Page variables
topic:
uuid:
---

# browserHeight

The  variable displays the height of the browser window.


<!-- 
browserheight.xml
-->

This variable is populated after the page code and before *`doPlugins`* is run.

> [!NOTE] This variable should only be read and never set.

You may read these values and copy them into props/eVars, but you should never alter them. This variable is introduced with version H.11 of the JavaScript file.

**Parameters** 

<table id="table_94598A2204CF42FF9DD14D353D5C0468"> 
 <thead> 
  <tr> 
   <th class="entry"> Query Param </th> 
   <th class="entry"> Value </th> 
   <th class="entry"> Example </th> 
   <th class="entry"> Reports Affected </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td> <p>bh </p> </td> 
   <td> <p>A positive integer </p> </td> 
   <td> <p>865 </p> </td> 
   <td> <p>Traffic &gt; Technology &gt; Browser Height </p> </td> 
  </tr> 
 </tbody> 
</table>

