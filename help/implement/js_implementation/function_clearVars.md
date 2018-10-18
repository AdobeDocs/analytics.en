---
description: Clears the following values from the instance object. This function removes the elements (sets them as "undefined.")
keywords: Analytics Implementation
seo-description: Clears the following values from the instance object. This function removes the elements (sets them as "undefined.")
seo-title: The s.clearVars() Function
solution: Analytics
title: The s.clearVars() Function
topic: Developer and implementation
uuid: b7c5931a-6dbd-46e2-96ca-fcbdea71af39
index: y
internal: n
snippet: y
---

# The s.clearVars() Function

Clears the following values from the instance object. This function removes the elements (sets them as "undefined.")

* `props` 
* `eVars` 
* `hier` 
* `list` 
* `events` 
* `eventList` 
* `products` 
* `productsList` 
* `channel` 
* `purchaseID` 
* `transactionID` 
* `state` 
* `zip` 
* `campaign`

For example:

```js
s.clearVars()
```

>[!NOTE]
>
>`clearVars()` is included in [AppMeasurement for JavaScript](../js_implementation/c_appmeasurement_js/appmeasure_mjs.md#concept_F3957D7093A94216BD79F35CFC1557E8) but is not available in H code and previous versions.

