---
description: The s_gi() function is used to create or find your instance of AppMeasurement by report suite ID. Internally, AppMeasurement keeps track of every instance created, and s_gi() returns the existing instance for a report suite if one exists. If an instance does not exist, a new instance is created and returned.
keywords: Analytics Implementation
seo-description: The s_gi() function is used to create or find your instance of AppMeasurement by report suite ID. Internally, AppMeasurement keeps track of every instance created, and s_gi() returns the existing instance for a report suite if one exists. If an instance does not exist, a new instance is created and returned.
seo-title: The s_gi() Function
solution: Analytics
title: The s_gi() Function
topic: Developer and implementation
uuid: a77de90e-c60e-4946-90cf-deaf8aa3d755
---

# The s_gi() Function

The s_gi() function is used to create or find your instance of AppMeasurement by report suite ID. Internally, AppMeasurement keeps track of every instance created, and s_gi() returns the existing instance for a report suite if one exists. If an instance does not exist, a new instance is created and returned.

We recommend calling `s_gi()` before setting variables and making tracking calls throughout your page code. This ensures that the correct object is used to make the tracking call in the case that the s variable is inadvertently overwritten.

## Using Multiple Report Suites {#section_F2F3B76E7AFD4B4B91CDC8BBEB34BBC5}

The object returned varies based on the report suite ID(s) passed. For example, if you make the following initial call to `s_gi()`:

```
var s=s_gi('rsid1,rsid2')
```

The following table outlines what is returned by subsequent calls: 

|  **Subsequent Call to s_gi** | **Description of Object Returned** |
|---|---|
|  `s=s_gi('rsid1,rsid2')`  | The same object referenced earlier.  |
|  `s=s_gi('rsid1')`  | A copy of the object created earlier, but not the original.  |
|  `s=s_gi('rsid1,rsid3')`  | A copy of the object created earlier, but not the original.  |
|  `s=s_gi('rsid3')`  | A new, empty object, with no config variables set (e.g. linkTrackVars is empty, as is linkDownloadFileTypes).  |
