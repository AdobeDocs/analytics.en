---
description: Dynamic variables let you copy values from one variable to another without typing the full values multiple times in the image requests on your site.
keywords: Analytics Implementation
solution: 
title: Dynamic variables
---


# s.linkInternalFilters

The  variable is used to determine which links on your site are exit links.

It is a comma-separated list of filters that represent the links that are part of the site.

|  Max Size  | Debugger Parameter  | Reports Populated  | Default Value  |
|---|---|---|---|
|  N/A  | N/A  | Paths > Entries & Exits > Exit Links  |  |

> [!NOTE] We had previously suggested setting the linkInternalFilters to javascript:. However, this resulted in all domains being considered external, including the current domain on which the tag resides. If you want several domains to be considered internal, you can add those, as shown in the examples below.

The *`linkInternalFilters`* variable is used to determine whether a link is an exit link, which is defined as any link that takes a visitor away from your site. Whether the target window of an exit link is a pop-up, or the existing window, does not affect whether the link appears in the exit links report. Exit links are only tracked if *`trackExternalLinks`* is set to `"true"`. (See [Link Tracking](https://marketing.adobe.com/resources/help/en_US/dtm/link_tracking.html) in the Dynamic Tag management documentation for information about how DTM handles exit links.) The filters in *`linkInternalFilters`* are not case-sensitive.

The list of filters in *`linkInternalFilters`* applies to the domain and path of any link by default. If *`linkLeaveQueryString`* is set to `"true"`, then the filters apply to the entire URL (domain, path, and query string). The filters are always applied to the absolute path of the URL, even if a relative path is used as the href value.

Be careful that all the domains of your site (and any partners who are using your JavaScript file) are included in *`linkInternalFilters`*. If you do not have all domains included in the list, all links on and to those domains are considered exit links, increasing the server calls sent. If you would like multiple domains or companies to use a single [!DNL AppMeasurement] for JavaScript file, you may consider populating *`linkInternalFilters`* on the page, overriding the value specified in the JavaScript file. If you have vanity domains that immediately redirect to your main domain, those vanity domains do not need to be included in the list.

The following example illustrates how this variable is used. In this example, the URL of the page is `https://www.mysite.com/index.html`.

```js
s.trackExternalLinks=true 
s.linkInternalFilters="mysite.com" 
s.linkExternalFilters="" 
s.linkLeaveQueryString=false 
...
<a href="https://www.mysite.com">Not an Exit Link</a> 
<a href="/careers/job_list.html">Not an Exit Link</a> 
<a href="https://www2.site3.com">Exit Link</a> 
<a href="https://www2.site1.com/partners/">Exit Link</a> 

```

## Syntax and Possible Values

The *`linkInternalFilters`* variable is a comma-separated list of ASCII characters. No spaces are allowed.

```js
s.linkInternalFilters="site1.com[,site2.com[,site3.net[...]]]"
```

## Examples

```js
s.linkInternalFilters="mysite.com"
```

```js
s.linkInternalFilters="mysite.com,mysite.net,vanity1.com"
```

## Configuration Settings

None

## Pitfalls, Questions, and Tips

* Include all domains that the [!DNL AppMeasurement] for JavaScript file may be served under in the filter list.
* Periodically check the [!UICONTROL Paths] > [!UICONTROL Entries & Exits] > [!UICONTROL Exit] Links report to make sure that none of the entries in that report are incorrect.

* Periodically review partner contracts to determine if they contain restrictions on link tracking. For example, you might be prohibited from tracking links that appear in partner display ads. Filter partner links by adding their domain to *`linkInternalFilters`*:

```js
s.linkInternalFilters="mysite.com,mysite.net,mypartner.net/adclick"
```
