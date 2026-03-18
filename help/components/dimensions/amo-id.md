---
title: AMO ID
description: The Adobe Media Optimizer ID, used in Adobe Advertising integrations.
feature: Dimensions
---
# AMO ID

The **[!UICONTROL AMO ID]** is a collection of concatenated identifiers used in Adobe Advertising integrations. Values stored in this dimension are automatically organized into separate, more human-readable classification dimensions for use in Analytics reporting. The dimension is automatically created when enabling the [Analytics for Advertising](https://experienceleague.adobe.com/en/docs/advertising/integrations/analytics/overview) integration.

## Populate this dimension with data

This dimension collects its values in multiple ways:

* For click-through traffic, data is collected from the `s_kwcid` query string parameter in the [Page URL](page-url.md), usually on the page through which ad-driven traffic enters the site.
* Click-through traffic can also be captured when the URL does not contain tracking codes, but the Adobe Advertising JavaScript detects a click within the prior two minutes.
* For supported view-through traffic, Adobe Advertising supplements values on the backend using a supplemental ID (`SDID`).

## Dimension items

Dimension items include AMO IDs, also called `s_kwcid` values. The exact format depends on whether traffic originated from DSP or from Search, Social, & Commerce. AMO IDs are less granular than EF IDs and are primarily used for classifications and ingestion of Adobe Advertising metrics in Analytics.

### DSP

```text
AC!{ad key}!{placement key}
```

* **`AC`**: Indicates the display channel.
* **`ad key`**: Adobe Advertising-generated alphanumeric identifier for the ad.
* **`placement key`**: Adobe Advertising-generated alphanumeric identifier for the placement.

Example value:

```text
AC!iIMvXqlOa6Nia2lDvtgw!GrVv6o2oV2qQLjQiXLC7
```

### Search, Social, & Commerce ads

Search, Social, & Commerce AMO IDs begin with `AL`, followed by the advertiser user ID, the ad network account ID, then network-specific identifiers. Shared ad network account IDs include:

* **`3`**: Google Ads
* **`10`**: Microsoft Advertising
* **`45`**: Meta
* **`86`**: Yahoo! Display Network
* **`87`**: Naver
* **`88`**: Baidu
* **`90`**: Yandex
* **`94`**: Yahoo! Japan Ads
* **`105`**: Yahoo Native (deprecated)
* **`106`**: Pinterest (deprecated)

#### Google Ads

Google Ads uses two related formats. Newer accounts can include campaign ID and ad group ID, which supports campaign- and ad group-level reporting for Performance Max and drafts/experiments campaigns.

```text
AL!{user}!3!{creative}!{matchtype}!{placement}!{network}!{product partition}!{keyword}[!{campaign id}!{ad group id}]
```

* **`creative`**: Google Ads creative ID.
* **`matchtype`**: Keyword match type (`e` for exact, `p` for phrase, `b` for broad).
* **`placement`**: Domain on which the ad was clicked.
* **`network`**: Network on which the click occurred (`g` for Google search, `s` for a search partner, `d` for display).
* **`product partition`**: Product group ID for product ads.
* **`keyword`**: Triggering keyword on search sites, or best-matching keyword on content sites.
* **`campaign id`**: Google Ads campaign ID, when present.
* **`ad group id`**: Google Ads ad group ID, when present.

For dynamic search ads, the keyword field is populated with the auto target.

Example:

```text
AL!1234!3!569345525675!e!!g!!adobe express!15557590691!136734402131
```

#### Microsoft Advertising

```text
AL!{user}!10!{ad id}!!!!{keyword/order item id}!!{campaign id}!{ad group id}
```

* **`ad id`**: Microsoft Advertising creative ID.
* **`keyword/order item id`**: Microsoft Advertising keyword ID.
* **`campaign id`**: Microsoft Advertising campaign ID.
* **`ad group id`**: Microsoft Advertising ad group ID.

Legacy Microsoft formats can still exist for some non-migrated accounts.

Example:

```text
AL!1234!10!79577297926903!!!!79577437127536!!291647087!1273234845019564
```

#### Baidu

```text
AL!{user}!88!{creative}!{placement}!{keyword id}
```

* **`creative`**: Baidu creative ID.
* **`placement`**: Website on which the ad was clicked.
* **`keyword id`**: Baidu keyword ID.

#### Yahoo! Japan Ads

```text
AL!{user}!94!{creative}!{matchtype}!{network}!{keyword}
```

* **`creative`**: Yahoo! Japan Ads creative ID.
* **`matchtype`**: Keyword match type (`be` exact, `bp` phrase, `bb` broad).
* **`network`**: Network on which the click occurred (`n` native, `s` search).
* **`keyword`**: Triggering keyword.

#### Yandex

```text
AL!{user}!90!{ad id}!{source type}!!!{phrase id}
```

* **`ad id`**: Yandex creative ID.
* **`source type`**: Site type on which the ad was displayed (`b` search, `c` context/content, `ct` category).
* **`phrase id`**: Yandex keyword ID.

## Classifications

When enabling the [Analytics for Advertising](https://experienceleague.adobe.com/en/docs/advertising/integrations/analytics/overview) integration, the following classifications are automatically created. Classification values are automatically maintained by the integration.

| Classification | Description | DSP | Search,<br>Social, &<br>Commerce |
| --- | --- | :---: | :---: |
| **[!UICONTROL Account]** | The account name. | &check; | &check; |
| **[!UICONTROL Ad Display URL]** | The URL displayed in the ad. | | &check; |
| **[!UICONTROL Ad Description]** | The ad description (DSP) or ad body (Search, Social, & Commerce). | &check; | &check; |
| **[!UICONTROL Ad Destination URL]** | The destination URL for the ad. | | &check; |
| **[!UICONTROL Ad Group]** | The ad group name. | | &check; |
| **[!UICONTROL Ad Platform]** | The advertising DSP or search engine name. | &check; | &check; |
| **[!UICONTROL Ad Title]** | The ad type (DSP) or ad title (Search, Social, & Commerce). | &check; | &check; |
| **[!UICONTROL Ad Type]** | The ad type, such as `text`, `video`, `display`, or `native`. | &check; | &check; |
| **[!UICONTROL AdCloud Attribute 1]** -<br>**[!UICONTROL AdCloud Attribute 5]** | Placeholder classifications reserved for future custom attributes. Not currently in use. | | |
| **[!UICONTROL Campaign]** | The campaign name. | &check; | &check; |
| **[!UICONTROL Creative Experience Name]** | Name of the creative experience associated with the ad interaction, representing a group of creative variations used in testing or personalization. | &check; | |
| **[!UICONTROL Creative Branch Name]** | Name of the branch within a creative experience that represents a specific variation or path in the creative experiment. | &check; | |
| **[!UICONTROL Creative Branch ID]** | Unique identifier assigned to a creative branch within a creative experience. | &check; | |
| **[!UICONTROL Creative Name]** | Name of the specific ad creative asset that was served to the user. | &check; | |
| **[!UICONTROL Creative Variant Name]** | Name of the specific variant of a creative used within a creative experience or branch. | &check; | |
| **[!UICONTROL Keyword]** | The keyword. | | &check; |
| **[!UICONTROL Keyword Match Type]** | The keyword and match type. | | &check; |
| **[!UICONTROL Landing Type]** | Whether the landing page entry was a view-through or a click-through. | &check; | &check; |
| **[!UICONTROL Match Type]** | The search match type. | | &check; |
| **[!UICONTROL Network]** | RTB (DSP) or the ad network name (Search, Social, & Commerce). | &check; | &check; |
| **[!UICONTROL Optimization]** | The package name (DSP) or portfolio name (Search, Social, & Commerce). | &check; | &check; |
| **[!UICONTROL Placement]** | The placement name. | &check; | |
| **[!UICONTROL Product Target]** | The product target for a product listing ad. | | &check; |
