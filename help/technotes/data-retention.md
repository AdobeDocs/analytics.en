---
title: Data retention policy
description: A data retention policy determines how long Adobe stores your data.
exl-id: f3bb02d2-380d-4eb7-8449-e0318fc8c0a6
feature: Data Governance
TQID: https://experienceleague.adobe.com/ymM-0bethfijutq5sprEuEfOFgw3Xn4gTsLNNgKTEio
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
    internal-label: Analysis Workspace
  - id: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
    internal-label: API
  - id: ff9b434a-2221-4df7-81d1-5bcbf5f80bce
    internal-label: Admin Tools
subfeature_v2:
  - id: ef60b66e-5984-4336-ba72-6d978b1b6f87
    internal-label: Report suites
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: c7d04a2c-412a-4c9d-9d7a-4456eaa5adeb
    internal-label: Governance
  - id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
    internal-label: Privacy
---
# Data retention policy

Data collected by Adobe Analytics is retained for a specific period of time. The time that Adobe keeps this data varies from contract to contract, and is outlined in an organization's data retention policy. This policy applies to the data itself, which means that it affects all Analytics reporting capabilities (Analysis Workspace, reporting API, etc).

**The default data retention policy for Adobe Analytics is 25 months.** Your organization's retention policy can be different, depending on contract.

Data retained is based on the current date and the date/time of historical data. The date/time recorded on hits can be different than the date/time the hit(s) were received by Adobe.

## Adjust the default data retention period

If you would like to reduce or extend the default data retention period, contact your Adobe Account Team.

* There is no charge for reducing the default data retention period.
* Extending data retention beyond the default retention period of 25 months requires the purchase of extensions, which are available in increments of one year each. Up to eight extensions can be purchased, for a total of 10 years 1 month (2 years 1 month for default retention, plus 8 years purchased).

## Data retention and Data Privacy

Adobe, in its role as your data processor, must take appropriate measures to assist its customers in fulfilling access, deletion, and other requests from individuals. Applying appropriate, secure, and timely deletion policies is an important part of complying with this obligation. GDPR applies to all customers that market to or process information of EU citizens. CCPA applies to all customers that market to or process information of California citizens. Therefore, Data Privacy is a worldwide regulatory change.

## Data deletion

Once data exceeds your data retention policy, Adobe retains the right to delete it with no option for recovery. You must ensure that all data that you want to retain is within your organization's data retention policy.

## View/manage current data retention policy

The Data Governance dialog in [!UICONTROL Admin] Tools provides an overview of which report suites have been configured for data governance. It also indicates whether they have been mapped to a CX Enterprise organization, and whether a data retention policy is in place for this report suite.

## Frequently asked questions

+++ How do I decide on my organization's data retention period?

Your company, as the data controller, can identify stakeholders (such as your marketing, analytics, and privacy teams) within your organization responsible for making decisions about data retention. Your organization is in the best position to know the appropriate period for how long Adobe Analytics retains data.

+++

+++ How do I calculate the data retention window?

The data retention policy defines a rolling data retention window in which complete data can be viewed and reported. The data retention start date is determined by the current date minus the data retention period. The data retention end date is determined by the current date. Data is included in the data retention window if the timestamp of the data is between the start date and end date.

+++

+++ Can I request a copy of my data prior to it being deleted?

Yes. Adobe can provide a historical data dump of raw, hit-level data. See [Data Feeds](/help/export/analytics-data-feed/data-feed-overview.md) in the Export user guide for more information. If you have data export requirements outside the scope of what the UI can provide, contact your Adobe Account Team. Special accommodations can be made; costs may vary.

+++

+++ When does Adobe delete data?

Contact your Adobe Account Team for the specific time your data is scheduled to be deleted. Data is typically deleted on a rolling monthly basis.

+++

