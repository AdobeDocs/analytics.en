---
description: Writes a value to a cookie.
keywords: Analytics Implementation
subtopic: JavaScript AppMeasurement
title: Util.cookieWrite
topic: Developer and implementation
uuid: 8d526e4c-6d7a-4119-9434-d7ce4fbb7577
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

