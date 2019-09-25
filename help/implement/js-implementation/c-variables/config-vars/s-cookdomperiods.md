---
description: Dynamic variables let you copy values from one variable to another without typing the full values multiple times in the image requests on your site.
keywords: Analytics Implementation
seo-description: Dynamic variables let you copy values from one variable to another without typing the full values multiple times in the image requests on your site.
solution: 
title: Dynamic variables
---

# s.cookieDomainPeriods

The  variable determines the domain on which the [!DNL Analytics] cookies `s_cc` and `s_sq` are set by determining the number of periods in the domain of the page URL. This variable is also used by some plug-ins in determining the correct domain to set the plug-in's cookie. 

The default value for *`cookieDomainPeriods`* is "2". This is the value that is used if *`cookieDomainPeriods`* is omitted. For example, using the domain `www.mysite.com`, *`cookieDomainPeriods`* should be "2". For `www.mysite.co.jp`, *`cookieDomainPeriods`* should be "3".

If *`cookieDomainPeriods`* is set to "2" but the domain contains three periods, the JavaScript file attempts to set cookies on the domain suffix.

For example, if setting *`cookieDomainPeriods`* to "2" on the domain `www.mysite.co.jp`, the `s_cc` and `s_sq` cookies are created on the domain `co.jp`. Because `co.jp` is an invalid domain, almost all browsers reject these cookies. As a consequence, visitor click map data is lost, and the [!UICONTROL Visitor Profile] > [!UICONTROL Technology] > [!UICONTROL Cookies] report indicates that almost 100% of visitors reject cookies.

If *`cookieDomainPeriods`* is set to "3" but the domain contains only two periods, the JavaScript file sets the cookies on the subdomain of the site. For example, if setting *`cookieDomainPeriods`* to "3" on the domain `www2.mysite.com`, the `s_cc` and `s_sq` cookies are created on the domain `www2.mysite.com`. When a visitor goes to another subdomain of your site (such as `www4.mysite.com`), all cookies set with `www2.mysite.com` cannot be read.

>[!NOTE]
>
>Do not include additional subdomains as part of *`cookieDomainPeriods`*. For example, `store.toys.mysite.com` would still have *`cookieDomainPeriods`* set to "2". This variable definition correctly sets the cookies on the root domain, [!DNL mysite.com]. Setting *`cookieDomainPeriods`* to "3" in this example would set cookies on the domain [!DNL toys.mysite.com], which has the same implications as the prior example.

See also [s.fpCookieDomainPeriods](../../../implement/js-implementation/c-variables/configuration-variables.md#concept_0A25BD152B0744989E7C662A95448274). 

|  Max Size  | Debugger Parameter  | Reports Populated  | Default Value  |
|---|---|---|---|
|  N/A  | CDP  | Affects multiple reports as it controls how the visitor ID is stored and handled.  | "2"  |

>[!NOTE]
>
>Some cloud computing services are considered Top-Level Domains, which do not allow cookies to be written. (For example, `compute.amazonaws.com`, `*.herokuapp.com`, `*.googlecode.com`, and so on.) If you implement on those services, you could potentially be affected by Analytics privacy setting that removes users who have blocked all cookies if you don't have your own domain set up (for example, if you're testing your implementation). In this case, any hit where the system has determined that cookies are disabled, non-functional, or inaccessible is opted out and thus excluded from reporting.

## Examples

Setting the variable manually: 

```js
s.cookieDomainPeriods = "3";
```

Several examples to dynamically set the variable if your core JavaScript file hosts both types:

```js
document.URL.indexOf(".co.") > 0 ? s.cookieDomainPeriods = "3" : s.cookieDomainPeriods = "2";
```

```js
s.cookieDomainPeriods = "2"; 
var d=window.location.hostname; 
if(d.indexOf(".co.uk") > 0 || d.indexOf(".com.au") > 0) 
    {s.cookieDomainPeriods = "3";}
```

```js
s.cookieDomainPeriods = "2"; 
if(window.location.indexOf(".co.jp") > 0 || window.location.indexOf(".com.au") > 0) 
    {s.cookieDomainPeriods = "3";}
```

## Pitfalls, Questions, and Tips

* If you notice that visitor click map data is absent, or that the [!UICONTROL Traffic] > [!UICONTROL Technology] > [!UICONTROL Cookies] report shows a large percentage of visitors who reject cookies, check that the value of *`cookieDomainPeriods`* is correct. 

* If *`cookieDomainPeriods`* is higher than the number of sections in the domain, cookies will be set with the full domain. This can cause data loss as visitors switch between subdomains. 
* The *`cookieDomainPeriods`* variable was used in deprecated implementations prior to *`trackingServer`* to set the visitor ID cookie. Though only present in outdated code, failure to correctly define *`cookieDomainPeriods`* in this circumstance puts your implementation at risk of data loss.