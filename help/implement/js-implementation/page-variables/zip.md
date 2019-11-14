---
description: Page variables directly populate a report, such as pageName, List Props, List Variables, and so on.
keywords: Analytics Implementation
solution: Analytics
subtopic: Variables
title: Page variables
topic:
uuid:
---

# zip

The  and  variables are conversion variables.

<!-- 

zip.xml

 -->

They are like eVars in that they capture events, but unlike eVars, they don't persist. The *`zip`* and *`state`* variables are like eVars that expire immediately.

|  Max Size  | Debugger Parameter  | Reports Populated  | Default Value  |
|---|---|---|---|
|  50 bytes  | zip  | Conversion > Visitor Profile > ZIP/Postal Codes  | ""  |

Since the *`state`* and *`zip`* variables expire immediately, the only events associated with them are events fired on the same page that are populated. For example, if you are using *`zip`* to compare conversion rates by Zip Code, you should populate *`zip`* on every page of the checkout process. Adobe recommends using the billing address as the source for the Zip Code. You may choose to use the shipping address instead (assuming there is only one shipping address for the order). A media site may choose to use *`zip`* and *`state`* for registration or ad click-through tracking.

**Syntax and Possible Values** {#section_5EDCFCAC8FC241D1B4CC777996858CD7}

```js
s.zip="zip_code"
```

The *`zip`* variable does not impose any value or format restrictions. There are no limitations on *`zip`* outside of the standard variable limitations.

**Examples** {#section_F25C0D0CC3C04B81892A662CD605C593}

```js
s.zip="92806"
```

```js
s.zip="92806-4115"
```

**Configuration Settings** {#section_7987084EECC34DD38B643B94F82385CA}

None

**Pitfalls, Questions, and Tips** {#section_E86774D5CE8B40EFA36353CDEE3A84D0}

* Populate [!UICONTROL zip] on every page in which a relevant event is fired (such as each page of the checkout process).
* The *`zip`* and *`state`* variables act like eVars that expire on the Page View.

