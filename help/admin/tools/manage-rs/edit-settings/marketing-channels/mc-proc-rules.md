---
title: Processing rules for Marketing Channels
description: Use rules to determine which marketing channel a hit belongs to.
feature: Marketing Channels
exl-id: 825f70a5-cce3-4b1c-bb42-828388348216
role: Admin
---
# Marketing Channel processing rules

_This page refers to processing rules that assigns a marketing channel to a hit. See [Processing rules](../general/processing-rules/pr-overview.md) for the feature that allows you to adjust how data is collected._

Marketing Channel processing rules allow you create logic that determines the value for the [Marketing Channel](/help/components/dimensions/marketing-channel.md) and [Marketing Channel Detail](/help/components/dimensions/marketing-detail.md) dimensions. Use the [Marketing Channel manager](c-channels.md) to determine what marketing channels you use, then use processing rules to determine how each channel is set.

![Marketing channel buckets](assets/buckets_2.png)

**[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Report Suites]** > **[!UICONTROL Edit Settings]** > **[!UICONTROL Marketing Channels]** > **[!UICONTROL Marketing Channel Processing Rules]**

Once the [Automatic setup](/help/components/c-marketing-channels/c-getting-started-mchannel.md) runs, it creates a rule for each channel generated during setup.

![Default rules](assets/marketing_channel_rules.png)

You can use multiple rules to define a single marketing channel. Using multiple rules for a single channel can be beneficial if you want to set the channel detail differently depending on rule conditions. You can also use multiple conditions to define a single rule.

## Rule definitions

Each rule contains a condition and an assignment:

* **[!UICONTROL If any/all of the following are true]**: If you add multiple conditions to a single rule, you can determine if all the conditions must be met or any one of the conditions be met to set the channel and associated value.
* **Rule conditions**: Specify one or more rule conditions that must be met. Typically you specify a dimension that a hit must match to qualify for the marketing channel.
* **[!UICONTROL Then do the following]**: When the rule conditions match, set [Marketing Channel](/help/components/dimensions/marketing-channel.md) ([!UICONTROL Identify the channel as]) and [Marketing Channel Detail](/help/components/dimensions/marketing-detail.md) ([!UICONTROL Set the channel's value]).

## Rule conditions

The following options are available when setting rule conditions.

>[!NOTE]
>
>All text fields are evaluated as **case-insensitive**. For example, if you use a rule condition where query string parameter `cmp` equals `abc123`, both the query string parameter and value can use any combination of uppercase and lowercase.

**Adobe-detected conditions** do not contain any options or fields to enter text.

| Adobe-detected condition | Description |
|---|---|
| **[!UICONTROL Matches Paid Search Detection Rules]** | The hit originated from a recognized search engine and matched [Paid search detection rules](../general/paid-search-detection/paid-search-detection.md). |
| **[!UICONTROL Matches Natural Search Detection Rules]** | The hit originated from a recognized search engine and did not match paid search detection rules. |
| **[!UICONTROL Referrer Matches Internal URL Filters]** | The hit contained a [Referrer](/help/components/dimensions/referrer.md) that matched [Internal URL filters](../general/internal-url-filter-admin.md). |
| **[!UICONTROL Referrer Does Not Match Internal URL Filters]** | The hit contained a referrer that did not match internal URL filters. |
| **[!UICONTROL Is First Hit of Visit]** | The hit was the first in a visit. |
| **[!UICONTROL Referrer Is Social Network]** | The [Referrer type](/help/components/dimensions/referrer-type.md) is "Social networks". |
| **[!UICONTROL Referrer Is Not Social Network]** | The referrer type is not "Social networks". |
| **[!UICONTROL Referrer Is Conversational AI]** | The referrer type is "Conversational AI". |
| **[!UICONTROL Referrer Is Not Conversational AI]** | The referrer type is not "Conversational AI". |

**Hit attributes** allow you to specify a dimension, a matching operator, and a value to look for.

| Hit attribute condition | Description |
|---|---|
| **[!UICONTROL Page]** | The [Page](/help/components/dimensions/page.md) dimension. |
| **[!UICONTROL Page Domain]** | The domain of the URL. For example, `products.example.com`. |
| **[!UICONTROL Page Domain And Path]** | The domain and path of the URL. For example, `products.example.com/mens/pants/overview.html`. |
| **[!UICONTROL Page Root Domain]** | The root domain of the URL. For example, `example.co.uk`. |
| **[!UICONTROL Page URL]** | The full page URL. |
| **[!UICONTROL Query String Parameter]** | An individual query string parameter in the page URL. Use one query string parameter per rule condition. If you want to include multiple query string parameters in a rule, use multiple rule conditions. |
| **[!UICONTROL Referrer]** | The [Referrer](/help/components/dimensions/referrer.md) dimension. |
| **[!UICONTROL Referring Domain]** | The [Referring Domain](/help/components/dimensions/referring-domain.md) dimension. |
| **[!UICONTROL Referring Domain And Path]** | A concatenation of referring domain and the referrer's URL path. For example, `www.example.com/products/id/12345` or `ad.example.com/foo`. |
| **[!UICONTROL Referring Parameter]** | A query string parameter within the referrer. |
| **[!UICONTROL Referring Root Domain]** | The referring root domain. |
| **[!UICONTROL Search Engine]** | The [Search engine](/help/components/dimensions/search-engine.md) dimension. |
| **[!UICONTROL Search Keyword(s)]** | The [Search keyword](/help/components/dimensions/search-keyword.md) dimension. |
| **[!UICONTROL Search Engine + Search Keyword(s)]** | A concatenation of search engine and search keyword. |
| **[!UICONTROL AMO ID]** | The primary tracking code used by the Adobe Advertising and Advertising Analytics integrations. When one of these integrations is enabled, then the tracking code prefix can be used to identify Advertising specific channels. Values beginning with "AL" are for Search and Social. Values beginning with "AC" are for Display. When the AMO ID is used in marketing channels, click/cost/impression metrics can be attributed to the correct channel. |
| **[!UICONTROL AMO EF ID]** | The secondary tracking code used by Adobe Advertising. Serves as the key for sending data back to Advertising. It can be used to identify display click throughs and display view throughs as two separate marketing channels. To do this, set the marketing channel logic for "AMO EF ID" ends with `:d` for display click throughs, or "AMO EF ID" ends with `:i` for display view throughs. If you do not desire to split display into two channels, use the AMO ID dimension instead. |

**Conversion variables** allow you to specify a custom eVar, a matching operator, and a value to look for.

| Converation variable condition | Description |
|---|---|
| **eVar 1-250** | The associated [eVar](/help/components/dimensions/evar.md) dimension. |
