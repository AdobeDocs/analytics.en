---
description: Page variables directly populate a report, such as pageName, List Props, List Variables, and so on.
keywords: Analytics Implementation
solution: Analytics
subtopic: Variables
title: Page variables
topic:
uuid:
---


# browserWidth

The  variable displays the width of the browser window.


<!-- 

browserwidth.xml

 -->

This variable is populated after the page code and before *`doPlugins`* is run.

> [!NOTE] This variable should only be read and never set.

You may read these values and copy them into props/eVars, but you should never alter them. This variable is introduced with version H.11 of the JavaScript file.

**Parameters** 

<table id="table_B70F279A8CD240328520E5BD889806BD"> 
 <tbody> 
  <tr> 
   <td> <p> <b>Query Param</b> </p> </td> 
   <td> <p> <b>Value</b> </p> </td> 
   <td> <p> <b>Example</b> </p> </td> 
   <td> <p> <b>Reports Affected</b> </p> </td> 
  </tr> 
  <tr> 
   <td> <p>bw </p> </td> 
   <td> <p>A positive integer </p> </td> 
   <td> <p>1179 </p> </td> 
   <td> <p>Traffic &gt; Technology &gt; Browser Width </p> </td> 
  </tr> 
 </tbody> 
</table>
