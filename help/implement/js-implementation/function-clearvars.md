---
description: Clears the following values from the instance object. This function removes the elements (sets them as "undefined.")
keywords: Analytics Implementation
seo-description: Clears the following values from the instance object. This function removes the elements (sets them as "undefined.")
seo-title: The s.clearVars() Function
solution: Analytics
title: The s.clearVars() Function
topic: Developer and implementation
uuid: 43c425bc-15ae-4892-a5a5-e1defcb25ff4
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
>`clearVars()` is included in [AppMeasurement for JavaScript](/help/implement/js-implementation/c-appmeasurement-js/appmeasure-mjs.md) but is not available in H code and previous versions.

