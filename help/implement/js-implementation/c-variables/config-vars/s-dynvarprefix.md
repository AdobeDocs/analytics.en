---
description: Dynamic variables let you copy values from one variable to another without typing the full values multiple times in the image requests on your site.
keywords: Analytics Implementation
seo-description: Dynamic variables let you copy values from one variable to another without typing the full values multiple times in the image requests on your site.
solution: 
title: Dynamic variables
---

# s.dynamicVariablePrefix {#concept_38C1F2452DDB47FCA8F458BE1398E276}

The  variable allows deployment to flag variables, which should be populated dynamically.

Cookies, request headers, and image query string parameters are available to be populated dynamically.

|  Max Size  | Debugger Parameter  | Reports Populated  | Default Value  |
|---|---|---|---|
|  N/A  | D=  | Any  | D=  |

## Syntax and Possible Values

```js
s.prop1="D=User-Agent"
```

OR USE CUSTOM FLAG FOR DYNAMIC VARIABLES

```js
s.dynamicVariablePrefix=".."
```

## Examples

```js
s.prop1="D=User-Agent"
```

OR USE CUSTOM FLAG FOR DYNAMIC VARIABLES

```js
s.dynamicVariablePrefix=".."
```

```js
s.prop1="..User-Agent"
```

## Pitfalls, Questions, and Tips

* Dynamic variables can be used to significantly reduce the total length of the URL by copying values into other variables.

* Dynamic variables can be used to collect data from headers and cookies not otherwise available for data collection.
