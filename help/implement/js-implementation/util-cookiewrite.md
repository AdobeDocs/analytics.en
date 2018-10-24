---
description: Writes a value to a cookie.
keywords: Analytics Implementation
seo-description: Writes a value to a cookie.
seo-title: Util.cookieWrite
solution: Analytics
subtopic: JavaScript AppMeasurement
title: Util.cookieWrite
topic: Developer and implementation
uuid: cb23e1de-42a7-48e8-aa20-628980eb41ac
index: y
internal: n
snippet: y
---

# Util.cookieWrite

Writes a value to a cookie.

 **Syntax:**

```
s.Util.cookieWrite(key, value [,expire])
```

**Parameters:** 

|  Parameter  | Description  |
|---|---|
|  key  | (required) key to write value for in cookies.  |
|  value  | (optional) value to write to cookies.  |
|  expire  | (optional) Date object containing the expiration date for the cookie. Default is to use a session cookie.  |

**Returns:**

**Example:**

```js
//set a cookie with an expiration 6 months from now 
var date = new Date(); 
date.setMonth(date.getMonth() + 6); 
var success = s.Util.cookieWrite("my_cookie", "my_value", date);
```

