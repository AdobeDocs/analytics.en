---
title: Best practices for implementing Adobe Analytics Marketing Channels
description: Updated best practices for using Marketing Channels with Attribution and Customer Journey Analytics
feature: Marketing Channels
exl-id: a0ab818d-7165-4f34-bc43-1ed8d6215800
TQID: https://experienceleague.adobe.com/mKq-l0nm-MFJjcvWoIwUfQ2QM-dYD6VlcfH-CszsUv8
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
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
---
# Attribution with Marketing Channels - Best Practices

[Marketing Channels](/help/components/c-marketing-channels/c-getting-started-mchannel.md) are a valuable and powerful feature of Adobe Analytics. The current guidance regarding Marketing Channel implementation was formulated at a time when neither [Attribution](/help/analyze/analysis-workspace/attribution/overview.md)  nor [Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-usecases/marketing-channels.html#cja-usecases) existed.

In order to future-proof your Marketing Channels implementation and to ensure that there is reporting consistency with Attribution and with Customer Journey Analytics, we are issuing a set of updated best practices. If you are already using Marketing Channels, you can choose the best options among these new guidelines. If you are new to Marketing Channels, we would advise you to adhere to all new best practices.

When Marketing Channels were first introduced, they came with only first-touch and last-touch dimensions. Explicit first/last touch dimensions are no longer needed with the current version of attribution. Adobe provides generic 'Marketing Channel' and 'Marketing Channel Detail' dimensions so you can use them with your desired attribution model. These generic dimensions behave identically to Last-Touch Channel dimensions, but are labeled differently to prevent confusion when using Marketing Channels with a different attribution model.

Since Marketing Channel dimensions depend on a traditional Visit definition (as defined by their processing rules), their Visit definition cannot be changed using virtual report suites. These revised practices enable clear and controlled lookback windows with Attribution and with Adobe Analytics.

## Best Practice #1: Leverage Attribution for controlled analysis

We recommend using [Attribution](/help/analyze/analysis-workspace/attribution/overview.md) instead of the existing Marketing Channel attribution to fine tune your Marketing Channel analysis. Follow the other best practices to ensure consistency and robust controls over your analysis with Attribution.

![](assets/attribution.png)

* Configuration of the dimensions Marketing Channel and Marketing Channel Detail establishes touchpoints to be evaluated, corresponding to each Marketing Channel Instance.
* For metric analysis, your organization should align on one or more attribution model/s. Save custom metrics with this model for easy reuse.
* By default, data is allocated using Last Touch and the setting of the Visitor Engagement Period. Attribution metric models offer greater control over the lookback windows and more variety, including [algorithmic attribution](/help/analyze/analysis-workspace/attribution/algorithmic.md#analysis-workspace).

## Best Practice #2: No Direct and Session Refresh channel definitions

Direct and Internal/Session Refresh channels are not recommended for use with custom attribution models.

What if your organization already has Direct and Session Refresh configured? In this case, Adobe recommends that you [create a classification](/help/admin/tools/manage-rs/edit-settings/marketing-channels/classifications-mchannel.md) for First Touch/Last Touch and leave Direct and Session Refresh channels unclassified. The classified dimension yields Attribution results similar to the case where those channels were never configured.

![](assets/direct-session-refresh.png)

If you disable these channels and remove their marketing channel processing rules, the results differ slightly from the classification approach. The value `None` represents visits that did not match any marketing channel processing rules. Differences can appear when a visit matching no channel follows a visit that matches a channel.

You can still use custom attribution models to apply lookback windows and attribution models in either case.

## Best Practice #3: Enable Override Last-Touch Channel for all channels

Custom attribution models used with the Marketing Channel dimension in Workspace work best when this setting is enabled. Enabling this setting causes a Marketing Channel Instance to count when a new channel/detail is encountered. You should enable this for all channels except for Direct or Internal/Session Refresh, which we no longer recommend for use with custom attribution models.

![](assets/override.png)

## Best Practice #4: Minimize Visitor Engagement period

Setting the Visitor Engagement period to the minimum of "1 Day" minimizes the likelihood of persisting values. Because custom attribution models (AIQ) allow flexible lookback windows, we recommend setting the minimum value to minimize the impact of this setting.

![](assets/expiration.png)

## Best Practice #5: Marketing Channels Processing Rules should exist only for enabled channels

Ensure that you remove any Marketing Channel Processing Rules for disabled channels. Rules should exist only for Marketing Channels that are checked as enabled.
