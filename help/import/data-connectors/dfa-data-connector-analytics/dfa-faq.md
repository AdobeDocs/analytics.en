---
description: null
keywords: DFA
seo-description: null
seo-title: Frequently Asked Questions
solution: Analytics
title: Frequently Asked Questions
topic: Data connectors
uuid: 59d187e9-1ec1-4cf3-8831-b981f87c9372
---

# Frequently Asked Questions{#frequently-asked-questions}

## Why won't the Data Connectors wizard accept my login credentials? {#section-f019b3de18774df3954af7881aa564fa}

If you have verified that the login credentials are valid, next verify that the username provided to the integration is enabled for API access. The Data Connectors wizard uses the DFA API to validate login credentials, as well as turn off and on Adobe-specific settings in the DFA API. API Access is a setting that must be turned on from within the DFA interface by an administrator. Next, make sure that you have permission to access the Advertiser ID or the Floodlight Configuration ID selected in the wizard.

## Why am I not seeing any data from the nightly uploaded metrics (DFA Impressions, DFA Clicks, etc)? {#section-465fd22ae6b447ffb6baf20b57daa433}

If you are using version 1.5 of the integration, this could be because your integration has not yet been assigned a Client Site ID. A Client Site ID (CSID) is required for the nightly exchange to occur, and to request data from the DFA ad server. CSIDs can take up to 3 days from the date of integration to be exchanged with Google. Once the CSID has been received from Google, you will be notified via the integration's email address of the new CSID, along with the latest JavaScript code.

If it has been more than 3 days and you have not received the setup email and metrics are not flowing, then the most likely problem is that the CSID has already been assigned to another integration. Google maintains a 1 to 1 mapping between CSID and Report Suite, meaning that if an integration in one report suite uses same Advertiser ID as another integration in another report suite, only the first one will be assigned a CS ID. To change which report suite or Advertiser ID a CSID is mapped to, a ticket must be opened with Google Support.

For example, say there is an integration in Report Suite A with Advertiser ID Z which gets assigned a CSID. If another integration is later setup in Report Suite B with Advertiser Z, this newer integration will NOT be re-assigned the CSID. This would require a Google ticket. On the other hand, take the example of an integration in Report Suite A, with Advertiser ID Z, and later another integration in Report Suite A, Advertiser Z is setup. Only the first Integration will receive data for the integration; however, in this case, the first integration can be deactivated and data will flow to the second integration.

> [!NOTE] CSIDs are not used in version 2.0 of the integration and so the CSID negotiation process does not apply.

## I am using version 2.0 of the integration and cost metrics are not appearing for my DFA ads. Why might this be? {#section-805748111bbe4bbf918d6dbbb2641fff}

Cost metrics have to be both turned on from both the Google DFA side, and supplied in the DFA interface, as well as turned on in the Data Connectors wizard. The first place to verify is that you have mapped an Analytics event for DFA Media Cost, and supplied a currency code. If you have mapped the Media Cost event, and finish and save the wizard, the DFA omnitureCostData flag will be turned on in the DFA API. This will signal to Google that the metrics should be sent in the nightly file. You can double check via the DFA interface that omnitureCostData is enabled by looking at properties on the integrated Floodlight. Finally, after checking these two places, ensure that the ads that are part of the integrated Floodlight specify cost data and cost structures. If cost data is not provided in the DFA interface, it will not show up in Analytics.

## Why do certain ads not show any DFA Impressions or view-throughs, but they do show clicks and click-throughs? {#section-39b2eeeefd7f43d1a373df0b987bacef}

There are some ads which only record click data, called clicktrackers. These type of ads do not return last impression data from when the Floodlight server is queried. To verify if a certain ad is a clicktracker or click-only ad, contact either your DFA agency or your Google Support representative.

## Why aren't there any click-throughs for ads that show DFA Clicks? {#section-758c1f1fc5b54bfc9294dcdc71bbd96a}

There can be one of many answers to this.

First, check that the ad in question has a landing page URL which is both (a) tagged with Adobe code for the same report suite you are viewing the discrepancy in and (b) contains the *`clickThroughParam`* query string parameter.

Second, verify that you have a working integration by following through the steps in [Confirming a Successful DFA Integration](../dfa-data-connector-analytics/dfa-integration.md). If you see a DFA tracking code come through with the Adobe hit on the landing page, then you should see that Click-through come in the DFA Campaigns report. If you are not seeing it come through, verify that the report suites match between the landing page's *`s.account`* variable, and the report suite being viewed in Reports & Analytics. If these match, check for tracking codes in the View Through eVar report that look like DFA:XXX:XXX:XXX:llXXX:XXX:XXX:XXX:XXX.

These indicate failures of the DFA VISTA rule to digest the raw data from DFA. This problem can be remedied by opening a support ticket through your Adobe Account Representitive.

If none of the solutions above explain the problem, see [Reconciling Metric Discrepancies](../dfa-data-connector-analytics/dfa-reconciling-metric-discrepancies.md) to explore other possibilities.