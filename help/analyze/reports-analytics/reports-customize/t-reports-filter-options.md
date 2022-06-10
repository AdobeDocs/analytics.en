---
description: Filters allow you to narrow the report to include or exclude line items that match a filter.
title: Filtering Report Data
uuid: b6dcaaf7-61f0-4793-870d-e1d156575d5a
feature: Reports & Analytics Basics
role: User, Admin
exl-id: 232c6f69-40bf-487a-8621-d1d7d633681f
---
# Filter Report Data {#concept_09DC5B986A644738B12204DAC76A90E1}

Filters allow you to narrow the report to include or exclude line items that match a filter.

## Simple Filter {#section_5C4DE873F8D5484BB77F38A4AEB57B4A}

![](assets/filter.png)

The simple filter appears on most reports to let you quickly find specific line items. Simple filters do not use any special characters, so `-, ", ', +` and other special characters match the literal value in the report. You can find line items that contain multiple terms using a space.

For example:

```
help search
```

Matches the following pages: 

```
help:Search
help:Paid Search Detection
help:Configure paid search detection
help:Search Keywords Report
help:Internal Search Term
```

## Advanced Filters {#section_E016626C084640E8A066B2FDA5B932BF}

Advanced filters let you control the scope of your search using a collection of filters. You can select to match all filters, or any filters.

![](assets/advanced_filter.png)

**Contains**

Matches if the term is found anywhere in the line item. This operates the same as the simple filter.

>[!NOTE]
>
>Spaces cannot be used in filters, because spaces are delimiters in searches

**Does not contain**

Matches if the term is not found anywhere in the line item. You can filter "unspecified", "none", "keyword unavailable" and other [special values](https://experienceleague.adobe.com/docs/analytics/technotes/unspecified.html) from reports using "does not contain".

Does not contain: `none`

For a more exact filter, you can use an Advanced (Special Characters) filter: 

* Advanced (Special Character): `-^none$`
* Advanced (Special Character): `-"keyword unavailable"`

For example, the following line item is filtered by the "Does not contain" criteria, but is not filtered by the "Advanced (Special Character)" criteria:

```
help:Rename the None classification key
```

**Contains One Of**

Matches if any terms, separated by spaces, are found in the line item. The following filter shows all pages that contain "mens" or "sale": 

Contains One Of: `mens sale`

Matches the following pages: 

```
Womens
Mens
Mens:Desk & TravelJewelry & Accessories:Accessories:Hats:Mens
Sale & Values
```

**Equals**

Matches if the entire line item, including spaces and other characters, match the specified phrase.

Equals: `mens:desk & travel`

`Mens:Desk & Travel`

**Starts With**

Matches if the line item, including spaces and other characters, starts with the specified phrase.

Starts With: `mens`

Matches the following pages: 

```
Mens
Mens:Desk & Travel
Mens:Apparel
Mens Perfume Spray
Mens Hemp/Bamboo Flip Flops
```

**Ends With**

Matches if the line item, including spaces and other characters, ends with the specified phrase.

Ends With: `jean`

Matches the following pages: 

```
Bell Bottom Jean
Velvet Dream Skinny Leg Jean
Dark Slimmer Jean
Bling Belt High Waist Jean
Ocean Blue Jean
```

## Advanced (Special Character) {#section_83DA3B6C23EB4C119DB6D74062DB501D}

Advanced let you perform wildcard and other complex searches.

| Advanced (Special Character) | Description |
|--- |--- |
|`" "`|Match exact phrase.|
|`*`|Wild card, greedy matching. <br>For example, `r*p`  matches "Registration Signup".|
|`^`|Starts with. <br>Do not include a space between the special character and the search phrase.|
|`$`|Ends with. <br>Do not include a space between the special character and the search phrase.|
|`-`|Not. <br>Do not include a space between the special character and the search phrase.|
|`|`|Or<br>Note:  you must include a space on each side of the pipe character, `" | "`.|

## Create report-specific filters {#task_DEBB0632411D4CA8AA0B3BA267A5B35F}

Steps that describe how to create filters for reports.

<!-- 

t_reports_filter_specific.xml

 -->

Certain reports contain a filter that is specific to that report. For example, a [!UICONTROL Purchase Conversion Funnel Report] lets you filter by web pages. A [!UICONTROL Geosegmentation Report] lets you filter by geographical region. Additional reports have other filters specific to those reports.

When you access these filters, you can see report metrics for the items specified in the list.

**To create report-specific filters** 

1. Generate a report, such as a [!UICONTROL Purchase Report] ( **[!UICONTROL Site Metrics]** > **[!UICONTROL Purchases]** > **[!UICONTROL Purchase Conversion Funnel]**).
1. In the report header, click the **[!UICONTROL Filter]** link.
1. On the [!UICONTROL Filter Selector] page, click **[!UICONTROL Apply a Filter]**, then select a filter type.
1. To search for an item, type a character string in the **[!UICONTROL Search]** field.
1. Click **[!UICONTROL OK]**.

## Add a correlation filter {#task_065042E384DA4BF3864C58AF2B88D6E2}

Steps that describe how to add a correlation filter.

<!-- 

t_reports_correlation_filter.xml

 -->

Certain reports let you add custom correlation filters. For example, if you are viewing the [!UICONTROL Pages Report] for a report suite that has Site Sections correlated with a Women's page, you can create a filter rule that generates a report showing the most popular pages when Site Sections = Women.

You can filter the data shown in a correlation report using any available correlation. The example here shows how you add a search engine correlation filter.

**To add a correlation filter** 

1. Run a report that supports correlations. (See [Running a Breakdown Report](/help/analyze/reports-analytics/reports-customize/breakdowns.md#task_F685624830E64C829C8BE6435A107F69).)
1. In the report header, click the **[!UICONTROL Correlation Filter]** link.
1. Under [!UICONTROL Filter Rule Creator], select a category to correlate with an item.
1. Click **[!UICONTROL OK.]**
