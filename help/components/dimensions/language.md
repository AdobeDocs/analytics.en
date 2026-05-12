---
title: Language
description: The preferred language setting in the browser.
feature: Dimensions
exl-id: 590406a4-d336-42c7-8048-e7cd8e611d43
TQID: https://experienceleague.adobe.com/KC8nBiwUbQaE8Wi5OVKdjwP-sTijGYYMBK74M-TnOFs
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
subfeature_v2:
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
    internal-label: Calculated Metrics
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
    internal-label: Measurement
---
# Language

The 'Language' [dimension](overview.md) shows the top languages that visitors prefer to see content in. This dimension is valuable when you want to understand the most frequent preferred languages of visitors to aid in localization efforts.

>[!NOTE]
>
>This dimension does not collect the language of your site. If you want to collect the language of your site in a dimension, Adobe recommends using a custom variable, such as an [eVar](evar.md).

## Populate this dimension with data

This dimension references a lookup table internal to Adobe. The lookup value is based on the `Accept-Language` HTTP header in image requests. If you use an AppMeasurement library (such as through tags in Adobe Experience Platform), this dimension works out of the box.

## Dimension items

Dimension items include friendly names of the preferred languages of visitors. Examples include `"English (United States)"`, `"English (United Kingom)"`, `"Chinese (China)"`, and `"Spanish (Spain)"`. If an image request does not contain a valid language in the HTTP header, the dimension item is `"None"`.
