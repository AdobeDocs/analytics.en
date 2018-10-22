---
description: Gets the value for a cookie.
keywords: Analytics Implementation
seo-description: Gets the value for a cookie.
seo-title: Util.cookieRead
solution: Analytics
subtopic: JavaScript AppMeasurement
title: Util.cookieRead
topic: Developer and implementation
uuid: 16b477c1-d8b8-4067-b288-4db05089607d
index: y
internal: n
snippet: y
---

# Util.cookieRead

Gets the value for a cookie.

 **Syntax:**

```
s.Util.cookieRead(key)
```

**Parameters:** 

|  Parameter  | Description  |
|---|---|
|  key  | (required) key to write value for in cookies.  |

**Returns:**

Cookie value or an empty string if the cookie is not found.

**Example:**

```js
var myCookie = s.Util.cookieRead("my_cookie");
```

