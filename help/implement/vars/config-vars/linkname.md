---
title: linkName
description: Set the name of the custom link hit.
---

# linkName

Use the `linkName` variable to determine the dimension item of custom links, download links, or exit links when running the next [`tl()`](../functions/tl-method.md) method.

If this variable is blank, AppMeasurement reverts to the [`linkURL`](linkurl.md) variable.

## Link Name in Adobe Experience Platform Launch

You can set the link name field when configuring a rule to send a beacon.

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
2. Click the desired property.
3. Go to the [!UICONTROL Rules] tab, then click the desired rule (or create a rule).
4. Under [!UICONTROL Actions], click the '+' icon
5. Set the [!UICONTROL Extension] dropdown to Adobe Analytics, and the [!UICONTROL Action Type] to Send Beacon.
6. Click the `s.tl()` radio button which reveals the [!UICONTROL Link Name] field.

## s.linkName in AppMeasurement and Launch custom code editor

The `s.linkName` variable is a string that determines the dimension item for custom links, download links, or exit links (depending on what [`s.linkType`](linktype.md) is). It can hold up to 100 bytes.

>[!TIP]
>
>This variable is the third parameter of the `tl()` method, and usually does not need to be set as a standalone variable. However, you can use the `linkName` variable if you do not want to set values as arguments in the `tl()` method.

```js
s.linkName = "Example custom link";
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
