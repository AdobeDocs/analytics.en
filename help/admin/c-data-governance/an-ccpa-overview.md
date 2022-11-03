---
description: This document describes what you need to do in Adobe Analytics to support your data subjects' CCPA access and delete rights.
title: Adobe Analytics and CCPA
feature: Data Governance
exl-id: 1f37e72b-99e4-4833-a506-98c8ec415757
---
# Adobe Analytics and CCPA

This document describes what you need to do in Adobe Analytics to support your data subjects' CCPA access and delete rights.

## Adobe Overview

>[!IMPORTANT]
>
>The contents of this document are not legal advice and are not meant to substitute for legal advice. Please consult your company's legal department for advice concerning CCPA.

On January 1, 2020, the California Consumer Privacy Act (CCPA) goes into effect. For more information about Adobe's response and what this means for you as an Adobe customer, see [Adobe's Privacy Center.](https://www.adobe.com/privacy.html)

When Adobe is providing software and services to an enterprise, Adobe is acting as a data processor for any personal data it receives and stores on behalf of our customers, as part of providing the services. As a data processor, Adobe processes personal data in accordance with your company's permission and instructions (for example, as set out in your agreement with Adobe).

As the data controller, you determine the personal data that Adobe processes and stores on your behalf. If you use Adobe Experience Cloud solutions, Adobe might host personal data for you depending on the solutions you use and the information you choose to send to your Adobe Experience Cloud account. For a list of examples, see [Adobe Experience Cloud privacy.](https://www.adobe.com/privacy/marketing-cloud.html#collect)

## How Adobe Handles CCPA Data

The Adobe Cloud Platform (ACP) provides an integrated solution that connects your brand's data governance infrastructure with the Adobe tools it uses to create and manage consumer experiences. The data governance features of the Adobe Cloud Platform enable a direct linkage of data governance policy to data usage.

Familiarize yourself with [how Adobe Analytics handles GDPR](https://www.adobe.com/data-analytics-cloud/analytics/general-data-protection-regulation.html) which discusses steps for privacy readiness and how to integrate with the Adobe Experience Cloud Privacy Service API.

## CCPA Readiness and your Adobe Analytics Data

Adobe realizes that you are most familiar with the custom data in your report suites and we are giving you the opportunity to define your data governance settings and preferences.
To that end, Adobe Analytics provides a Data Governance user interface that lets you, as the data controller, set [privacy labels](/help/admin/c-data-governance/gdpr-labels.md#data-governance-labels) on your Analytics report suites and all the dimensions and metrics in those report suites. You can identify the columns in your data set that contain directly identifiable data or indirectly identifiable data so that you can submit your access and delete requests to address that data. For each request, the labels defined in the Analytics Data Governance user interface will be honored for the specific identifier that corresponds to that request.

See [Label Report Suite Data](/help/admin/c-data-governance/gdpr-setup-reportsuite.md) for more information on how to set the labels.

## Prerequisites

* Familiarize yourself with [GDPR terminology.](/help/admin/c-data-governance/gdpr-terminology.md)
* Link your login company to an Experience Cloud organization, if it isn't already. Contact Adobe Customer Care and refer to [Organizations and account linking.](https://experienceleague.adobe.com/docs/core-services/interface/manage-users-and-products/organizations.html)
* Set a data retention policy for each report suite so that CCPA Delete and Access requests can be honored.

   Adobe Analytics cannot assist you with processing requests to the Privacy Services API, i.e., processing access or deletion requests you receive from your end users, if the data retention period has not been set in Adobe Analytics. Please contact your Customer Success Manager in order to set your data retention period.

* Check your permissions: to use the Data Governance Management interface in Adobe Analytics, you must be an Adobe Analytics Administrator.
* Consider implementing the [Consent Management Variables](/help/admin/admin/privacy-reporting.md) to track consent status at a hit level.
