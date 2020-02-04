---
title: Plug-ins overview
description: Paste code on your site to introduce new functionality.
---

# Plug-ins overview

Plug-ins are snippets of code that perform several advanced functions to help your Analytics implementation. These plug-ins extend the capabilities of your JavaScript file to give you more functionality that is not available with a basic implementation. Adobe offers a number of other plug-ins as part of advanced solutions.

> [!IMPORTANT] Plug-ins are provided by Adobe Consulting as a courtesy to help you get more value out of Adobe Analytics. Adobe Customer Care does not provide support with any of these plug-ins, including installation or troubleshooting. If you require help with a plug-in, contact your organization's Account Manager. They can arrange a meeting with a consultant for assistance.

Adobe offers several ways to install a given plug-in:

1. Use the 'Common Analytics Plugins' extension using Adobe Experience Platform Launch
2. Paste plug-in code using the Launch custom code editor
3. Paste the plug-in code in your `AppMeasurement.js` file

Each organization has different implementation needs, so you can decide how you want to include them in your implementation. Make sure that you meet the following criteria when including the code on your site:

1. Instantiate the Analytics tracking object (using `s_gi`) first.
   * Launch automatically instantiates the tracking object when Adobe Analytics loads.
   * Implementations using `AppMeasurement.js` typically initialize the tracking object at the top of the JavaScript file.
2. Include plug-in code second.
   * The 'Common Analytics Plugins' extension has an action configuration where you can initialize plug-ins.
   * If you don't want to use the plug-in, you can paste plug-in code in the custom code editor when configuring the Analytics extension.
   * If your implementation does not use Launch, you can paste plug-in code into `AppMeasurement.js` anywhere after you instantiate the tracking object.
3. Call the plug-in third.
   * All implementations, both inside and outside of Launch, use JavaScript to call plug-ins. Call the plug-in using the format documented on that plug-in's page.
4. Validate your implementation and publish.

Many organizations call plug-ins using the [`doPlugins`](../functions/doplugins.md) function. While this function is not required, Adobe considers it a best practice to use. AppMeasurement calls this function just before compiling and sending an image request, which is ideal since several plug-ins depend on other Analytics variables.
