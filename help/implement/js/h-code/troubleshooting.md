---
title: Troubleshoot H code implementations
description: Learn some common issues with legacy JavaScript implementations.
feature: Implementation Basics
exl-id: 51d6e286-7008-4736-a196-bd8ac4e3e9cb
role: Developer
TQID: https://experienceleague.adobe.com/DootwtTj5kDIRHKhFPeY3Fnt3bWdVLsXc6J3UEc5LPI
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
    internal-label: Implementations
subfeature_v2:
  - id: df312454-73c4-43f6-a90e-18f5043f074c
    internal-label: Tags
  - id: e7d92df1-c5ba-4e93-85df-f83171b889be
    internal-label: Variables
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: c1579802-ddd4-4214-8a91-97b2066abe11
    internal-label: Troubleshooting
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
