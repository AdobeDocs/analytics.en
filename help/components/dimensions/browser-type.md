---
title: Browser type
description: The organization that made the browser.
exl-id: 2a88ebc6-879e-4e5b-a8e5-40a32d54ac1b
---
# Browser type

The 'Browser type' dimension lists organizations who made the browser that the visitor uses. This dimension is useful when you want to see which overarching browsers visitors use. It provides value over the 'Browsers' dimension in that it does not list different versions of the same browser as separate dimension items.

## Populate this dimension with data

This dimension references a lookup table internal to Adobe. The lookup value is based on the `User-Agent` HTTP header in image requests. If you use an AppMeasurement library (such as through tags in Adobe Experience Platform), this dimension works out of the box.

## Dimension items

Dimension items include organizations that make browsers. Common dimension items include `"Google"` (the creators of [!DNL Chrome]), `"Apple"` (the creators of [!DNL Safari]), `"Microsoft"` (the creators of [!DNL Edge]), and `"Mozilla"` (the creators of [!DNL Firefox]).
