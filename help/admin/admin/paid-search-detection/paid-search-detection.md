---
description: Paid Search Detection differentiates paid from natural searches in the Search Engines and Search Keywords reports. You can specify the search engines where you use paid ads, and specify a character string found in the URL of a visit from a paid ad.
title: Paid Search Detection
topic: Admin tools
uuid: 41aadf17-7b8b-49ce-84ca-dc3293660205
exl-id: 6b513ad2-f955-4a34-92f8-57a141e44801
---
# Paid Search Detection

Paid Search Detection differentiates paid from natural searches in the Search Engines and Search Keywords reports. You can specify the search engines where you use paid ads, and specify a character string found in the URL of a visit from a paid ad.

## Paid Search Detection - Descriptions {#section_0C2CFA0AF77B47098BE37CB024665D0D}

The following table describes the fields and options you use to [configure paid search detection](/help/admin/admin/paid-search-detection/t-paid-search-detection.md).

| Elements | Description |
|--- |--- |
|Search Engine|Select a search engine from the drop-down list. You specify the engine if you use different query string parameters for different search engines. Usually, the value  Any is sufficient.|
|Query string|Specifies a case-sensitive rule set to either contain or not contain a specific value. This value should be the query string parameter, omitting the "?". <br>**Note**: Paid Search Detection is case sensitive. For example, a rule that specifies  PID as a query string parameter does not display pid in reporting. If your organization uses mixed cases, place the exact values as separate rules, so all desired query string parameters can be caught.</br>|
