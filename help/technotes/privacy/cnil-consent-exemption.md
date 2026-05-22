---
description: Learn about the guidelines and recommendations for users' consent to store or read non-essential cookies on devices or browsers.
title: What are the CNIL guidelines for user's consent and cookies
feature: Data Governance
role: Admin
exl-id: 04179e58-dbba-45e2-ba57-7fe5fdedc483
TQID: 'https://experienceleague.adobe.com/DNqDZWOm1buhq-vLG3io11v-s-7SAXfb6W3A9VAOtXw'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
    internal-label: Reports
  - id: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
    internal-label: API
  - id: b8734a57-d5fb-44a8-8ee1-65225cecaeae
    internal-label: Data configuration and collection
subfeature_v2:
  - id: b99602d0-836e-4dbb-979f-c0dec53f883c
    internal-label: Privacy
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
    internal-label: Measurement
  - id: c7d04a2c-412a-4c9d-9d7a-4456eaa5adeb
    internal-label: Governance
  - id: d3cdead0-685a-4489-9250-4bb709942f66
    internal-label: Data collection
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
    internal-label: Administration
  - id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
    internal-label: Privacy
---
# CNIL Consent Exemption

On October 1, 2020, the French Data Protection Authority (the "CNIL") published a revised version of its cookie guidelines (the "Guidelines") and its final recommendations on obtaining users' consent to store or read non-essential cookies and similar technologies on users' devices or browsers (the "Recommendations").

The Guidelines provide a limited exemption to the consent requirement ("Consent Exemption"). The Consent Exemption applies to analytics cookies whose purpose is limited to measuring the audience of the site or app only on behalf of the web publisher. The Guidelines provide that for the Consent Exemption to apply, the following conditions must be implemented:

* 25-month data retention max.  You can review your current data retention settings under [!UICONTROL Analytics] > [!UICONTROL Admin] > [!UICONTROL Data Governance].  [Data Retention](/help/technotes/data-retention.md)
* Disable third party cookies in ECID. [disableThirdPartyCalls](https://experienceleague.adobe.com/docs/id-service/using/id-service-api/configurations/disablethirdpartycalls.html#id-service-api), [disableThirdPartyCookies](https://experienceleague.adobe.com/docs/id-service/using/id-service-api/configurations/disable-cookies.html#id-service-api), and [disableIdSyncs](https://experienceleague.adobe.com/docs/id-service/using/id-service-api/configurations/disableidsync.html#id-service-api)
* 13-month cookie limit.  You  can override your analytics cookie expiration using the `cookieLifetime` variable. CX Enterprise cookies including Analytics and ECID extend the cookie expiration date with each visit.  To set a static, non-rolling cookie expiration, you can either: (1) write custom code to set a date on which to delete the cookie, or (2) use your CMP to control the date of the cookie reset.   [cookieLifetime](/help/implement/vars/config-vars/cookielifetime.md) and [CX Enterprise Cookies](https://experienceleague.adobe.com/docs/core-services/interface/ec-cookies/cookies-privacy.html#ec-cookies)
* Limited scope. The scope of the cookie must be limited to a single site or application. [Browser Cookies](/help/technotes/cookies/cookies.md#third-party-cookie-limitations)
* Anonymization. Anonymize the last octet of the IP Address. [General Account Settings](/help/admin/tools/manage-rs/edit-settings/general/general-acct-settings-admin.md)
* Hide visitor ID from reporting.  The visitor IDs are not visible in Adobe Workspace and Adobe Reports and Analytics by default.  Visitor IDs are available in Data Feeds and Data Warehouse.  Access to Data Feeds and Data Warehouse can be limited by [Access Permissions in Admin Console](https://experienceleague.adobe.com/docs/core-services/interface/administration/admin-getting-started.html) and [Data Feed Column Reference](/help/export/analytics-data-feed/c-df-contents/datafeeds-reference.md)
* Geolocation parameters. Geolocation can be no more precise than postal code level. [Zip Option](/help/implement/vars/page-vars/zip.md) and [General Account Settings](/help/admin/tools/manage-rs/edit-settings/general/general-acct-settings-admin.md)
* Set opt-in options.  The opt-in service lets you set visitor protocols to determine if you can set a cookie on the user's device or browser when visiting your site. [Opt-In Service](https://experienceleague.adobe.com/docs/id-service/using/implementation/opt-in-service/optin-overview.html)
* Prevent data sharing.  To preclude data sharing to Adobe Audience Manager, use the `opt.dmp` context variable for [Privacy Reporting](/help/admin/tools/manage-rs/edit-settings/privacy-reporting.md) to block hits from being shared.
* Access and delete ability. Utilize the Privacy Service for access and delete requests. [Analytics & Privacy Service](gdpr.md)

## Additional Considerations for Data Collection

The following additional considerations apply:

* Adobe Analytics operates data processing centers in the United States, United Kingdom and Singapore in order to provide flexibility to all customers to collect, process, and store their data regionally. When configuring the initial set-up of Adobe Analytics, customers may select their desired data processing center location. Customers' data is ultimately stored within their selected region for the core Analytics product.
* Consider collecting the opt-in status in an Analytics variable in order to separate opted-in data from opted-out data for segmentation, virtual report suites, or to route to separate end-points.
* No measurement outside the site or app without prior consent, for example no off-site campaigns, email campaigns, or iFrames.
* Collection of personal information in variables is not permitted without consent. [Control CX Enterprise Activities Based on User Consent](https://experienceleague.adobe.com/docs/id-service/using/implementation/opt-in-service/use-opt-in-to-control-experience-cloud-activities-based-on-user-consent.html#implementing-opt-in-on-the-page)
* Data is only to be used to produce anonymous statistics, without combination with other data.
* Data is not used to cross-reference actions.
* GPS geolocation data is not collected.
* When end-user consent has been given, the above settings can be modified and restrictions relaxed.

>[!IMPORTANT]
>
>This document is not intended as legal or regulatory advice and does not constitute any warranty or contractual commitment on the part of Adobe. We encourage customers to seek independent legal advice on customer's legal and regulatory obligations on issues related to this subject matter. 

For more information, see the [CNIL Cookie Exemption](https://www.cnil.fr/en/sheet-ndeg16-use-analytics-your-websites-and-applications) website.
