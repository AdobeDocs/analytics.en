---
description: Page variables directly populate a report, such as pageName, List Props, List Variables, and so on.
keywords: Analytics Implementation
subtopic: Variables
title: Page variables
topic:
uuid:
---

# media.trackVars

The  variable identifies which variables should be sent with a media hit.


<!-- 

media_trackVars.xml

 -->

It is only applicable with JavaScript and [!UICONTROL ActionSource].

|  Max Size  | Debugger Parameter  | Reports Populated  | Default Value  |
|---|---|---|---|
|  N/A  | N/A  | N/A  | s.Media.trackVars="None"  |

**Syntax and Possible Values** {#section_7374684A7EB34AE685E8C40A66CFD289}

Variable names such as [!UICONTROL propN], *`eVarN`*, *`events`*, *`channel`*, and so forth.

**Examples** {#section_48653222ABA14AB0A3C4471659971FAA}

```js
s.Media.trackVars="prop2,events,eVar3"
```

**Pitfalls, Questions, and Tips** {#section_615AE1B696124B00B78F651B03813EAB}

* Even if eVar3 is specified in [!UICONTROL trackVars], it is sent with the media hit.

## mobile {#concept_0CEE045F57B444138C0EAA015FC7EA70}

The  variable controls the order in which cookies and subscriber IDs are used to identify visitors.

<!-- 

mobile.xml

 -->

See [Mobile network protocols](/help/implement/js-implementation/c-additional-libraries/network-protocols.md).

|  Max Size  | Debugger Parameter  | Reports Populated  | Default Value  |
|---|---|---|---|
|  N/A  | /5/ or /1/ in path of image url  | N/A  | None  |

**Syntax and Possible Values** {#section_7F1C58090C454882BA9D3D66C9263A76}

```js
s.mobile="any_string" //subscriber id used first, produces /5/ in path of image url 
s.mobile=""  // if set to an empty string or not set at all, cookies used first, produces /1/ in path of image url 

```

**Pitfalls, Questions, and Tips** {#section_06CD5CB4EF1E4B9FBE3B9D1F18AAFA30}

Use cross-visitor identification to mitigate possible spikes in visitor traffic when using the *`s.mobile`* variable with the JavaScript cookie implementation.
