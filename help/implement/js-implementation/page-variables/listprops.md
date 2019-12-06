---
description: Page variables directly populate a report, such as pageName, List Props, List Variables, and so on.
keywords: Analytics Implementation
subtopic: Variables
title: Page variables
topic:
uuid:
---


# List Props

List props are a delimited list of values that are passed into a variable, then reported as individual line items. List props are most commonly implemented on pages that contain user-selectable values, such as listed items with check boxes or radio buttons. They are useful in any circumstance where you want to define multiple values in a variable without sending multiple image requests.


<!-- 

list_props.xml

 -->

**Considerations**

* List props are enabled only on traffic variables ( [props](/help/implement/js-implementation/page-variables/propn.md)).
* Pathing and correlations cannot be enabled for list props.
* Analytics provides visits and unique visitors to almost every report, including all list prop reports.
* Classifications are supported for list props.
* Any custom traffic variable can become a list prop. (Exceptions: [pageName](/help/implement/js-implementation/page-variables/pagename.md), [channel](/help/implement/js-implementation/page-variables/channel.md), and [server](/help/implement/js-implementation/page-variables/server.md).) 

* When defining duplicate values in the same image request, instances are not deduplicated.

A prop can be changed into a list prop on the Admin Tools > Report Suite > Traffic Variables page by enabling List Support and then selecting a delimiter. Popular delimiters are colons, semi-colons, commas, or pipes. The delimiter can technically be any of the first 127 ASCII characters.

**Implementation Examples** 

When you request enabling of list props, indicate the delimiter that you would like to use. After the *`s.prop`* of your choice is enabled, multiple values can be set in the variable as shown in the following examples:

A list prop delimited by a pipe, passing in two values:

```js
s.prop1="Banner ad impression|Sidebar impression"
```

A list prop delimited by a comma passing in several values:

```js
s.prop2="cerulean,vermilion,saffron"
```

List props can also be sent with a single value:

```js
s.prop3="Single value"
```

The delimiter can be changed at any time. However, the implementation must match the new delimiter. Failure to use the correct delimiter results in the list prop value being treated as a single concatenated line item in reporting.

Because a list prop is still a Traffic Variable, it is subject to Traffic Variable limitations. List props are limited to 100 bytes of data and are affected by case sensitivity settings.

