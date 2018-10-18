---
description: Test unpublished rules from your console if you use Akamai hosting.
keywords: Dynamic Tag Management;rule;switcher plugin;akamai;test akamai;unpublished rules;test unpublished rules;debug rule
seo-description: Test unpublished rules from your console if you use Akamai hosting.
seo-title: Test unpublished rules for Akamai hosting
solution: Marketing Cloud,Analytics,Target,Dynamic Tag Management
title: Test unpublished rules for Akamai hosting
uuid: 037b0ec0-b229-4bf8-8df9-48b32bd60d2f
index: y
internal: n
snippet: y
---

# Test unpublished rules for Akamai hosting

Test unpublished rules from your console if you use Akamai hosting.

The Switcher plugin is often the easiest way to test. See [Search Discovery Plugins](https://marketing.adobe.com/resources/help/en_US/dtm/search_discovery_plugins.html) in the Dynamic Tag Management Product Documentation for more information.

The following steps show how to test without using the Switcher plugin: 

1. Access your web console on your site and type `localStorage.setItem('sdsat_stagingLibrary', true)`.
1. Press **[!UICONTROL Enter]**.
1. Type `_satellite.setDebug(true)`, then press **[!UICONTROL Enter]**.
1. Refresh the page.

   This action loads your staging library and sets the debugger, so that you can see details of all available (published / unpublished) rules firing on the page. 
1. When finished, run `localStorage.setItem('sdsat_stagingLibrary', false)`, then press **[!UICONTROL Enter]**.

   Step Result 