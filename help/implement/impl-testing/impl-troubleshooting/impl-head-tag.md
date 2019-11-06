---
description: Analytics code creates an image object, a non-visible image that does not show up on your page.
keywords: Analytics Implementation
seo-description: Analytics code creates an image object, a non-visible image that does not show up on your page.
seo-title: Putting Analytics code in the head tag
solution: Analytics
title: Putting Analytics code in the head tag
topic: Developer and implementation
uuid: e8f91d3c-cb72-454d-9bd4-ff54d83d981f
---

# Putting Analytics code in the head tag

Analytics code creates an image object, a non-visible image that does not show up on your page.

>[!NOTE]
>
>This section applies only to the legacy s_code.js implementation. [AppMeasurement for JavaScript 1.0](/help/implement/js-implementation/c-appmeasurement-js/appmeasure-mjs.md) supports deploying the library and page code in the `<head>` tag.

Previously, a common implementation practice was to place the Analytics JavaScript code between the <head> and </head> tags. By placing the code between these tags it prevented the 1 x 1 pixel image that was returned by the request that sent data into Adobe servers from affecting page layout in any way. Putting code in the document head means the code appears earlier in the code. This lets it execute sooner, which lets you count page views for partial page loads more effectively.

Certain elements of the code require the existence of the body object. Since Web browsers execute code in the order they receive it, if the Analytics JavaScript code is in the document head, it executes before the body object exists. As a result, your implementation does not collect [!UICONTROL ClickMap] data, and automatic tracking of file downloads or [!UICONTROL exit] links are not available. You also do not receive connection type data or visitor home page data. Putting the code in the document head works, but the result is a very limited version of Analytics, and users may wonder why certain reports and tools, including [!UICONTROL ClickMap], aren't recording data.

The Analytics code can be placed anywhere inside BODY tags (<BODY></BODY>) of a well-formed HTML page. Adobe recommends placing the code in a global include file at the top of the page (inside the HTML body tag). The code can be placed anywhere on the page, except as noted below:

* If placed within a table, post the code only within the <td></td> tags. For example, do not place the code between an opening <tr> tag and an opening <td> tag.
* The code that sets the variables must occur after the reference to the s_code.js file.
* Make certain that the [!UICONTROL report suite ID]s in the *`s_account`* variable in the s_code.js file are set correctly. This variable is typically set correctly when downloading code from the Code Manager for a particular report suite, or as supplied by an Adobe Technical Consultant.

If you want to integrate Analytics with Target, the JavaScript include file must be placed at the bottom of the page. The following example shows correct placement of the Analytics code:

```js
<html> 
<head></head> 
<body> 
<!-- Analytics code version: H.20.3.
Copyright 1997-2009 Omniture, Inc. More info available at 
https://www.omniture.com --> 
<script language="JavaScript" type="text/javascript" src="https://www.yourdomain.com/js/s_code.js"></script> 
<script language="JavaScript" type="text/javascript"><!-- 
/* You may give each page an identifying name, server, and channel on 
the next lines. */ 
s.pageName="" 
s.server="" 
s.channel="" 
s.pageType="" 
s.prop1="" 
s.prop2="" 
s.prop3="" 
s.prop4="" 
s.prop5="" 
/* Conversion Variables */ 
s.campaign="" 
s.state="" 
s.zip="" 
s.events="" 
s.products="" 
s.purchaseID="" 
s.eVar1="" 
s.eVar2="" 
s.eVar3="" 
s.eVar4="" 
s.eVar5="" 
/************* DO NOT ALTER ANYTHING BELOW THIS LINE ! **************/ 
var s_code=s.t();if(s_code)document.write(s_code)//--></script> 
<!-- End Analytics code version: H.20.3. --> 
</body> 
</html> 

```

