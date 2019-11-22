---
description: Page variables directly populate a report, such as pageName, List Props, List Variables, and so on.
keywords: Analytics Implementation
solution: Analytics
subtopic: Variables
title: Page variables
topic:
uuid:
---

# media.trackEvents

The  variable identifies which events should be sent with a media hit.


<!-- 

media_trackEvents.xml

 -->

It is only applicable with JavaScript and [!UICONTROL ActionSource].

|  Max Size  | Debugger Parameter  | Reports Populated  | Default Value  |
|---|---|---|---|
|  N/A  | N/A  | N/A  | s.Media.trackEvents="None"  |

**Syntax and Possible Values** {#section_66A978EF56914BEAAE73359A268A1B4A}

Event names such as event1 or purchase.

**Examples** {#section_140A55D80EA24011954F9383CF312237}

```js
s.Media.trackEvents="event1,purchase"
```

**Pitfalls, Questions, and Tips** {#section_030B11C64EE84D46A85CA550DB732D28}

Make sure to populate [!UICONTROL trackVars] with "events" whenever this variable is populated.
