---
title: linkType
description: Use the linkType variable to determine which link tracking dimension the hit belongs to.
---

# linkType

Link tracking hits can populate one of three dimensions:

* Custom links
* Exit links
* Download links

Use the `linkType` variable to determine which dimension you want to populate when running the next [`tl()`](../functions/tl-method.md) function.

## Link Type in Adobe Experience Platform Launch

Set the link type when configuring a rule to send a beacon.

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
2. Click the desired property.
3. Go to the [!UICONTROL Rules] tab, then click the desired rule (or create a rule).
4. Under [!UICONTROL Actions], click the '+' icon
5. Set the [!UICONTROL Extension] dropdown to Adobe Analytics, and the [!UICONTROL Action Type] to Send Beacon.
6. Click the `s.tl()` radio button which reveals the [!UICONTROL Link Type] dropdown.

You can set this dropdown to [!UICONTROL Custom Link], [!UICONTROL Download Link], or [!UICONTROL Exit Link].

## s.linkType in AppMeasurement and Launch custom code editor

The `s.linkType` variable is a string that accepts one of three single-character values: `o`, `d`, or `e`. If a `tl()` method is called without a link type, it defaults to Custom link.

* `o` - Custom links
* `d` - Download links
* `e` - Exit links

>[!TIP]
>
>This variable is the second parameter of the `tl()` method, and usually does not need to be set as a standalone variable. However, you can use the `linkType` variable if you do not want to set values as arguments in the `tl()` method.

```js
s.linkType = "e";
```

## Example

The following two example link tracking calls are functionally identical. They are different methods to accomplish the same link tracking hit.

```js
// Set link tracking arguments as individual variables
s.linkType = "d";
s.linkName = "Example download link";
s.tl();

// Set link tracking arguments directly in the tl() function
s.tl(this,"d","Example download link");
```
