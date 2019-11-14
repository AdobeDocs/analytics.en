---
description: Page variables directly populate a report, such as pageName, List Props, List Variables, and so on.
keywords: Analytics Implementation
solution: Analytics
subtopic: Variables
title: Page variables
topic:
uuid:
---

# pageType

The  variable is used only to designate a 404 Page Not Found Error page.

<!-- 

pageType.xml

 -->

<table id="table_0492B136E9D14070A6CA49ED534BCA4C"> 
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
   <td> 20 bytes </td> 
   <td> pageType </td> 
   <td> Paths &gt; Pages &gt; Pages <p>Not Found </p> </td> 
   <td> "" </td> 
  </tr> 
 </tbody> 
</table>

The *`pageType`* variable captures the errant URL when a 404 Error page is displayed, which allows you to quickly find broken links and paths that are no longer valid on the custom site. Set up the *`pageType`* variable on the error page exactly as shown below.

Do not use the page name variable on 404 error pages. The *`pageType`* variable is only used for the 404 Error page.

In most cases, the 404 Error page is a static page that is hard-coded. In these cases, it is important that the reference to the .JS file is set to an appropriate global or relative path/directory.

**Syntax and Possible Values** {#section_C1C59968226446559B05F6EE7374D525}

The only allowable value of *`pageType`* is "errorPage" as shown below.

```js
s.pageType="errorPage"
```

**Examples** {#section_6CE22FCB835B4A19B633B7F67E73A115}

```js
s.pageType="errorPage"
```

**Configuration Settings** {#section_3B304A6D3A6C48F2BE90B4DA92A39DDB}

None

**Pitfalls, Questions, and Tips** {#section_943681AB01FE47BEAC72E93CB60C53C8}

To capture other server-side errors (such as 500 errors), use a prop to capture the error message and put "`500 Error: <URL>`" where `<URL>` is the URL requested, in the *`pageName`* variable. By following this course of action, you can use [!UICONTROL Pathing] reports to see which paths caused users to generate 500 errors. The prop explains which error message is given by the server.

