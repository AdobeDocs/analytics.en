---
title: Best Practices
description: Learn some segmentation best practices.
feature: Segmentation
exl-id: 4115a804-5063-430a-b9d3-2b64b26ca4d8
TQID: https://experienceleague.adobe.com/PJi-kkv6HL3jHEKArltzxMGk9BVtZ-Mr1ivHMkhxt88
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
    internal-label: Reports
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
---
# Segmentation best practices

Complex segments are often necessary to obtain desired data. If complex segments are inefficient and used in a large report suite, reports take considerably longer to run. Consider the following resources when creating or editing a segment to minimize complexity.

## Only use the `Contains` operator as a last resort

The [**[!UICONTROL Contains]** operator](/help/components/segmentation/seg-reference/seg-operators.md) is one of the most processing-intensive features in segmentation, as the operator has to analyze the entire contents of every value. Consider using other operators such as **[!UICONTROL Starts with]** or **[!UICONTROL Ends with]** if the desired values are at the beginning or end of a string.

If a **[!UICONTROL Contains]** operator in a segment returns a large number of results, the report typically times out. For example, if you created a segment where **[!UICONTROL Referrer]** **[!UICONTROL equals]** `"."`, the segment searches through the contents of every value. Consider using the **[!UICONTROL Exists]** operator instead.

## Use classifications to group dimension items

If you have many segment conditions, they can quickly degrade segment performance. For example, **[!UICONTROL Page]** **[!UICONTROL equals]** `X` **[!UICONTROL OR]** **[!UICONTROL Page]** **[!UICONTROL equals]** `Y` **[!UICONTROL OR]** **[!UICONTROL Page]** **[!UICONTROL equals]** `Z` repeated with hundreds of different values. Instead of writing out these hundreds of conditions, classify all desired values into a segment, then use the classified value in a segment.

1. Create a classification for the variable that you're working with.
2. Download the classification template, and open it in your desired spreadsheet or text editor.
3. Give each dimension item that you would like to include in your segment the same value.
4. Use the classification importer to import the spreadsheet back into Adobe Analytics
5. Once the classification is finished processing, create a segment using the classified value.

This method drastically increases performance and provides an easy way to modify segment conditions. Instead of editing the segment with different values, you can add or remove dimension items from the classificiation.
