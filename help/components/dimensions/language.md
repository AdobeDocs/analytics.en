---
title: Language
description: The preferred language setting in the browser.
exl-id: 590406a4-d336-42c7-8048-e7cd8e611d43
---
# Language

The 'Language' dimension shows the top languages that visitors prefer to see content in. This dimension is valuable when you want to understand the most frequent preferred languages of visitors to aid in localization efforts.

>[!NOTE]
>
>This dimension does not collect the language of your site. If you want to collect the language of your site in a dimension, Adobe recommends using a custom variable, such as an [eVar](evar.md).

## Populate this dimension with data

This dimension references a lookup table internal to Adobe. The lookup value is based on the `Accept-Language` HTTP header in image requests. If you use an AppMeasurement library (such as through tags in Adobe Experience Platform), this dimension works out of the box.

## Dimension items

Dimension items include friendly names of the preferred languages of visitors. Examples include `"English (United States)"`, `"English (United Kingom)"`, `"Chinese (China)"`, and `"Spanish (Spain)"`. If an image request does not contain a valid language in the HTTP header, the dimension item is `"None"`.
