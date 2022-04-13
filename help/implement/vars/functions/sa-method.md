---
title: sa
description: Change the report suite at any time in your implementation.
feature: Variables
exl-id: 524857a7-c820-4985-86c7-fcf21a0809bd
---
# sa

The `sa()` method lets you dynamically change a report suite at any time on the page. If you want to send data to different report suites without a page reload, you can use this method.

## Use the sa method using tags in Adobe Experience Platform

There is not a flexible way to change report suite in the interface. You can set report suite under the [!UICONTROL Library Management] accordion when configuring the Adobe Analytics extension. However, you cannot change or update the report suite using rules. If you want to update report suite values after they are set, use the custom code editor following AppMeasurement syntax.

## s.sa() in AppMeasurement and custom code editor

Call the `s.sa()` method to change the destination report suite. Its only argument is a string containing a report suite ID, or multiple report suite IDs delimited by a comma. The report suite ID argument is required. Do not use spaces in the string argument.

```js
s.sa("examplersid");
```

## Example

You can change the report suite if the user takes a specific action on your site.

```js
// Instantiate the tracking object
var s = s_gi("examplersid");

// If the visitor plays a video, you can add a video report suite
s.sa("examplersid,videorsid");

// Then send an image request
s.t();
```
