---
title: Brand Visibility Integration
description: Integrate Brand Visibility with CAdobe Analytics
role: User
---

# Adobe Brand Visibility integration

[Adobe Brand Visibility](https://experienceleague.adobe.com/en/docs/llm-optimizer/using/home) is a generative AI-first application for Generative Engine Optimization, designed to help brands enhance their visibility, accuracy, and influence in AI-driven search environments. Brand Visibility provides insights into brand presence in AI-generated answers, offers prescriptive content recommendations, and automates optimization fixes.

AI has become a primary discovery channel. Large language model (LLM) agents, such as ChatGPT, Claude, Copilot, and Perplexity, crawl brand content. 

>[!NOTE]
>
>Brand Visibility was formerly referred to as **LLM Optimizer (LLMO)**. Some Adobe documentation may continue to use the former LLMO terminology during the transition.


>[!PREREQUISITES]
>
>You must have an Brand Visibility paid offering provisioned and connected to your Experience Platform configuration through the managed connector.


>[!IMPORTANT]
>
>As part of this integration, some temporary processing of Brand Visibility data occurs in the United States. Data is ultimately stored in your designated region as configured in your Adobe Analytics contract.

If you use Customer Journey Analyticsm a separate, richer inbound integration lands the same underlying CDN traffic data into Customer Journey Analytics through Adobe Experience Platform. That integration is available today. See [Brand Visibility integration with Customer Journey Analytics](https://experienceleague.adobe.com/en/docs/analytics-platform/using/integrations/bv). If you have Customer Journey Analytics, review that integration first, since it exposes more fields and supports joining Brand Visibility data with other datasets. The Analytics integration described in this guide is designed for customers who use Adobe Analytics without having access to or a license for Customer Journey Analytics.


## Use cases

You can benefit from the integration between Adobe Analytics and Brand Visibility in two ways:

* **Inbound integration**: Use Brand Visibility data in Adobe Analytics to measure LLM-driven traffic (bot crawlers, RAG requests, agent activity) alongside existing web and mobile data. For example, you can:
  
  * Measure LLM-driven traffic by agent source alongside traditional channels.
  
  * Identify content that is heavily consumed by LLMs but underperforms in human conversion.
  
  * Detect where LLM-agent requests fail across critical paths.

  * Compare LLM bot demand for a page against that page's conversions and revenue in your web data, matched at the URL and host level.
  
* **Outbound integration**: Send Adobe Analytics performance data into Brand Visibility so you can optimize AI visibility for the LLM sources that send you valuable traffic, such as ChatGPT or Perplexity. For example, you can:

  * See which LLM sources send human visitors who go on to convert or generate revenue. Adobe Analytics measures this from the referred web traffic, not from the bot dataset.
  * Rank LLM sources by the downstream value of the human visitors they send, then focus your AI visibility work on the sources that perform best.
  

## Inbound integration

This section describes the prerequisites and setup steps for the **Adobe Brand Visibility → Adobe Analytics** inbound integration.


The inbound Adobe Analytics connector is configured per report suite through the **Report Suite Manager**, described in Section 6.

>[!PREREQUISITES]
>
>CDN access logs must already be forwarded to and received by Adobe Brand Visibility for each Brand Visibility site before the Brand Visibility → Adobe Analytics connector can be enabled.
>
>This requirement applies on a **per-Brand Visibility-site basis**. A CDN configuration or log feed for one site, domain, or subdomain should not be assumed to cover another site unless Adobe confirms that coverage.
>
>
>Before enabling the connector, confirm:
>
>1. The relevant CDN or log pipeline is configured to forward the required access logs to the Adobe-provided destination.
>1. Brand Visibility  has confirmed that logs are being received and detected for the relevant site.
>1. Data is visible in your Brand Visibility  Agentic Traffic dashboard for that site.
>
>BYOCDN Log Forwarding provides the server-side CDN request data used for agentic-traffic analysis. The data does not depend on JavaScript tags running in a browser. Without the required CDN log feed, the connector will have no traffic data to bring into your report suite.
>
>See [BYOCDN Log Forwarding reference](https://experienceleague.adobe.com/en/docs/brand-visibility/using/log-forwarding/log-forwarding-overview) for more information.


>[!IMPORTANT]
>
>As part of this integration, some temporary processing of Brand Visibility data occurs in the United States. Data is ultimately stored in your designated region as configured in your Adobe Analytics contract.


### How it works

The inbound Brand Visibility → Adobe Analytics integration adds a set of **reserved variables** to your report suite. These variables carry summary-level data about bot and automated-agent traffic detected on your website, including LLM-based traffic, sourced from the same CDN access logs described in the [prerequisites](#inbound-integration).

This traffic generally does not run browser JavaScript tags and is not captured through your existing Adobe Analytics implementation. The reserved variables give you a way to see this traffic inside the same report suite you already use for your site.

The following reserved variables are added when the connector is enabled:

| Reported as | Type | Notes |
|---|---|---|
| URL | Dimension | The page URL associated with the request. |
| Bot Type | Dimension | The type of bot or automated agent that made the request (for example, a named AI crawler). |
| User Agent | Dimension | The user agent string reported by the bot or agent. |
| Status | Dimension | The HTTP status code returned for the request. |
| Referer | Dimension | The HTTP referer value for the request, when present. |
| Requests | Metric | The count of bot and agentic CDN requests. |


#### Coverage compared to Customer Journey Analytics

The CJA inbound integration is built on a broader CDN Requests Summary dataset and supports additional fields (for example, host and CDN provider) plus joining with other datasets in Customer Journey Analytics. The Adobe Analytics integration is a smaller, report-suite-native set of reserved variables designed to work within Analytics' existing data model. If your reporting needs go beyond the fields listed above, evaluate the CJA integration.

#### Important limitations

- No visitor ID, ECID, visits, or unique-user data is included. This is aggregated, non-visitor-tied summary data.
- The reserved variables do not support allocation type or expiration type settings, since they are not tied to a visitor.
- Data cannot be joined with other Analytics datasets or dimensions the way it can in Customer Journey Analytics.
- Use the **Requests** metric to measure bot and agentic traffic volume. Do not use it interchangeably with visit- or hit-based metrics elsewhere in your report suite.

The exact set of available fields should be confirmed against your report suite's variable configuration after the connector is enabled.

### Responsibilities

The setup and configuration of the inbound connector comesw with responsibilities for both [Adobe](#adobe-managed-responsibilities) and [you as the customer](#customer-owned-responsibilities).

#### Adobe-managed responsibilities

1. Detects and confirms CDN log forwarding for each onboarded Brand Visibility site.
2. Makes the reserved variables available for provisioning once BYOCDN log forwarding is confirmed.
3. Runs the 90-day backfill and ongoing hourly sync once the connector is enabled for a report suite.

#### Customer-owned responsibilities

1. Completing Brand Visibility onboarding and BYOCDN log forwarding for each site.
2. Confirming data is visible in the Brand Visibility Agentic Traffic dashboard before enabling the connector.
3. Choosing the report suite each Brand Visibility site connects to (one site per report suite).
4. Enabling the connector through Report Suite Manager.
5. Building reports, segments, or Data Views (where applicable) that use the reserved variables listed in [How it works](#how-it-works).

### Before you start

Confirm the following before enabling the connector:

- You have completed Adobe Brand Visibility onboarding for the site you want to connect.
- BYOCDN log forwarding is set up and confirmed for that site (see [prequisites](#inbound-integration)).
- Data is showing in your Adobe Brand Visibility Agentic Traffic dashboard for that site.
- You know which report suite you want to connect the site to.

Each Adobe Brand Visibility site connects to exactly one report suite. If you want to bring in data for more than one Brand Visibility site, connect each site to a separate report suite.


### Enable the connector

The connector is turned on and off from the report suite's **Edit Settings** menu.

To open the Adobe Brand Visibility settings for your report suite:

1. Sign in to Adobe Analytics.
1. Go to **[!UICONTROL Admin]** > **[!UICONTROL Report Suites]**.
1. Select the report suite you want to connect.
1. Select **[!UICONTROL Edit Settings]**.
1. From the context menu, select **[!UICONTROL Adobe Brand Visibility]**.

To provision the connector:

1. Select **Provision Adobe Brand Visibility Data Connector**.
1. Review the dimensions and metric that will be added to this report suite (listed in [How it works](#how-it-works)).
1. Under **Select Adobe Brand Visibility Site**, choose the site to connect to this report suite. Once connected, the site's summary data syncs to this report suite every hour.
1. Select **Enable**.

   Once enabled, these variables cannot be removed from this report suite. Enabling the connector starts a 90-day backfill, importing the past 90 days of Adobe Brand Visibility data into this report suite.

   Before you enable the connector, confirm you have completed the steps described in [Before you start](#before-you-start), This includes the verification that data is already shows up in your Adobe Brand Visibility Agentic Traffic dashboard.

After you have enabled the connector, allow time for the initial backfill and the first hourly sync to complete. Then confirm the reserved variables mentioned in [How it works](#how-it-works) are populated in your report suite. see Section 8, Step 3).

### Disable the connector

>[!WARNING]
>
>Disabling the connector is **non reversible**. Disabling stops the hourly sync and deletes historical Adobe Brand Visibility data for this report suite.

To disable the connector:

1. Go to **Admin → Report Suites → Edit Settings → Adobe Brand Visibility**.
1. Select **Deprovision Adobe Brand Visibility Data Connector**.
1. Confirm the Adobe Brand Visibility site listed is the one you intend to disconnect.
1. Select **Disable**.
1. Acknowledge the warning to confirm.

If you only want to pause reporting temporarily, do not disable the connector. Contact your Adobe account team to discuss options to pause repoirting before disabling.

### Setup completion criteria

The inbound integration is ready for reporting when all of the following are confirmed:

* CDN logs are forwarded to and received by Adobe Brand Visibility for the site.
* Data is visible in the Adobe Brand Visibility Agentic Traffic dashboard for the site.
* The connector has been enabled for the intended report suite through Report Suite Manager.
* The initial backfill and at least one hourly sync have completed.
* The reserved variables in Section 4 return expected values in reporting.

### Verification procedure

The verification procedure consists of the following steps:

1. Confirm Brand Visibility site and CDN-log readiness: 

   * Confirm the exact site or domain you plan to connect.
   * Confirm CDN logs are forwarding for that site and that Brand Visibility has confirmed receipt.
   * Confirm data is visible in the Agentic Traffic dashboard for that site.

1. Confirm the connector is enabled:

   1. Go to **Admin → Report Suites → Edit Settings → Adobe Brand Visibility** for the target report suite.
   1. Confirm the page shows the connector as enabled and lists the connected Brand Visibility site.

1. Confirm data in reporting:

   1. Open Analysis Workspace (or your standard reporting workflow) against the connected report suite.
   1. Build a table or visualization using the **Requests** metric broken down by **Bot Type**.
   1. Confirm request volume appears for a recent date range.
   1. Confirm the **URL**, **User Agent**, **Status**, and **Referer** dimensions return expected values.

   The exact time required for data to appear depends on the backfill and sync schedule described in [Enable the connector](#enable-the-connector).



### Troubleshooting

See the following issues and how to troubleshoot these issues.

| Issue | Troubleshoot |
|---|---|
| The connector will not enable, or the site list is empty. | Check whether:<ul><li>Adobe Brand Visibility onboarding is complete for the site.</li><li>BYOCDN log forwarding is configured and confirmed for the site.</li><li>You are working in the correct report suite.</li></ul> |
| The connector is enabled but no data appears. | Check whether: <ul><li>Data is visible in the Agentic Traffic dashboard for the connected site (if not, the issue is upstream of Analytics).</li><li>Enough time has passed for the initial 90-day backfill and at least one hourly sync.</li><li>- The selected date range in your report includes a period after the connector was enabled.</li></ul> |
| Data appears incomplete or unexpected. | Check whether: <ul><li>The report suite is not also expected to receive data for a different Brand Visibility site (each report suite connects to exactly one site).</li><li>You are reading the **Requests** metric rather than counting rows or hits elsewhere in the report suite.</li><li>The dimensions you are viewing match the list in Section 4; unrelated evars or events in the same report suite are not part of this integration.</li></ul> |

>[!MORELIKETHIS]
>
>[Brand Visibility /LLMO integration reference](https://experienceleague.adobe.com/en/docs/analytics-platform/using/integrations/bv)
>[BYOCDN Log Forwarding reference](https://experienceleague.adobe.com/en/docs/brand-visibility/using/log-forwarding/log-forwarding-overview)

## Drafting notes for Docs (not for publication)

This section is for internal review and should be removed before publishing.

- **Source of truth used:** field names, reserved variable list, and the Report Suite Manager workflow are sourced from [AN-468884](https://jira.corp.adobe.com/browse/AN-468884) (David Wardell, status New as of 2026-08-28), which is more current and more specific than the original documentation request [AN-449989](https://jira.corp.adobe.com/browse/AN-449989) (Rob In der Maur, status New). Page copy for the Provision/Deprovision screens incorporates the wording refinements from the 2026-08-28 internal review (`2026-08-28-an468884-abv-report-suite-ui-review.md`), which replaced the raw ticket's "ABV" abbreviation with "Adobe Brand Visibility" in customer-facing text.
- **Field-set discrepancy to reconcile before publishing:** AN-449989's original dimension list was Host, URL / Page Path, CDN Provider, User Agent, and LLM Bot Type, with a single Agentic Request Count metric. AN-468884's actual reserved-variable list is URL, Bot Type, User Agent, Status, and Referer, with a single Requests event. Host and CDN Provider are not present as separate reserved variables in AN-468884; Status is new. This draft follows AN-468884 as authoritative per the eng ticket, but the two should be reconciled with Aaron Kern / David Wardell before this is finalized, since the field names customers see may not match what account teams have described using the older AN-449989 language.
- **Not yet confirmed, do not state as fact in the published version:**
  - Exact GA date. AN-431416 carries FixVersion H2 2026 (2026-11-30 release window) and is in Execute status as of 2026-09-01; AN-468884 (the reserved-variable implementation) and AN-449989 (this doc) are both still New. Do not publish until eng ships.
  - Whether allocation type / expiration type are fully suppressed on the reserved evars in production. The 2026-08-28 review flagged that a test report suite currently shows these evars with Allocation set to "Most Recent (Last)," which may be a default that needs to be cleared rather than confirmed final behavior.
  - The LLMO API endpoint for listing ABV sites by IMS org (populates the Site Selection dropdown) and the deprovision/disable API were both still pending from Joe Bass as of the 2026-08-26 ticket comment.
  - The exact CJA field-count comparison. AN-449989's original ticket claims CJA has "9 additional dimensions" and "5 additional metrics," but several of those (LLM Session Bucket, LLM Unique Session Count, LLM Request Duplication Count) were not confirmed to exist in the delivered `cdn-requests-summary` field group as of the 2026-06-18 review. This draft intentionally avoids citing specific counts in the CJA comparison for that reason.
  - Sync cadence for this AA path is stated here as hourly, matching AN-468884's ticket language ("run hourly syncs" / "hourly sync process"). This has not been independently validated against production AA Data Sources behavior the way the CJA cadence was.


## Outbound integration

This guide covers only the inbound Brand Visibility integration, which adds bot and automated-agent traffic data to an Analytics report suite. The published integration documentation also describes an outbound direction, in which Analytics performance data is made available to Brand Visibility inside the Brand Visibility product. That direction is outside the scope of this guide. See the [Brand Visibility documention](https://experienceleague.adobe.com/en/docs/brand-visibility/using/resources/adobe-analytics-integration) for more information on the outbound integration.