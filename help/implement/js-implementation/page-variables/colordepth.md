---
description: Page variables directly populate a report, such as pageName, List Props, List Variables, and so on.
keywords: Analytics Implementation
subtopic: Variables
title: Page variables
topic:
uuid:
---

# colorDepth

The  variable is used to show the number of bits used to display color on each pixel of the screen.


<!-- 

colordepth.xml

 -->

For example, 32 represents 32 bits of color on the screen. This variable is populated after the page code and before *`doPlugins`* is run.

> [!NOTE] This variable should only be read and never set.

You may read these values and copy them into `props/eVars`, but you should never alter them. This variable is introduced with version H.11 of the JavaScript file.

|  Query Param  | Value  | Example  | Reports Affected  |
|---|---|---|---|
|  c  | 8,16, and 32  | 32  | Traffic > Technology > Monitor Color Depth  |
