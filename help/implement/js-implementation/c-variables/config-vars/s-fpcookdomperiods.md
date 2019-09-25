---
description: Dynamic variables let you copy values from one variable to another without typing the full values multiple times in the image requests on your site.
keywords: Analytics Implementation
seo-description: Dynamic variables let you copy values from one variable to another without typing the full values multiple times in the image requests on your site.
solution: 
title: Dynamic variables
---

# s.fpCookieDomainPeriods

The  variable is for cookies set by JavaScript (s_sq, s_cc, plug-ins) that are inherently first-party cookies even if your implementation uses the third-party 2o7.net or omtrdc.net domains. 

The *`fpCookieDomainPeriods`* variable should never be dynamically set . If you use *`cookieDomainPeriods`*, it is good practice to specify a value for *`fpCookieDomainPeriods`* as well. *`fpCookieDomainPeriods`* inherits the *`cookieDomainPeriods`* value. Note that *`fpCookieDomainPeriods`* does not affect the domain on which the visitor ID cookie is set, even if your implementation treats this as a first-party cookie.

The name " *`fpCookieDomainPeriods`*" refers to the number of periods (".") in the domain when the domain begins with "www." For example, `www.mysite.com` contains two periods, while `www.mysite.co.jp` contains three periods. Another way to describe the variable is the number of sections in the main domain of the site (two for `mysite.com` and three for `mysite.co.jp`).

The [!DNL AppMeasurement] for JavaScript file uses the *`fpCookieDomainPeriods`* variable to determine the domain with which to set first-party cookies other than the [!UICONTROL visitor ID] (s_vi) cookie. There are at least two cookies affected by this variable, including s_sq and s_cc (used for visitor click map and cookie checking respectively). Cookies used by plug-ins such as [!UICONTROL getValOnce] are also affected. 

|  Max Size  | Debugger Parameter  | Reports Populated  | Default Value  |
|---|---|---|---|
|  N/A  | N/A  | N/A  | cookieDomainPeriods  |

## Sample Code for Setting Cookie Domain Variables

```js
s.fpCookieDomainPeriods="2" 
var d=window.location.hostname 
if(d.indexOf('.co.uk')>-1||d.indexOf('.com.au')>-1) 
  s.fpCookieDomainPeriods="3" 

```

## Syntax and Possible Values

The *`cookieDomainPeriods`* variable is expected to be a string, as shown below.

```js
s.fpCookieDomainPeriods="3"
```

## Examples

```js
s.fpCookieDomainPeriods="3"
```

```js
s.fpCookieDomainPeriods="2"
```

## Configuration Settings

None 