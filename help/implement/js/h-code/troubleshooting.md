---
title: Troubleshoot H code implementations
description: Learn some common issues with legacy JavaScript implementations.
exl-id: 51d6e286-7008-4736-a196-bd8ac4e3e9cb
---
# Troubleshoot H code implementations

The following are troubleshooting steps specific to H code implementations.

## Putting Analytics code in the head tag

>[!NOTE]
>
>While H Code implementations require code be referenced in the `<body>` tag, other implementations (such as using tags in Adobe Experience Platform) require code be referenced in the `<head>` tag.

Analytics code creates an invisible 1x1 pixel image. Previously, a common implementation practice was to place the `s_code.js` reference in the `<head>` tag. Placing the code here prevented the image from affecting page layout in any way. It also executes sooner, which lets you count page views for partial page loads more effectively.

However, certain elements of the code require the existence of the `<body>` object. If the Analytics JavaScript code is in the `<head>` tag, it executes before the `<body>` object exists. As a result, your implementation does not collect [!UICONTROL ClickMap] data, automatic tracking of file downloads or exit links, or connection type data. Putting the script reference to `s_code.js` in the `<head>` tag works, but the result is a very limited version of Analytics.

The Analytics code can be placed anywhere inside the `<body>` tag of a well-formed HTML page. Adobe recommends placing Analytics code as close to the top of the `<body>` tag as possible. Make sure that any page variables are set after the `s_code.js` file loads.

>[!TIP]
>
>If you want to integrate Adobe Analytics with Adobe Target, the JavaScript include file must be placed at the bottom of the page.
