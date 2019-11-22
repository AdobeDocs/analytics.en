---
description: Page variables directly populate a report, such as pageName, List Props, List Variables, and so on.
keywords: Analytics Implementation
solution: Analytics
subtopic: Variables
title: Page variables
topic:
uuid:
---


# javascriptVersion

The  variable indicates the version of JavaScript supported by the browser.


<!-- 

javascriptVersion.xml

 -->

This variable is populated after the page code and before *`doPlugins`* is run.

> [!NOTE] This variable should only be read and never set.

You may read these values and copy them into props/eVars, but you should never alter them. This variable is introduced with version H.11 of the JavaScript file.

|  Query Param  | Value  | Example  | Reports Affected  |
|---|---|---|---|
|  j  | 1.0, 1.1, 1.2, … 1.7  | 1.7  | Traffic > Technology > JavaScript Version  |

Version H.10 and higher of the JavaScript file accurately detect up to version 1.7 (the highest version at the time H.10 was released). Prior versions of the JavaScript file only detected up to version 1.3 
