---
title: Processing rules for Marketing Channels
description: Marketing Channel processing rules determine if a visitor hit meets the criteria assigned to a channel. The rules process every hit a visitor makes on your site. When a rule does not meet the criteria for a channel, or if rules are not configured correctly, the system assigns the hit to No Channel Identified.
feature: Marketing Channels
exl-id: 825f70a5-cce3-4b1c-bb42-828388348216
---
# Processing rules for Marketing Channels

>[!NOTE]
>
> For general information on Marketing Channels, see [Get started with Marketing Channels](/help/components/c-marketing-channels/c-getting-started-mchannel.md).
>
> To maximize effectiveness of Marketing Channels for Attribution IQ and Customer Journey Analytics, we have published some [revised best practices](/help/components/c-marketing-channels/mchannel-best-practices.md).

**[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Report Suites]** > **[!UICONTROL Edit Settings]** > **[!UICONTROL Marketing Channels]** > **[!UICONTROL Marketing Channel Processing Rules]**.

Marketing Channel processing rules determine if a visitor hit meets the criteria assigned to a channel by processing every hit a visitor makes on your site. The rules are processed in the order you specify, and when a rule is met, the system stops processing the remaining rules. 

![](assets/buckets_2.png)

Additional notes about processing :

* Data collected with these rules are 100% permanent, and rules altered after data is collected is not retroactive. We strongly recommend that you review and consider all circumstances before saving [!UICONTROL Marketing Channel Processing Rules] to mitigate data being collected in incorrect channels.
* The report can process up to 25 channels at a time.
* Rules can access variables that VISTA has set, but cannot access data that VISTA has deleted.
* Two marketing channels never receive credit for the same event (such as purchases or clicks). In this way, marketing channels differ from eVars (where two eVars might receive credit for the same event).
* If there is a gap coverage of your rules, you may see [No Channel Identified.](/help/components/c-marketing-channels/c-faq.md)

## Prerequisites

* Review the conceptual information in [Getting Started with Marketing Channels](/help/components/c-marketing-channels/c-getting-started-mchannel.md).
* Create one or more channels so that you can assign rules to them. See [Add marketing channels.](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/marketing-channels/c-channels.md).
* Review the best practices for using [!UICONTROL Marketing Channels] with [!UICONTROL Attribution IQ].

## Create Marketing Channel processing rules

Create Marketing Channel processing rules, which determine if a visitor hit meets the criteria assigned to a channel.

1. Click **[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Report Suites]**.
2. Select a report suite.

   If your report suite does not have channels defined, the [!UICONTROL Marketing Channels: Auto Setup] page displays.

   See [Run the Automatic Setup](/help/components/c-marketing-channels/c-getting-started-mchannel.md).

3. Click **[!UICONTROL Edit Settings]** > **[!UICONTROL Marketing Channels]** > **[!UICONTROL Marketing Channel Processing Rules]**. If you ran the automatic setup, a set of channel and rules were automatically defined for you.

   ![Step Result](assets/marketing_channel_rules.png)

4. If you want to add a new rule, select from the **[!UICONTROL Add New Rule Set]** menu. If you select a channel, you are given a rule template and if you select Custom, you start from a blank slate. Both options allow you to modify the rule set as needed. 

   ![Step Result](assets/example_email.png)

5. To continue creating rules, click **[!UICONTROL Add New Rule SetRule]**.
6. To prioritize rules, drag-and-drop them to the desired position.
7. Click **[!UICONTROL Save.]**

Continue down this page to see recommendations for channel rule order as well as more definition examples.

### Set the marketing channel value

