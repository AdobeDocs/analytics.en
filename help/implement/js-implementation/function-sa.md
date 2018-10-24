---
description: The s.sa() function lets you dynamically change a report suite at any time on the page, before or after an image request fires.
keywords: Analytics Implementation
seo-description: The s.sa() function lets you dynamically change a report suite at any time on the page, before or after an image request fires.
seo-title: The s.sa() Function
solution: Analytics
subtopic: Functions
title: The s.sa() Function
topic: Developer and implementation
uuid: ee5b99c9-e90a-424f-8e80-d3e31be16f2b
index: y
internal: n
snippet: y
---

# The s.sa() Function

The s.sa() function lets you dynamically change a report suite at any time on the page, before or after an image request fires.

 If your organization wants to send data to different report suites without a page reload, using this function is strongly recommended.

This information is suited for advanced users who are well-versed in both reporting and implementation. Do not attempt to make any edits to your implementation without complete knowledge of its consequences. If you require implementation changes, contact your organization's Account Manager.

## Properties of the Function {#section_E10CB41A0CF749F4A24C8377958E3671}

Setting this function takes all previously defined variables and lets them be used in a different report suite.

## Implementation Examples {#section_14B0B8C853244D5F82B08B995773640C}

Sending video data to one report suite while sending the rest to another:

```js
// Set in the core JS file by default 
var s=s_gi('prodrsid'); 
 
// Define this when a user interacts with a video 
s.sa('videorsid'); 
s.t(); // Sends an image request
```

Using s.sa() and multi-suite tagging:

```js
// Set in the core JS file by default 
var s=s_gi('rsid1'); 
 
// Call the function when you wish to change report suites 
s.sa('rsid1,rsid2'); 
s.t();
```

