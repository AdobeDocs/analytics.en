---
description: Determines if a new visit is starting.
keywords: Analytics Implementation
seo-description: Determines if a new visit is starting.
seo-title: getVisitStart
solution: Analytics
title: getVisitStart
topic: Developer and implementation
uuid: 9da1a249-618b-4096-aaf1-93ce2fb91ed9
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

