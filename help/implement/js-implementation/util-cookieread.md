---
description: Gets the value for a cookie.
keywords: Analytics Implementation
seo-description: Gets the value for a cookie.
seo-title: Util.cookieRead
solution: Analytics
subtopic: JavaScript AppMeasurement
title: Util.cookieRead
topic: Developer and implementation
uuid: 825a75c6-b804-4bfe-b23a-907113b8bfa6
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

