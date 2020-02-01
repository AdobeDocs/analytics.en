---
description: Test unpublished rules from your console if you use Akamai hosting.
keywords: Dynamic Tag Management;rule;switcher plug-in;akamai;test akamai;unpublished rules;test unpublished rules;debug rule
solution: Experience Cloud,Analytics,Target,Dynamic Tag Management
title: Test unpublished rules for Akamai hosting
uuid: 979e3d74-8d96-47d0-b581-cf5371248434
---

# Test unpublished rules for Akamai hosting

Test unpublished rules from your console if you use Akamai hosting.

The Switcher plug-in is often the easiest way to test. See [Search Discovery plug-ins](https://marketing.adobe.com/resources/help/en_US/dtm/search_discovery_plugins.html) in the Dynamic Tag Management Product Documentation for more information.

The following steps show how to test without using the Switcher plug-in: 

1. Access your web console on your site and type `localStorage.setItem('sdsat_stagingLibrary', true)`.
1. Press **[!UICONTROL Enter]**.
1. Type `_satellite.setDebug(true)`, then press **[!UICONTROL Enter]**.
1. Refresh the page.

   This action loads your staging library and sets the debugger, so that you can see details of all available (published / unpublished) rules firing on the page.
1. When finished, run `localStorage.setItem('sdsat_stagingLibrary', false)`, then press **[!UICONTROL Enter]**.

   Step Result 
