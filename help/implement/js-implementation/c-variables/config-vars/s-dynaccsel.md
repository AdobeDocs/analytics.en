---
description: Dynamic variables let you copy values from one variable to another without typing the full values multiple times in the image requests on your site.
keywords: Analytics Implementation
seo-description: Dynamic variables let you copy values from one variable to another without typing the full values multiple times in the image requests on your site.
solution: 
title: Dynamic variables
---

# s.dynamicAccountSelection

The  variable lets you dynamically select the report suite based on the URL of each page.

>[!NOTE]
>
>`dynamicAccountSelection` does not work with custom link tracking.

|  Max Size  | Debugger Parameter  | Reports Populated  | Default Value  |
|---|---|---|---|
|  N/A  | N/A  | N/A  | False  |

>[!NOTE]
>
>Both `dynamicAccountList` and `dynamicAccountMatch` are ignored if the `dynamicAccountSelection` variable is not declared or set to 'false.'

## Syntax and Possible Values

```js
s.dynamicAccountSelection=[true|false]
```

Only 'true' and 'false' are allowed as values of *`dynamicAccountSelection`*.

## Examples

```js
s.dynamicAccountSelection=true
```

```js
s.dynamicAccountSelection=false
```

## Configuration Settings

None

## Pitfalls, Questions, and Tips

* Dynamic account selection is not supported by [AppMeasurement for JavaScript](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/appmeasurement-js/appmeasure-mjs.html).

* Always use the [!DNL DigitalPulse Debugger] to determine which report suite is receiving data from each page.
