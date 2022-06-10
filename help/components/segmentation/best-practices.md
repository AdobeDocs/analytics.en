---
title: Segmentation best practices
description: Create optimal segments that return data efficiently.
feature: Segmentation
exl-id: 4115a804-5063-430a-b9d3-2b64b26ca4d8
---
# Segmentation best practices

Complex segments are often necessary to obtain desired data. If complex segments are inefficient and used in a large report suite, reports take considerably longer to run. Consider the following resources when creating or editing a segment to minimize complexity.

## Only use the 'Contains' operator as a last resort

The 'Contains' operator is one of the most processing-intensive features in segmentation, as it has to analyze the entire contents of every value. Consider using other operators such as 'Starts with' or 'Ends with' if the desired values are at the beginning or end of a string.

If a 'Contains' operator in a segment returns a large number of results, the report typically times out. For example, if you created a segment where `Referrer equals "."`, the segment searches through the contents of every value. Consider using the 'Exists' operator instead.

## Use classifications to group dimension items

If you have many segment conditions, they can quickly degrade segment performance. For example, `Page equals X or Page equals Y or Page equals Z` repeated with hundreds of different values. Instead of writing out these hundreds of conditions, classify all desired values into a segment, then use the classified value in a segment.

1. Create a classification for the variable that you're working with.
2. Download the classification template, and open it in your desired spreadsheet or text editor.
3. Give each dimension item that you would like to include in your segment the same value.
4. Use the classification importer to import the spreadsheet back into Adobe Analytics
5. Once the classification is finished processing, create a segment using the classified value.

This method drastically increases performance and provides an easy way to modify segment conditions. Instead of editing the segment with different values, you can add or remove dimension items from the classificiation.
