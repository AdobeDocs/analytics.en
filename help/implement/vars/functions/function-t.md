---
description: The s.t() function is what compiles all the variables defined on that page into an image request and sends it to our servers.
keywords: track;Analytics Implementation;page tracking;track page
subtopic: Functions
title: The s.t() Function - Page Tracking
topic: Developer and implementation
uuid: 67696e46-1e0d-4200-bfad-4217d1023948
---

# The s.t() Function - Page Tracking

The s.t() function is what compiles all the variables defined on that page into an image request and sends it to our servers.

## Properties of the Function {#section_DB1F3E216DCD4E12AE42BBDCD25B9626}

* Removing the [!UICONTROL s.t()] call prevents any data from reaching [!DNL Analytics]. Multiple [!UICONTROL s.t()] calls fires multiple image requests (doubling the reported traffic on your site).

* If you wish to fire more than one image request on a single page load, using the [!UICONTROL s.tl()] function is recommended.
* Triggering this function always increases [!UICONTROL pageviews]and always include the [!UICONTROL s.pageName] variable.

## Implementation {#section_F75C7BD4A8954CD5BE066C6B88A4A01C}

Upon generating code within the [!UICONTROL code manager], you are given the following at the bottom of the page code:

```js
var s_code=s.t();if(s_code)document.write(s_code)//--></script> 
<script language="JavaScript" type="text/javascript"><!--if(navigator.appVersion.indexOf('MSIE')>=0)document.write(unescape('%3C')+'\!-'+'-')//--></script> 
<noscript><img src="https://yournameserver.112.2o7.net/b/ss/yourreportsuiteid/1/H.23.6--NS/0" height="1" width="1" border="0" alt="" /></noscript> 

```

Each line of code has a specific purpose:

```js
var s_code=s.t();if(s_code)document.write(s_code)//-->
```

This line of code is what actually fires the Javascript function. The [!UICONTROL s_code] variable and it's accompanying document.write method is for browsers that don't support image objects (Netscape browsers prior to version 3 and Internet Explorer prior to version 4; estimated less than .5% of all internet users).

```js
<script language="JavaScript" type="text/javascript"><!--if(navigator.appVersion.indexOf('MSIE')>=0)document.write(unescape('%3C')+'\!-'+'-')//--></script> 
<noscript><img  
src="https://yournameserver.112.2o7.net/b/ss/yourreportsuiteid/1/H.23.6--NS/0" height="1" width="1" border="0" alt="" />
```

For any additional questions about the [!UICONTROL s.t()] function, contact your organization's Account Manager. They can arrange a meeting with an Adobe Implementation Consultant, who can provide assistance.
