---
description: Dynamic variables let you copy values from one variable to another without typing the full values multiple times in the image requests on your site.
keywords: Analytics Implementation
solution: 
title: Dynamic variables
---

# s.linkExternalFilters

If your site contains many links to external sites, and you do not want to track all exit links, use  to report on a specific subset of exit links.

|  Max Size  | Debugger Parameter  | Reports Populated  | Default Value  |
|---|---|---|---|
|  N/A  | N/A  | Paths > Entries & Exits > Exit Links  | ""  |

The *`linkExternalFilters`* variable is an optional variable used in conjunction with *`linkInternalFilters`* to determine whether a link is an exit link. An exit link is defined as any link that takes a visitor away from your site. Whether the target window of an exit link is a popup or the existing window, it does not affect whether the link appears in the exit links report. Exit links are tracked only if *`trackExternalLinks`* is set to 'true.' The filters in *`linkExternalFilters`* and *`linkInternalFilters`* are case insensitive.

> [!NOTE] If you don't want to use *`linkExternalFilters`*, delete it or set it to "".

The filters list in *`linkExternalFilters`* and *`linkInternalFilters`* apply to the domain and path of any link by default. If *`linkLeaveQueryString`* is set to 'true,' the filters apply to the entire URL (domain, path, and query string). These filters are always applied to the absolute path of the URL, even if a relative path is used as the href value.

Most companies find that *`linkInternalFilters`* gives them enough control over exit links that they don't need *`linkExternalFilters`*. Using *`linkExternalFilters`* simply decreases the likelihood that an exit link is considered external. If *`linkExternalFilters`* has a value, then a link is considered only external if it does not match *`linkInternalFilters`* and does match *`linkExternalFilters`*.

The following example illustrates how this variable is used. In this example, the URL of the page is `https://www.mysite.com/index.html`.

```js
s.trackExternalLinks=true 
s.linkInternalFilters="javascript:,mysite.com" 
s.linkExternalFilters="site1.com,site2.com,site3.com/partners" 
s.linkLeaveQueryString=false 
...
<a href="https://www.mysite.com">Not an Exit Link</a> 
<a href="/careers/job_list.html">Not an Exit Link</a> 
<a href="https://www2.site3.com">Not an Exit Link</a> 
<a href="https://www.site1.com">Exit Link</a> 
<a href="https://www2.site3.com/partners/offer.asp">Exit Link</a> 

```

## Syntax and Possible Values

The *`linkExternalFilters`* variable is a comma-separated list of ASCII characters. No spaces are allowed.

```js
s.linkExternalFilters="site1.com[,site2.com[,site3.net[...]]]"
```

Any portion of a URL might be included in *`linkExternalFilters`*, separated by commas.

## Examples

```js
s.linkExternalFilters="partnersite.com,partnertwo.net/path/"
```

```js
s.linkExternalFilters=""
```

## Configuration Settings

None

## Pitfalls, Questions, and Tips

* Using *`linkExternalFilters`* can result in fewer links on your site being exit links. Do not use this variable in place of *`linkInternalFilters`* to force internal links to become exit links.

* If *`linkExternalFilters`* should be applied to the query string of a link, make sure *`linkLeaveQueryString`* is set to 'true.' See [linkLeaveQueryString](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-account.html) before setting to `"true"`.

* To disable exit link tracking, set *`trackExternalLinks`* to `"false"`.
