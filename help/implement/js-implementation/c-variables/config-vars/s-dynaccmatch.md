---
description: Dynamic variables let you copy values from one variable to another without typing the full values multiple times in the image requests on your site.
keywords: Analytics Implementation
solution: 
title: Dynamic variables
---

# s.dynamicAccountMatch

The  variable uses the DOM object to retrieve the section of the URL to which all rules in  are applied.

This variable is only valid when *`dynamicAccountSelection`* is set to 'True.' Since the default value is [!DNL window.location.host], this variable is not required for [!UICONTROL Dynamic Account Selection] to work. For additional information, see [dynamicAccountList](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/appmeasurement-js/appmeasure-mjs.html).

The rules found in `dynamicAccountList` are applied to the value of `dynamicAccountMatch`. If `dynamicAccountMatch` only contains [!DNL window.location.host] (default), the rules in `dynamicAccountList` apply only to the domain of the page.

|  Max Size  | Debugger Parameter  | Reports Populated  | Default Value  |
|---|---|---|---|
|  N/A  | N/A  | N/A  | window.location.host  |

## Syntax and Possible Values

The `dynamicAccountMatch` variable is usually populated by the Adobe consultant who provides the AppMeasurement for JavaScript file. However, the values listed below may be applied at any time.

```js
s.dynamicAccountMatch=[DOM object]
```

|  Description  | Value  |
|---|---|
|  Domain (default)  | window.location.host  |
|  Path  | window.location.pathname  |
|  Query String  | (window.location.search?window.location.search:"?")  |
|  Domain and Path  | window.location.host+window.location.pathname  |
|  Path and Query String  | window.location.pathname+(window.location.search?window.location.search:"?")  |
|  Full URL  | window.location.href  |

## Examples

```js
s.dynamicAccountMatch=window.location.pathname
```

```js
s.dynamicAccountMatch=window.location.host+window.location.pathname
```

## Configuration Settings

None

## Pitfalls, Questions, and Tips

* Dynamic account selection is not supported by [AppMeasurement for JavaScript](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/appmeasurement-js/appmeasure-mjs.html).

* When pages are saved to a hard drive, [!DNL window.location.host] is empty, causing those page views to be sent to the default report suite (in `s_account`).

* When a page is translated via a web-based translation engine, such as Google, the [!UICONTROL Dynamic Account Selection] does not work as designed. For more precise tracking, populate the [!UICONTROL s_account]variable server-side.