**[!UICONTROL Set the channel's value]** defines the marketing channel detail dimension that is available for that channel. This enables you to breakdown Marketing channel dimensions and see more detailed information about the channel.

It is recommended that the channel value be set to the same criteria used to define the channel itself. For example, if query string parameter is used to define the channel, set query string parameter as the channel value as well.

### Rule criteria

This reference table defines the fields, options, and hit attributes you can use to define Marketing Channel Processing Rules. 

>[!NOTE]
>
>Any text field you define, such as query string parameter or lists of values to match against, are evaluated as **case-insensitive** values. For example, if you have a rule where query string parameter cmp = abc123, all versions of both 'cmp' and 'abc123' will match the rule. You do not need to list multiple case versions of these values. 

| Term  | Definition  |
|--- |--- |
|All|Activates this channel only when all of the rules in the numbered rule are true.|
|Any|Activates this channel when any of the rules in the rule set are true. This option is available only if more than one rule exists in the numbered rule.|
|AMO ID|The primary tracking code used by the Advertising Cloud and Advertising Analytics integrations. When one of these integrations is enabled, then the tracking code prefix can be used to identify Advertising Cloud specific channels. Use "AMO ID" starts with "AL" for Search, "AC" for Display, or "AO" for Social. When the AMO ID is used in marketing channels the click/cost/impression metrics can be attributed to the correct channel (when not configured, these metrics will go to Direct or None).|
|AMO ED ID|The secondary tracking code used by Advertising Cloud. The main purpose of this tracking code is to serve as the key for sending data back to Ad Cloud. It can however also be used to identify display ClickThroughs vs. display ViewThroughs if you desire to see these as two separate marketing channels. This can be done by setting the marketing channel logic for "AMO EF ID" ends with ":d" for Display ClickThroughs or "AMO EF ID" ends with ":i" for Display ViewThroughs. If you do not desire to split Display into two channels, then use the AMO ID dimension instead.|
|Conversion Variables|Consists of eVars that are enabled for this report suite, and applies only when these variables are set via the Adobe code on the page.  See the  Implementation Guide .|
|Exists|Several selections are available, including:<ul><li>**Does Not Exist**: Specifies that the hit attribute does not exist on the request. For example, in a referring domain, if the user types a URL or clicks a bookmark, the referring domain attribute does not exist.</li><li>**Is Empty**: Specifies that a hit attribute exists, usually an eVar or query string parameter, but there is no value associated with the hit attribute.</li><li>**Does Not Contain**: Lets you specify, for example, that a referring domain does not contain a specific value (as opposed to using the selection "Contains".)</li></ul>|
|Identify the channel as|Associates the rule with a marketing channel that you added to the  Marketing Channel Manager  page.  See  Add marketing channels .|
|Matches Paid Search Detection Rules|A paid search detected by Adobe. Paid searches are when companies pay a fee for the search engine to list their site. Paid searches usually appear at the top or the right side of the search results.|
|Matches Natural Search Detection Rules|A non-paid search detected by Adobe reporting.|
|Referrer Matches Internal URL Filters|A visit whose page URL matches an internal URL filter, as defined for the report suite in Admin Tools.|
|Referrer Does Not Match Internal URL Filters|The referring URL does not match an internal URL filter, as defined for the report suite in Admin Tools. You can use this setting with  Page URL  and  Exists  to set up a catch-all rule, so that no visits land in the  No Channel Identified  section of the report.|
|Ignore hits matching internal URL filters|(For referrers) Tracks only hits coming from externally referred sites. Typically, leave this setting enabled unless you want to include internal traffic.|
|Is First Page of Visit|The first page of a visit detected by Adobe reporting.|
|Page|The page name of a web page on your site that is tagged using Adobe's web beacon. This value is equivalent to  s.pageName . Examples include `Home Page` and `About Us`.|
|Page Domain|The domain of the page on which the visitor lands, such as `products.example.co.uk`.|
|Page Domain and Path|The domain and path, such as `products.example.co.uk/mens/pants/overview.html` .|
|Page Root Domain (TLD+1)|The root domain of the page on which the visitor lands, such as example.co.uk .|
|Page URL|The URL of a web page on your site.|
|Referring Domain|The domain your visitors came from before they visited your site, for example, referrers coming from `abcsite.com` versus `xyzsite.com`.|
|Query String Parameter|If a page URL on your site looks like `https://example.com/?page=12345&cat=1`, then 'page' and 'cat' are both query string parameters. (See `https://en.wikipedia.org/wiki/Query_string`.)  You can specify only one query string parameter per rule set. To add additional query string parameters, use `ANY` as your operator, then add new query string parameters to the rule. Query string parameters are evaluated as case-insensitive; for example, 'cat' and 'CAT' will be evaluted the same way.|
|Referrer|The web page location (full URL) your visitors were at before coming to your site. A referrer exists outside your defined domain.|
|Referring Domain and Path|A concatenation of the Referring Domain and URL path. Examples include:    `www.example.com/products/id/12345` or `ad.example.com/foo`|
|Referring Parameter|A query string parameter on the referrer URL. For example, if your visitors come from `example.com/?page=12345&cat=1`, then page and cat are the referring parameters.|
|Referring Root Domain|The root domain of the referrer. A referrer exists outside of your defined domain.|
|Search Engine|A search engine like Google or Yahoo! that brought visitors to your site.|
|Search Keywords|A word used to perform a search using a search engine.|
|Search Engine + Keywords|A concatenation of the Search Keyword and Search Engine to uniquely identify the search engine. For example, if you search for the word computer, the search engine and keyword are identified as follows: `Search Tracking Code = "<search_type>:<search engine>:<search keyword>" where    search_type = "n" or "p", search_engine = "Google", and search_keyword = "computer"`**Note:** n = natural; p = paid|
|Set the channel's value to|In addition to knowing which marketing channel brings a visitor to your site, you can know which banner ad, search keyword, or email campaign within the channel is getting credit for a visitor's site activity. This ID is a channel value that is stored along with the channel. Often this value is a campaign ID embedded in the landing page or the referring URL; in other cases it is the search engine and search keyword combination, or the referring URL that most correctly identifies the visitor from a particular channel.|

## Marketing Channel rule order and definitions {#channel-rules}

Channel rules are processed in the order you specify. A recommended aproach to channel order is to place paid or managed channels first (e.g. paid search, natural search, display, email) so that they receive credit, followed by organic channels (e.g. direct, internal, referring domains).

Below is the recommended order for channel rules as well as example definitions:

### Paid Search {#paid-search}

Paid search is a word or phrase that you pay a search engine for placement in search results. This channel is typically defined based on query string parameter (see Display channel example) or paid search detection rules. The decision depends on the marketing channel detail you would like to record.

#### Paid search detection

To match paid search detection rules, the marketing channel uses settings configured on the [!UICONTROL Paid Search Detection] page. ( **[!UICONTROL Admin]** > **[!UICONTROL Report Suites]** > **[!UICONTROL Edit Settings]** > **[!UICONTROL General]** > **[!UICONTROL Paid Search Detection]**). The destination URL matches the existing paid search detection rule for that search engine.

For the marketing channel rule, the [!UICONTROL Paid Search] settings are as follows:

![](assets/example_paid_search.png)

See [Paid Search Detection](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/paid-search-detection/paid-search-detection.html) in Admin for more information.

### Natural Search {#natural-search}

A natural search occurs when visitors find your website through a Web search, where the search engine ranked your site without you paying for the listing. 

There is no natural search detection in Analytics. After you set up Paid Search Detection, the system knows that if a search referrer was not a paid search referrer, it must be a natural search referrer. See [Paid Search Detection](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/paid-search-detection/paid-search-detection.html) in the Admin for more information.

For the marketing channel rule, the Natural Search settings are as follows:

![](assets/example_natural_search.png)

### Display {#display}

This rule identifies visitors originating from banner advertisements. It is identified by a query string parameter in the destination URL, in this case *`Ad_01`*. Query string parameter and the values it looks for are evaluated as case-insensitive values.

![](assets/example_display.png)

### Email {#email}

This rule identifies visitors originating from email campaigns. It is identified by a query string parameter in the destination URL, in this case *`eml`*:

![](assets/example_email.png)

### Affiliates {#afilliates}

This rule identifies visitors that originate from a specified set of referring domains. In the rule, you list the domains of affiliates you would like to track, as follows:

![](assets/example_affiliates.png)

### Other Campaigns {#other-campaigns}

A best practice is to include an "Other campaigns" channel following all paid channel rules. This channel acts as a catch-all for uncategorized paid traffic.

![](assets/other-campaigns.png)

### Social Networks {#social-networks}

This rule identifies visitors that originate from a social network, such as Facebook;. The channel is often renamed to Organic Social. The settings can be as follows:

![](assets/example_social.png)

### Internal (Session Refresh) channel {#internal}

This rule visitors where their referring URL matches the Internal URL Filters setup in the Admin Console, meaning the visitor came from within the site to start their visit. This channel is often renamed to Session Refresh.

![](assets/int-channel1.png)

See [Reasons for Internal (Session Refresh)](https://experienceleague.adobe.com/docs/analytics/components/marketing-channels/c-faq.html#internal) for more information on why this channel occurs.

### Direct {#direct}

This rule identifies visitors that have no referring domain, which includes visitors that come to your site directly, such as from a Favorites link or by pasting a link in their browser. This channel is often renamed to Direct Typed/Bookmarked.

![](assets/example_direct.png)

### Referring Domains channel {#referring-domains}

The Referring Domains channel identifies visitors that have a referring domain. Together, the Internal, Direct, and Referring domains channels act as a catch-all for all remaining hits that have not yet been categorized into a channel.

![](assets/referring-domains.png)
