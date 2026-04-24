---
description: Frequently asked questions around Advertising Analytics.
title: Frequently Asked Questions for advertising analytics
feature: Advertising Analytics
exl-id: 664a5641-1c79-439f-a9fb-2ff134574412
TQID: https://experienceleague.adobe.com/HC9F-en-nLFRkxsaY6Szdtb3jR5NgdpsbjSAX6kTBlQ
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
    internal-label: Reports
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
  - id: eb9732ab-8232-4b21-bc4c-89de86dbe4d7
    internal-label: Integrations
  - id: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
    internal-label: API
subfeature_v2:
  - id: a9364d69-0c51-44bf-8b5f-6d99c04493b8
    internal-label: Advertising Analytics
  - id: c80b99d6-98b9-4aeb-b5c4-933ef2ef705c
    internal-label: Marketing Channels
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: c2296997-5d79-4905-b32e-99b5aa892429
    internal-label: Search optimization
  - id: cdd65e7e-8839-44a2-bc21-0e03623b5dd1
    internal-label: Optimization
---
# Frequently Asked Questions

## Access/Entitlements {#access}

+++ Do I need to be an Adobe Advertising customer to access this functionality?

No, this functionality is available for non-Advertising customers. Adobe Advertising customers can leverage the existing Analytics + Advertising integration.

+++

+++ Which Adobe Analytics SKUs entitle you to the use of Advertising Analytics? 

Advertising Analytics is available for Adobe Analytics 

