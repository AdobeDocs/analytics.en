---
description: Dynamic variables let you copy values from one variable to another without typing the full values multiple times in the image requests on your site.
keywords: Analytics Implementation
seo-description: Dynamic variables let you copy values from one variable to another without typing the full values multiple times in the image requests on your site.
solution: 
title: Dynamic variables
---

# s.trackInlineStats

The  variable determines whether ClickMap data is gathered.

If *`trackInlineStats`* is 'true,' data about the page and link clicked are stored in a cookie called s_sq. If 'false,' s_sq will have a value of "[[B]]," which is considered null.

|  Max Size  | Debugger Parameter  | Reports Populated  | Default Value  |
|---|---|---|---|
|  N/A  | N/A  | ClickMap  | False  |

## Syntax and Possible Values

```
js
s.trackInlineStats=true|false

```

The *`trackInlineStats`* variable is expected to be either 'true' or 'false.'

## Examples

```js
s.trackInlineStats=true
```

```js
s.trackInlineStats=false
```

## Configuration Settings

None 
