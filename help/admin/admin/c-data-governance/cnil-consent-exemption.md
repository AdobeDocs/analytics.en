---
description: Learn about the guidelines and recommendations for users' consent to store or read non-essential cookies on devices or browsers.
title: What are the CNIL guidelines for user's consent and cookies
feature: Data Governance
exl-id: 04179e58-dbba-45e2-ba57-7fe5fdedc483
---
# CNIL Consent Exemption

On October 1, 2020, the French Data Protection Authority (the "CNIL") published a revised version of its cookie guidelines (the "Guidelines") and its final recommendations on obtaining users' consent to store or read non-essential cookies and similar technologies on users' devices or browsers (the "Recommendations").

The Guidelines provide a limited exemption to the consent requirement ("Consent Exemption"). The Consent Exemption applies to analytics cookies whose purpose is limited to measuring the audience of the site or app only on behalf of the web publisher. The Guidelines provide that for the Consent Exemption to apply, the following conditions must be implemented:

* 25-month data retention max.  You can review your current data retention settings under [!UICONTROL Analytics] > [!UICONTROL Admin] > [!UICONTROL Data Governance].  [Data Retention](https://experienceleague.adobe.com/docs/analytics/technotes/data-retention.html)
* Disable third party cookies in ECID. [disableThirdPartyCalls](https://experienceleague.adobe.com/docs/id-service/using/id-service-api/configurations/disablethirdpartycalls.html#id-service-api), [disableThirdPartyCookies](https://experienceleague.adobe.com/docs/id-service/using/id-service-api/configurations/disable-cookies.html#id-service-api), and [disableIdSyncs](https://experienceleague.adobe.com/docs/id-service/using/id-service-api/configurations/disableidsync.html#id-service-api)
* 13-month cookie limit.  You  can override your analytics cookie expiration using the `cookieLifetime` variable. Experience Cloud cookies including Analytics and ECID extend the cookie expiration date with each visit.  To set a static, non-rolling cookie expiration, you can either: (1) write custom code to set a date on which to delete the cookie, or (2) use your CMP to control the date of the cookie reset.   [cookieLifetime](https://experienceleague.adobe.com/docs/analytics/implementation/vars/config-vars/cookielifetime.html) and [Experience Cloud Cookies](https://experienceleague.adobe.com/docs/core-services/interface/ec-cookies/cookies-privacy.html#ec-cookies)
* Limited scope. The scope of the cookie must be limited to a single site or application. [Browser Cookies](https://experienceleague.adobe.com/docs/analytics/technotes/cookies/cookies.html#third-party-cookie-limitations)
* Anonymization. Anonymize the last octet of the IP Address. [General Account Settings](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/general-acct-settings-admin.md)
* Hide visitor ID from reporting.  The visitor IDs are not visible in Adobe Workspace and Adobe Reports and Analytics by default.  Visitor IDs are available in Data Feeds and Data Warehouse.  Access to Data Feeds and Data Warehouse can be limited by [Access Permissions in Admin Console](https://experienceleague.adobe.com/docs/core-services/interface/administration/admin-getting-started.html) and [Data Feed Column Reference](https://experienceleague.adobe.com/docs/analytics/export/analytics-data-feed/data-feed-contents/datafeeds-reference.html#columns%2C-descriptions%2C-and-data-types)
* Geolocation parameters. Geolocation can be no more precise than postal code level. [Zip Option](https://experienceleague.adobe.com/docs/analytics/implementation/vars/page-vars/zip.html?lang=en) and [General Account Settings](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/general-acct-settings-admin.html)
* Set opt-in options.  The opt-in service lets you set visitor protocols to determine if you can set a cookie on the user's device or browser when visiting your site. [Opt-In Service](https://experienceleague.adobe.com/docs/id-service/using/implementation/opt-in-service/optin-overview.html)
* Prevent data sharing.  To preclude data sharing to Adobe Audience Manager, use the `opt.dmp` context variable for [Privacy Reporting](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/privacy-reporting.md) to block hits from being shared.
* Access and delete ability. Utilize the Privacy Service for access and delete requests. [Analytics & Privacy Service](https://experienceleague.adobe.com/docs/analytics/admin/data-governance/an-gdpr-overview.html)

## Additional Considerations for Data Collection

The following additional considerations apply:

* Adobe Analytics operates data processing centers in the United States, United Kingdom and Singapore in order to provide flexibility to all customers to collect, process, and store their data regionally. When configuring the initial set-up of Adobe Analytics, customers may select their desired data processing center location. Customers' data is ultimately stored within their selected region for the core Analytics product.
* Consider collecting the opt-in status in an Analytics variable in order to separate opted-in data from opted-out data for segmentation, virtual report suites, or to route to separate end-points.
* No measurement outside the site or app without prior consent, for example no off-site campaigns, email campaigns, or iFrames.
* Collection of personal information in variables is not permitted without consent. [Control Experience Cloud Activities Based on User Consent](https://experienceleague.adobe.com/docs/id-service/using/implementation/opt-in-service/use-opt-in-to-control-experience-cloud-activities-based-on-user-consent.html#implementing-opt-in-on-the-page)
* Data is only to be used to produce anonymous statistics, without combination with other data.
* Data is not used to cross-reference actions.
* GPS geolocation data is not collected.
* When end-user consent has been given, the above settings can be modified and restrictions relaxed.

>[!IMPORTANT]
>
>This document is not intended as legal or regulatory advice and does not constitute any warranty or contractual commitment on the part of Adobe. We encourage customers to seek independent legal advice on customer's legal and regulatory obligations on issues related to this subject matter. 


For more information, see the [CNIL Cookie Exemption](https://www.cnil.fr/en/sheet-ndeg16-use-analytics-your-websites-and-applications) website.

