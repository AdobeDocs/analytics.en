---
title: hier
description: Implement hierarchy variables in Adobe Analytics.
---

# hier

Hierarchy variables are custom variables that let you see a site's structure.

This variable is most useful for sites that have more than three levels in the site structure. For example, a media site may have 4 levels to the Sports section: Sports, Local Sports, Baseball, and Red Sox. If someone visits the Baseball page, Sports, Local Sports, and Baseball, all levels reflect that visit.

There are five [!UICONTROL hierarchy] variables available, which must be enabled by Adobe Customer Care. At the time the hierarchy is enabled, you should decide on a delimiter for the variable and the maximum number of levels for the hierarchy. For example, if the delimiter is a comma, the sports hierarchy may display as follows.

```js
s.hier1="Sports,Local Sports,Baseball"
```

Make sure that none of your section names have the delimiter in them. For example, if one of your sections is called "Coach Griffin, Jim," then you should choose a delimiter other than comma. Each hierarchy section is limited to 255 bytes, while the total variable limit is 255 bytes. After a delimiter is chosen (at the time the hierarchy is created) it is not easily changed.

Contact Adobe Customer Care about changing the delimiter for an existing hierarchy. Delimiters may also consist of multiple characters, such as || or /|\, which are less likely to appear in a hierarchy section.

## Syntax and Possible Values

Do not put a space between each delimiter. In the following example syntax, N is a number between one and five.

```js
s.hierN="Level 1[<delimiter>Level 2[<delimiter>Level 3[...]]]"
```

Do not use the delimiter except to delimit the levels of the hierarchy. The delimiter may be any character or characters of your choice.

## Examples

```js
s.hier1="Toys|Boys 6+|Legos|Super Block Tub"
```

```js
s.hier4="Sports/Local Sports/Baseball"
```

## Pitfalls, Questions, and Tips

* The delimiter may not be changed after the hierarchy is set up. If the delimiter for your hierarchy must be changed, contact Adobe Customer Care.
* The number of levels may not be changed after the hierarchy is set up.

> [!NOTE] Changes to hierarchies can result in a service charge.
