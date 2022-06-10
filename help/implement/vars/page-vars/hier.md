---
title: hier
description: Implement hierarchy variables in Adobe Analytics.
feature: Variables
exl-id: 72bdab8f-a001-4ada-b5e2-453a8e3f24a6
---
# hier

Hierarchy variables are custom variables that let you see a site's structure.

>[!TIP]
>
>This variable was more common in previous versions of Adobe Analytics. Adobe recommends using [eVars](evar.md) and classifications instead.

This variable is useful for sites that have more than three levels in their site structure. For example, a media site can have 4 levels to the Sports section: `Sports`, `Local Sports`, `Baseball`, and `Team name`. If someone visits the Baseball page, Sports, Local Sports, and Baseball, all levels reflect that visit.

Adobe supports up to 5 hierarchy variables in your implementation. At the time the hierarchy is enabled, decide on a delimiter for the variable and the maximum number of levels for the hierarchy. For example, if the delimiter is a comma, the hierarchy would look similar to the following:

```js
s.hier1 = "Sports,Local Sports,Baseball";
```

Make sure that none of your section names have the delimiter in them. For example, if one of your sections is called `Coach Griffin, Jim`, choose a delimiter other than a comma. The total variable limit is 255 bytes. Delimiters can consist of multiple characters, such as `||` or `/|\`, which are less likely to appear in variable values.

## Examples

```js
s.hier1="Toys|Boys 6+|Legos|Super Block Tub";
```

```js
s.hier4="Sports/Local Sports/Baseball";
```
