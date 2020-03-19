---
title: clearVars
description: Clears the following values from the instance object. This function removes the elements (sets them as "undefined.")
---

# clearVars

Some implementations, such as on single-page applications, require multiple hits sent on the same page load. Use the `clearVars()` method to clear variable values so they don't persist to subsequent hits.

This method does not take any arguments, and does not return any value. Its only purpose is to clear variable values from the instance object. This method sets the following elements to `undefined`:

* `prop1` - `prop75`
* `eVar` - `eVar250`
* `hier1` - `hier5`
* `list1` - `list3`
* `events`
* `products`
* `channel`
* `purchaseID`
* `transactionID`
* `state`
* `zip`
* `campaign`

## Clear Variables in Adobe Experience Platform Launch

Set the Clear Variables action when configuring a rule.

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
2. Click the desired property.
3. Go to the [!UICONTROL Rules] tab, then click the desired rule (or create a rule).
4. Under [!UICONTROL Actions], click the '+' icon
5. Set the [!UICONTROL Extension] dropdown to Adobe Analytics, and the [!UICONTROL Action Type] to [!UICONTROL Clear Variables].

## s.clearVars() in AppMeasurement and Launch custom code editor

You can call the `s.clearVars()` method anywhere in your implementation after you instantiate the Analytics object instance.

```js
s.clearVars();
```
