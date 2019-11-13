---
description: Page variables directly populate a report, such as pageName, List Props, List Variables, and so on.
keywords: Analytics Implementation
solution: Analytics
subtopic: Variables
title: Page variables
topic:
uuid:
---

# state

The  and  variables are conversion variables.

<!-- 

state.xml

 -->

They are like eVars in that they capture events, but unlike eVars, they don't persist. The *`zip`* and *`state`* variables are like eVars that expire immediately.

|  Max Size  | Debugger Parameter  | Reports Populated  | Default Value  |
|---|---|---|---|
|  50 bytes  | state  | Conversion > Visitor Profile > Visitor State  | ""  |

Because the *`state`* and *`zip`* variables expire immediately, the only events associated with them are events that are fired on the same page on which they are populated. For example, if you are using *`state`* to compare conversion rates by state, you should populate the *`state`* variable on every page of the checkout process. For conversion sites, Adobe recommends using the billing address as the source for the Zip Code, but you may choose to use the shipping address instead (assuming there is only one shipping address for the order). A media site may choose to use *`zip`* and *`state`* for registration or ad click-through tracking.

**Syntax and Possible Values** {#section_EDD1F5F9EDBC457898E61695F08C1744}

```js
s.state="state"
```

The *`state`* variable does not impose any special value or format restrictions. There are no limitations on *`state`* outside of the standard variable limitations.

**Examples** {#section_D181B163F79A41D199CA4C70765E583F}

```js
s.state="california" 

```

```js
s.state="prince edward island"
```

**Configuration Settings** {#section_DB0D6DC3F4764AC59C11B10D27D2806C}

None

**Pitfalls, Questions, and Tips** {#section_02F1620D0BB14AA6A838966FDB9A234F}

* Populate *`state`* on every page that a relevant event is fired (such as each page of the checkout process).
* The *`zip`* and *`state`* variables act like eVars that expire on the Page View.
