---
description: Page variables directly populate a report, such as pageName, List Props, List Variables, and so on.
keywords: Analytics Implementation
solution: Analytics
subtopic: Variables
title: Page variables
topic:
uuid:
---

# channel

The  variable is most often used to identify a section of your site.


<!-- 

channel.xml

 -->

For example, a merchant may have sections such as Electronics, Toys, or Apparel. A media site may have sections such as News, Sports, or Business.

|  Max Size  | Debugger Parameter  | Reports Populated  | Default Value  |
|---|---|---|---|
|  100 Bytes  | CH  | Site Content > Site Sections  | ""  |

Adobe recommends populating the channel variable on every page. You can also turn on a correlation between the *`channel`* and [!UICONTROL page name] variables.

When sections have one or more levels of subsections, you can show those sections in the *`channel`* variable or use separate variables to identify levels.

**Syntax and Possible Values**

```js
s.channel="value"
```

The *`channel`* variable has no extra limitations on its values.

**Examples** {#section_2527B2BB1CFD46CB952178ABF7A9028A}

```js
s.channel="Electronics"
```

```js
s.channel="Media"
```

**Pitfalls, Questions, and Tips** {#section_61941D5E4E644B59A267A4F44FD5DE8C}

If your site contains multiple levels, you can use the *`hierarchy`* or another variable to designate those levels. The *`channel`* value does not persist, but the success events fired on the same page are attributed to the *`channel`* value.
