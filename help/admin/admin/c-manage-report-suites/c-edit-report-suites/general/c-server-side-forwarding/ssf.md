---
description: Server-side forwarding is designed for customers who want to share data from Analytics to other Experience Cloud Solutions in real time. When enabled, server-side forwarding also allows Analytics to push data to other Experience Cloud solutions and for those solutions to push data to Analytics during the data collection process.
solution: Analytics
title: Server-side forwarding overview
feature: Server-Side Forwarding
exl-id: e3cd72d2-9588-4770-a7c2-64b13a1e9519
---
# Server-side forwarding overview

Server-side forwarding is designed for customers who want to share data from Analytics to other Experience Cloud Solutions in real time. When enabled, server-side forwarding also allows Analytics to push data to other Experience Cloud solutions and for those solutions to push data to Analytics during the data collection process.

Server-side forwarding improves upon data collection because it:

* Reduces calls from the page. With server-side forwarding, [!DNL Audience Manager] customers no longer need to use DIL for data collection because it is being forwarded from Analytics. Removing DIL means eliminating an `"/event"` call. Fewer calls helps improve page load times, which makes for a better customer experience on your site.
* Lets you take advantage of data sharing among Experience Cloud solutions.
* Conforms with our best practices for Audience Manager code implementation and deployment.

>[!TIP]
>
>Current Audience Manager customers who use Analytics should migrate to server-side forwarding. New Adobe Analytics and Audience Manager customers should implement server-side forwarding (instead of DIL) as the default data collection and transfer method.

>[!IMPORTANT]
>Prompted by the EU cookie compliance regulation, data controllers (Analytics customers) now have the option to restrict pre-consent data to Adobe Analytics, and prevent it from being server-side forwarded to Adobe Audience Manager (AAM). A new implementation context variable lets you flag hits where consent has not been received. The variable, when set, prevents these hits from being sent to AAM until consent has been received. For more information, see [GDPR_ePrivacy compliance and server-side forwarding](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/c-server-side-forwarding/ssf-gdpr.md).

To understand where your organization is in terms of implementing server-side forwarding, go through these validation steps: 

## ![step1_icon.png image](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/c-server-side-forwarding/assets/step1_icon.png) Verify ECID service implementation

Verify whether Experience Cloud ID (ECID) service is implemented, by inspecting the [Analytics tracking request](https://experienceleague.adobe.com/docs/id-service/using/implementation/test-verify.html).

On the Request tab, verify that a ECID value is being set. This tells you that Identity Service is implemented correctly, which is a pre-requisite for server-side forwarding.

* If you see an ECID value, continue to step 2.
* If you do not see an ECID value, [implement Identity Service](https://experienceleague.adobe.com/docs/id-service/using/implementation/implementation-guides.html) before proceeding to step 2.

## ![step2_icon.png image](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/c-server-side-forwarding/assets/step2_icon.png) Verify server-side forwarding implementation version

Verify whether you already have a version of server-side forwarding implemented, by [inspecting the Analytics tracking request](/help/admin/admin/c-server-side-forwarding/ssf-verify.md).

In the "Response" tab, check that the response contains Audience Manager data. If you see:

* A **JSON response from Audience Manager that includes items such as "postbacks" or "dcs_region"**: you have some form of server-side forwarding already enabled. Continue to step 3.
* The **"status":"SUCCESS"**: you have the Audience Management Module implemented, but do not have server side forwarding properly configured. Continue to step 3.
* A **2 x 2 image**: you do not have server-side forwarding or the Audience Management Module implemented. To correct this:

  * **AAM Customers with DIL**: coordinate the following 2 items in close conjunction:

    1. Remove the DIL code and install the [Audience Management Module](https://experienceleague.adobe.com/docs/audience-manager/user-guide/implementation-integration-guides/integration-other-solutions/audience-management-module.html) page code.
    1. Enable server-side forwarding in the Analytics Admin UI as described in step 3. Enabling this setting before removing DIL code will duplicate data and create additional billed server calls to Audience Manager.

  * **New AAM customers** - install the [Audience Management Module](https://experienceleague.adobe.com/docs/audience-manager/user-guide/implementation-integration-guides/integration-other-solutions/audience-management-module.html) page code and continue to step 3. Data will not be sent to Audience Manager until server-side forwarding is turned on in step 3.

## ![step3_icon.png image](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/c-server-side-forwarding/assets/step3_icon.png) Verify server-side forwarding implementation of report suite

Verify whether you have server-side forwarding implemented at the report-suite level, rather than the legacy tracking server approach.

Server-side forwarding at the report-suite level is recommended over the legacy tracking server approach because you can control at a finer level what data gets shared from Analytics. It is also a pre-requisite for this Audience Analytics integration.

Go to **Analytics** > **Admin** > **Report Suites** > (select **report suites**) > **Edit Settings** > **General** > **Server Side Forwarding**. If the checkbox is:

* **Inactive** (You are unable to make a selection or the menu does not exist): you do not have the selected report suites mapped to an organization ID. Contact Customer Care to make sure that the report suite is correctly mapped.
* **Disabled**: You do not have the new server-side forwarding turned on. Read the content on the page and then proceed with enabling the feature.
* **Enabled**: You are provisioned for new server-side forwarding. You are also able to set up this Audience Analytics integration.

>[!NOTE]
>
>Data will not appear in other Experience Cloud solutions, such as [Audience Manager](https://experienceleague.adobe.com/docs/audience-manager/user-guide/aam-home.html) or [Audiences](https://experienceleague.adobe.com/docs/core-services/interface/audiences/audience-library.html) until all 3 steps are complete. Once enabled, it will take several hours for these settings to take effect.
