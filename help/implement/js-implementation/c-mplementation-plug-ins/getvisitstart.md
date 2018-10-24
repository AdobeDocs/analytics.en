---
description: Determines if a new visit is starting.
keywords: Analytics Implementation
seo-description: Determines if a new visit is starting.
seo-title: getVisitStart
solution: Analytics
title: getVisitStart
topic: Developer and implementation
uuid: ea568357-11c9-42cb-a713-37c6f75592a9
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

