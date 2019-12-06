---
description: Page variables directly populate a report, such as pageName, List Props, List Variables, and so on.
keywords: Analytics Implementation
subtopic: Variables
title: Page variables
topic:
uuid:
---

# pageName

The  variable contains the name of each page on your site.


<!-- 

pageName.xml

 -->

<table id="table_0D09BAEC2FFD43F7905ED3649B3F8E05"> 
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
   <td> 100 bytes </td> 
   <td> pageName </td> 
   <td> <p>Pages </p> <p>Paths </p> </td> 
   <td> page URL </td> 
  </tr> 
 </tbody> 
</table>

The *`pageName`* variable should be populated with a value that business users recognize. In most cases the *`pageName`* value is not the URL or the path to the file. Common *`pageName`* values include names such as "Home Page," "Checkout," "Purchase Thank you," or "Registration."

Be careful not to allow new-line, -em or -en dashes, or any HTML characters to appear in the page name and other variables. Some browsers send new line characters while others don't, which causes the data in Analytics to be split between two seemingly identical page names. Many word processors and email clients will automatically convert a hyphen into an -en or -em dash when typing. Since -en and -em dashes are illegal characters in Analytics variables (ASCII characters with codes above 127), Analytics won't record the page name containing the illegal character and show the URL instead.

If *`pageName`* is left blank, the URL is used to represent the page name. Leaving *`pageName`* blank is often problematic because the URL may not always be the same for a page `www.mysite.com` and `mysite.com` are the same page with different URLs).

**Syntax and Possible Values** {#section_7A61EE70F1A84D26B414404998C84BA8}

The *`pageName`* variable should contain a useful identifier for business users of Analytics.

```js
s.pageName="page_name"
```

There are no limitations on *`pageName`* outside of the standard variable limitations.

**Examples** {#section_8BB4F86F84E246A08B72DEC47FFC0765}

```js
s.pageName="Search Results" 

```

```js
s.pageName="Standard Offer List"
```

**Configuration Settings** {#section_58CBC68C805344A999EB47455FEBA8D5}

Administrators have the ability to change the visible page name in Analytics with the [!UICONTROL Name Pages] tool, which is potentially dangerous and may negatively affect your reports. Please contact Adobe Customer Care before using the [!UICONTROL Name Pages] tool.

**Pitfalls, Questions, and Tips** {#section_BB41DC9682C34385B9CAA80D5257C113}

Make sure the *`pageName`* doesn't contain illegal characters.
