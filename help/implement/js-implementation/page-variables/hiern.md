---
description: Page variables directly populate a report, such as pageName, List Props, List Variables, and so on.
keywords: Analytics Implementation
solution: Analytics
subtopic: Variables
title: Page variables
topic:
uuid:
---


# hierN

The [!UICONTROL hierarchy] variable determines the location of a page in your site's hierarchy.

<!-- 

hierN.xml

 -->

This variable is most useful for sites that have more than three levels in the site structure. For example, a media site may have 4 levels to the Sports section: Sports, Local Sports, Baseball, and Red Sox. If someone visits the Baseball page, Sports, Local Sports, and Baseball, all levels reflect that visit.

|  Max Size  | Debugger Parameter  | Reports Populated  | Default Value  |
|---|---|---|---|
|  255 Bytes  | H1-H5  | Hierarchy  | ""  |

There are five [!UICONTROL hierarchy] variables available, which must be enabled by Adobe Customer Care. At the time the hierarchy is enabled, you should decide on a delimiter for the variable and the maximum number of levels for the hierarchy. For example, if the delimiter is a comma, the sports hierarchy may display as follows.

```js
s.hier1="Sports,Local Sports,Baseball"
```

Make sure that none of your section names have the delimiter in them. For example, if one of your sections is called "Coach Griffin, Jim," then you should choose a delimiter other than comma. Each hierarchy section is limited to 255 bytes, while the total variable limit is 255 bytes. After a delimiter is chosen (at the time the hierarchy is created) it is not easily changed.

Contact Adobe Customer Care about changing the delimiter for an existing hierarchy. Delimiters may also consist of multiple characters, such as || or /|\, which are less likely to appear in a hierarchy section.

**Syntax and Possible Values** {#section_0739948A68A2420DAB1CBEA3115A5A66}

Do not put a space between each delimiter. In the following example syntax, N is a number between one and five.

```js
s.hierN="Level 1[<delimiter>Level 2[<delimiter>Level 3[...]]]"
```

Do not use the delimiter except to delimit the levels of the hierarchy. The delimiter may be any character or characters of your choice.

**Examples** {#section_38E0929F88DD45B6ACDF473DF155971D}

```js
s.hier1="Toys|Boys 6+|Legos|Super Block Tub"
```

```js
s.hier4="Sports/Local Sports/Baseball"
```

**Configuration Settings** {#section_E823FB3CAD744D2480EBCE2DF9B134CC}

None

**Pitfalls, Questions, and Tips** {#section_104E5BD320764BDEA5FA8D13A70C78E3}

* The delimiter may not be changed after the hierarchy is set up. If the delimiter for your hierarchy must be changed, contact Adobe Customer Care.
* The number of levels may not be changed after the hierarchy is set up.

> [!NOTE] Changes to hierarchies can result in a service charge.

