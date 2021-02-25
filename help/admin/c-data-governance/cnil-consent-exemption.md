---
description: Learn about the guidelines and recommendations for users' consent to store or read non-essential cookies on devices or browsers.
title: What are the CNIL guidelines for user's consent and cookies
---

# CNIL Consent Exemption

On October 1, 2020, the French Data Protection Authority (the “CNIL”) published a revised version of its cookie guidelines (the “Guidelines”) and its final recommendations on obtaining users’ consent to store or read non-essential cookies and similar technologies on users’ devices or browsers (the “Recommendations”). 

The Guidelines provide a limited exemption to the consent requirement (“Consent Exemption”). The Consent Exemption applies to analytics cookies whose purpose is limited to measuring the audience of the site or app only on behalf of the web publisher. The Guidelines provide that for the Consent Exemption to apply, the following conditions must be implemented:

* 25-month data retention max.  You can review your current data retention settings under Analytics > Admin > Data Governance.  [Data Retention](https://experienceleague.adobe.com/docs/analytics/technotes/data-retention.html)
* 13-month cookie limit.  You can override your analytics cookie expiration using the `cookieLifetime` variable.  [cookieLifetime](https://experienceleague.adobe.com/docs/analytics/implementation/vars/config-vars/cookielifetime.html)
* Limited scope. The scope of the cookie must be limited to a single site or application. [Browser Cookies](https://experienceleague.adobe.com/docs/analytics/technotes/cookies.html?lang=en"\l"third-party-cookie-implementations)
* Anonymization. Anonymize the last octet of the IP Address. [General Account Settings](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/general-acct-settings-admin.html)
* Hide visitor ID from reporting.  The visitor IDs are not visible in Adobe Workspace and Adobe Reports and Analytics by default.  Visitor IDs are available in Data Feeds and Data Warehouse.  Access to Data Feeds and Data Warehouse can be limited by [Access Permissions in Admin Console](https://experienceleague.adobe.com/docs/core-services/interface/manage-users-and-products/admin-getting-started.html?lang=en"\l"task_040673FE3E3E429B9531FBCB8B6A4391)
* Geolocation parameters. Geolocation can be no more precise than postal code level. [Zip Option](https://experienceleague.adobe.com/docs/analytics/implementation/vars/page-vars/zip.html?lang=en"\l"zip-in-adobe-experience-platform-launch) and [General Account Settings](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/general-acct-settings-admin.html?lang=en"\l"admin-tools)
* Set opt-in options.  The Opt-in service lets you set visitor protocols to determine if you can set a cookie on the user’s device or browser when visiting your site. [Opt-In Service](https://experienceleague.adobe.com/docs/id-service/using/implementation/opt-in-service/optin-overview.html)
* Prevent data sharing.  To preclude data sharing to Adobe Audience Manager, use the `opt.dmp` context variable for [Privacy Reporting](https://experienceleague.adobe.com/docs/analytics/admin/data-governance/consent-variables.html?lang=en"\l"variables) to block hits from being shared.
* Access and delete ability. Utilize the Privacy Service for access and delete requests. [Analytics & Privacy Service](https://experienceleague.adobe.com/docs/analytics/admin/data-governance/an-gdpr-overview.html)

## Additional Considerations for Data Collection

The following additional considerations apply:

* No measurement outside the site or app without prior consent, for example no off-site campaigns, email campaigns, or iFrames.
* Collection of personal information in variables is not permitted without consent.
* Data is only to be used to produce anonymous statistics, without combination with other data.
* Data is not used to cross-reference actions.
* GPS geolocation data is not collected.

For more information, see the [CNIL Cookie Exemption](https://www.cnil.fr/en/sheet-ndeg16-use-analytics-your-websites-and-applications) website.
