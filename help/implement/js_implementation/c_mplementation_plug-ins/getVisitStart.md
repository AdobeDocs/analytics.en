---
description: Determines if a new visit is starting.
keywords: Analytics Implementation
seo-description: Determines if a new visit is starting.
seo-title: getVisitStart
solution: Analytics
title: getVisitStart
topic: Developer and implementation
uuid: f67e16c3-47e7-499e-9daa-436f4d7270a8
index: y
internal: n
snippet: y
---

# getVisitStart

Determines if a new visit is starting.

 **Configuration Variables**

None

**Parameters**

c = (string) cookie name for tracking.

**Returns**

(integer) 1 on first page of visit, otherwise 0.

**Sample Calls**

```
s.eVar50 = s.getVisitStart("s_visit");
```

