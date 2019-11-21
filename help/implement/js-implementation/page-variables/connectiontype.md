---
description: Page variables directly populate a report, such as pageName, List Props, List Variables, and so on.
keywords: Analytics Implementation
solution: Analytics
subtopic: Variables
title: Page variables
topic:
uuid:
---



# connectionType

The  variable, in Internet Explorer, indicates whether the browser is configured on a LAN or modem connection.


<!-- 

conntype.xml

 -->

This variable is populated after the page code and before *`doPlugins`* is run.

> [!NOTE] This variable should only be read and never set.

You may read these values and copy them into `props/eVars`, but you should never alter them. This variable is introduced with version H.11 of the JavaScript file.

|  Query Param  | Value  | Example  | Reports Affected  |
|---|---|---|---|
|  ct  | lan or modem  | lan  | Traffic > Technology > Connection Type  |
