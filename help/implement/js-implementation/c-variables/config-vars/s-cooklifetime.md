---
description: Dynamic variables let you copy values from one variable to another without typing the full values multiple times in the image requests on your site.
keywords: Analytics Implementation
seo-description: Dynamic variables let you copy values from one variable to another without typing the full values multiple times in the image requests on your site.
solution: 
title: Dynamic variables
---

# s.cookieLifetime

The  variable is used by both JavaScript and data collection servers in determining the lifespan of a cookie.

|  Max Size  | Debugger Parameter  | Reports Populated  | Default Value  |
|---|---|---|---|
|  N/A  | cl  | Traffic > Technology > Cookies All visitor-related reports  | ""  |

If *`cookieLifetime`* is set, it overrides any other cookie expirations for both JavaScript and data collection servers, with one exception, described below. The *`cookieLifetime`* variable can have one of three values:

* [!DNL Analytics] Cookies 
* Cookies 
* JavaScript Settings and Plugins

## Syntax and Possible Values

```js
s.cookieLifetime="value"
```

The possible values are listed as follows:

* "" 
* "NONE" 
* "SESSION" 
* An integer representing the number of seconds until expiration

## Examples

```js
s.cookieLifetime="SESSION"
```

```js
s.cookieLifetime="86400" // one day in seconds
```

## Configuration Settings

None

## Pitfalls, Questions, and Tips

*`cookieLifetime`* affects [!DNL Analytics] tracking. If, for example, *`cookieLifetime`* is two days, then monthly, quarterly, and yearly unique visitor reports will be incorrect. Use caution when setting *`cookieLifetime`*. 
