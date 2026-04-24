---
title: Plug-ins overview
description: Paste code on your site to introduce new functionality.
feature: Appmeasurement Implementation
exl-id: faae7963-078d-40ad-ba09-71efa0b90df1
role: Admin, Developer
TQID: https://experienceleague.adobe.com/ImzoBRU0DajPc99vRlu1698CteFNk9dOS2OZrN9DBZs
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
    internal-label: Implementations
subfeature_v2:
  - id: c069c44e-5426-4c1a-accc-8028662f2fde
    internal-label: Functions
  - id: df312454-73c4-43f6-a90e-18f5043f074c
    internal-label: Tags
  - id: e7d92df1-c5ba-4e93-85df-f83171b889be
    internal-label: Variables
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: c1579802-ddd4-4214-8a91-97b2066abe11
    internal-label: Troubleshooting
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
    internal-label: Measurement
---
# Plug-ins overview

Plug-ins are snippets of code that perform several advanced functions to help your Analytics implementation. These plug-ins extend the capabilities of your JavaScript file to give you more functionality that is not available with a basic implementation. Adobe offers a number of other plug-ins as part of advanced solutions.

{{plug-in}}

Adobe offers several ways to install a given plug-in:

* Use the 'Common Analytics Plugins' extension using the Adobe Analytics extension
* Paste plug-in code using the custom code editor
* Paste the plug-in code in your `AppMeasurement.js` file

Each organization has different implementation needs, so you can decide how you want to include them in your implementation. Make sure that you meet the following criteria when including the code on your site:

1. Instantiate the Analytics tracking object (using [`s_gi`](../functions/s-gi.md)) first.
   * Your tag-enabled site automatically instantiates the tracking object when Adobe Analytics loads.
   * Implementations using `AppMeasurement.js` typically initialize the tracking object at the top of the JavaScript file.
2. Include plug-in code second.
   * The 'Common Analytics Plugins' extension has an action configuration where you can initialize plug-ins.
   * If you don't want to use the extension, you can paste plug-in code in the custom code editor when configuring the Analytics extension.
   * If your implementation does not use tags in Adobe Experience Platform, you can paste plug-in code into `AppMeasurement.js` anywhere after you instantiate the tracking object.
3. Call the plug-in third.
   * All implementations, both inside and outside of a tag-enabled site, use JavaScript to call plug-ins. Call the plug-in using the format documented on that plug-in's page.
4. Validate your implementation and publish.

Many organizations call plug-ins using the [`doPlugins`](../functions/doplugins.md) function. While this function is not required, Adobe considers it a best practice to use. AppMeasurement calls this function just before compiling and sending an image request, which is ideal since several plug-ins depend on other Analytics variables.
