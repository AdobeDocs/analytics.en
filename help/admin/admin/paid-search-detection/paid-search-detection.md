---
description: Paid Search Detection differentiates paid from natural searches in the Search Engines and Search Keywords reports. 
title: Paid Search Detection
feature: Admin Tools
exl-id: 6b513ad2-f955-4a34-92f8-57a141e44801
---
# Paid Search Detection

[!UICONTROL Paid Search Detection] differentiates paid from natural searches in the [!UICONTROL Search Engines] and [!UICONTROL Search Keywords] reports. You can specify the search engines where you use paid ads, and specify a character string found in the URL of a visit from a paid ad.

## Configuration options {#section_0C2CFA0AF77B47098BE37CB024665D0D}

The following table describes the fields and options you use to [configure paid search detection](/help/admin/admin/paid-search-detection/t-paid-search-detection.md).

| Option | Description |
| --- | --- |
| [!UICONTROL Search Engine] | Select a search engine from the drop-down list. You specify the engine if you use different query string parameters for different search engines. Usually, the value `Any` is sufficient. |
| [!UICONTROL Query string] | Specifies a string for a case-sensitive match with any part of the query string parameter, which is the part of the url after the "?". <br>**Note**: [!UICONTROL Paid Search Detection] is case sensitive. For example, a rule that specifies "PID" as a query string parameter will not match "pid". If your organization uses mixed cases, place the exact values as separate rules, so all desired query string parameters can be caught.|
