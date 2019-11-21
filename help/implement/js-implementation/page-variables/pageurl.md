---
description: Page variables directly populate a report, such as pageName, List Props, List Variables, and so on.
keywords: Analytics Implementation
solution: Analytics
subtopic: Variables
title: Page variables
topic:
uuid:
---

# pageURL

The  variable overrides the actual URL of the page.


<!-- 

pageURL.xml

 -->

In rare cases, the URL of the page is not the URL that you would like reported in Analytics.

<table id="table_D4DC6B476FFD4BEEB36A5C6B2D026255"> 
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
   <td> No Limit* </td> 
   <td> <p>G </p> </td> 
   <td> Traffic &gt; Segmentation &gt; Most Popular Pages Paths </td> 
   <td> Page URL </td> 
  </tr> 
 </tbody> 
</table>

> [!NOTE] Although Adobe allows *`pageURL`* values up to 64k, some browsers impose a size limit on the URL of image requests. To prevent truncation of other data, page URLs longer than 255 bytes are split, with the first 255 bytes appearing in the `g=` parameter, with the remaining bytes appearing later in the query sting in the `-g=` query parameter.

**Syntax and Possible Values** {#section_22AF3BF7C2F743549967B0C760A095C0}

The *`pageURL`* variable must be a valid URL, with a valid protocol. The domain will be forced to display in lower-case before being populated in reports, and the query string may be stripped, depending on Analytics settings.

```js
s.pageURL="proto://domain/path?query_string"
```

Only URL-compatible characters are allowed as the page URL.

> [!NOTE] It is strongly advised that you contact your Adobe consultant or Customer Care before using the *`pageURL`* variable for custom purposes.

**Examples** {#section_45158FDA3F8F4574BDEB5CBC9F7E6C97}

```js
s.pageURL="https://mysite.com/home.jsp?id=1224" 

```

```js
s.pageURL="https://www.mysite.com/"
```

**Configuration Settings** {#section_A8F77DAD88164528ACC5C16C066B47DF}

None 