* [Select](https://www.adobe.com/data-analytics-cloud/analytics/select.html)

* [Prime](https://www.adobe.com/data-analytics-cloud/analytics/prime.html)

* [Ultimate](https://www.adobe.com/data-analytics-cloud/analytics/ultimate.html) 

+++

+++ Do I have to pay extra to use Advertising Analytics? 

No, outside of proper SKU provisioning Advertising Analytics does not incur extra cost.

+++

+++ Does Advertising Analytics count against my server call usage

No, Advertising Analytics uses a special data source type which does not incur server call costs.

+++

+++ If I already use Adobe Advertising, can I still use the Advertising Analytics functionality?

Any compatible search engine account will pass into Advertising Analytics and will be displayed as read-only. All edits or updates should be handled in Advertising. 

+++

+++ I own the correct SKU, but I cannot access Advertising Analytics, why is that? 

Advertising Analytics is available only for Adobe Analytics administrators; however, admins may grant access to non-admins. Please contact your administrator for access rights. 

+++

## Using Advertising Analytics {#using}
 
+++ Which search engine accounts are included in Advertising Analytics?

Search engine accounts include Google Ads and Microsoft Advertising. 

+++

+++ Where do I go to access Advertising Analytics?

After logging in to Adobe Analytics, navigate to the [!UICONTROL Admin]. Then select [!UICONTROL Advertising Analytics] to add your search engine accounts.

+++

+++ How is the data collected and passed into Analytics? 

Advertising Analytics utilizes a series of custom APIs to pass data from search engines through Adobe Advertising into Adobe Analytics.

+++

+++ What search data do I get with this integration? 

You get:

* Impressions
* Clicks
* Costs
* Quality Score
* Average Position directly from the search engines 
* AMO ID Instances (Click Instances)

+++

+++ Can I break my Advertising Analytics data down by other Analytics data (metrics/dimensions)? 

No, the raw search data will come in as an independent data set. However, there is an Instances version of the click data that can be broken down by other Analytics data.

+++

+++ What is the definition of the various status indicators for my accounts (Pending, Active, Paused, etc.)? Each of these status indicators identifies the lifecycle stage of each search engine account. 

* [!UICONTROL Pending]
* [!UICONTROL Paused] means the account was formerly set up but has been put in an inactive state.
* [!UICONTROL Active] means the account has been fully set up and is pulling search data.

+++

+++ I am trying to map my Advertising Analytics accounts to a specific report suite, but it is not available in the Report Suite modal. Why? 

Before you can assign a report suite to an Advertising Analytics account, the desired report suite needs to be [provisioned for Advertising Analytics reporting](/help/integrate/c-advertising-analytics/c-adanalytics-workflow/aa-provision-rs.md) 
This is done through a separate Admin page that is accessible from: Admin > Report Suites > `[select report suite]` > Edit Settings > Advertising Analytics Configuration.

+++

+++ Is it possible to assign a virtual report suite to an Advertising Analytics account? 

Virtual report suites do not collect data, so you cannot directly map an Advertising Analytics account to a Virtual report suite. However, you can map the Advertising Analytics account to the parent Report Suite of the Virtual report suite that you want to see data in. The Search Engine metrics (click/cost/impressions) may not show up in the Virtual report suite unless you include an "or" condition in your segment logic based on the AMO ID (or its classification). Example: Adding "all hits where AMO ID exists" would include the search engine metrics in the segment. 

+++

+++ Are Advertising Analytics metrics reportable in the *Marketing Channels* report? 

No, they are not included in the Marketing Channels report.

+++

+++ When does the search data get pulled into Analytics? 

The search data is pulled from the search engines around 6AM (06:00) in the time zone of your Analytics data center. This is when the AMO data is collected and inserted into the report suite. It is then converted into the report suite time zone as part of inserting the data into Analytics. 

+++

+++ What can be *captured before the click*? Do we bring impressions, cost, average position, etc. even without the click?

The AMO ID will capture the Search engine metrics: Impressions, Cost, Clicks, Average Position, and Average Quality Score. If there are no clicks, but there are impressions, then the impression/position/quality score data will still be sent to Analytics. Typically, if there are no clicks, then there is also no cost.

+++

+++ What level is this data being captured at? *Visitor? Hit?* 

The Search engine metrics are captured at the hit level and connected to the AMO ID (and its classifications). It is summary level data and not connected to visits/visitors. As such, the search engine metrics can only be used in segments that are hit-level scope and are based on the AMO ID (or its classifications). 

The AMO ID is also captured on the landing page in the hit for that page (which connects it to the visit/visitor) and will persist downstream to get credit for other Analytics metrics (until it expires or is overwritten by a new AMO ID). It is fully incorporated into the data set like any other eVar.

+++

+++ Do we only capture google.com or *country versions* (like google.co.uk, google.it, google.fr, or google.de) as well? 

The Ad Platform classification captures these values: "Google Adwords", and "Bing Ads". A common best practice is to include the country code as part of the naming of campaigns. You can then filter down or segment (e.g. if all campaigns start with countrycode_, then creating a segment where Campaigns (AMO ID) starts with "UK_" would provide you with only data for the UK). 

+++

+++ The metric "AMO Cost" is the cost paid for each keyword/ad as reported by the search engine. Is this Net cost or Gross cost? 

"AMO cost" is only the cost paid to the search engines. It does not include any agency or search optimization/management platform fees. 

+++

+++ Are there plans to include other advertising channels such as *Display* or *Social*? 

No, currently we do not have plans for these other channels on the roadmap. 

+++
  

## Auto vs. Manual Tracking {#section_7437C4698A6D482EB7ED94A948390119}

+++ When setting up my Advertising account, it states that *Auto Tracking* can lead to unintended consequences. What kinds of consequences may occur? 

Auto mode attempts to append URL parameters to the end of the tracking templates/destination URLs in the correct format. However, it is your responsibility to ensure that the added URL parameters persist correctly to the final landing page. Auto mode can insert key words into the landing URL, and your web server may not support keywords with special characters. 

+++

+++ If I set up Manual or Automatic Tracking initially, can I switch to the other tracking mode later on? What are the implications? 

Yes you can switch tracking modes, but you need to remove the old tracking logic before making the switch. This may result in some downtime of tracking on the day the switch is made (especially if moving from manual to automatic). As such, we recommend not switching unless absolutely necessary.

* Switching from Manual to Automatic: Remove the manual additions to the tracking templates and then switch the toggle in the Advertising Analytics UI from manual to Automatic and save the setting. Note that it may take several hours for the system to populate the automatic tracking codes.

* Switching from Automatic to Manual: Update the toggle from manual to automatic in the Advertising Analytics setup UI and then deploy the manual tracking codes as quickly as possible. While deploying the manual tracking codes, if you see the automatic tracking codes in the Search Engine tracking templates, remove them. 

+++
