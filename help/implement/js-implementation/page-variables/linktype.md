---
description: Page variables directly populate a report, such as pageName, List Props, List Variables, and so on.
keywords: Analytics Implementation
subtopic: Variables
title: Page variables
topic:
uuid:
---


# linkType

The  variable is an optional variable used in link tracking that determines which report a link name or URL appears (custom, download, or exit links).


<!-- 

linkType.xml

 -->

The *`linkType`* variable is not normally needed because the second parameter in the *`tl()`* function replaces it.

<table id="table_3D1A2FC1CECD4709BE2F9E32AC2DC730"> 
 <thead> 
  <tr> 
   <th class="entry"> Max Size </th> 
   <th class="entry"> Debugger Parameter </th> 
   <th class="entry"> Reports Populated </th> 
   <th class="entry"> Default Value </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td> One character </td> 
   <td> pe=[lnk_o|lnk_d|lnk_e] </td> 
   <td> <p>File Downloads </p> <p>Custom Links </p> <p>Exit Links </p> </td> 
   <td> "" </td> 
  </tr> 
 </tbody> 
</table>

Custom links send data to Analytics. The *`linkType`* variable (or the second parameter in the *`tl()`* function) is used to identify the report in which the link name or URL appears ( [!UICONTROL Custom], [!UICONTROL Download], or [!UICONTROL Exit Links] report).

For exit and download Links, the *`linkType`* variable is automatically populated depending on whether the link clicked is an exit or download link. A custom link may be configured to send data to any of the three reports with this variable or with the second parameter in the *`tl()`* function. By setting *`linkType`* to 'o,' 'e,' or 'd,' the *`linkName`* or link URL is sent to the [!UICONTROL Custom Links], [!UICONTROL Exit Links], or [!UICONTROL File Downloads] report respectively.

**Syntax and Possible Values** {#section_18DB3A8083FB4F75B970055ED336DA4E}

The *`linkType`* variable syntax depends on whether you use XML or a query string.

If you are using XML, the variable may only contain a single character, namely 'o,' 'e,' or 'd.'

```js
s.tl(this,'o','Link Name');
```

If you are using the query-string `pe`, you need to use `lnk_d`, `lnk_e`, or `lnk_o`.

**Examples** {#section_242B5DFFD1C9462A9A8EB1556B2E3160}

```js
<a href="index.html" onClick=" 
 var s=s_gi('rsid'); **see note below on the rsid** 
 s.tl(this,'o','Link Name'); 
 ">My Page</a> 

```

**Configuration Settings** {#section_59738AD1B5E94294B8D36F4E772DEDB3}

None

**Pitfalls, Questions, and Tips** {#section_F0D01DDE3FDA486C987162DA50A79C45}

* If *`linkType`* is not specified, custom links ('o') is assumed.
