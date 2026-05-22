---
description: This document describes what you need to do in Adobe Analytics to support your data subjects' CCPA access and delete rights.
title: Adobe Analytics and CCPA
feature: Data Governance
role: Admin
exl-id: 1f37e72b-99e4-4833-a506-98c8ec415757
TQID: 'https://experienceleague.adobe.com/medgbA9EBG0fE2xttZ7HLKT42-RBr7rlMGGGGrAyoKw'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
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
  - id: c7d04a2c-412a-4c9d-9d7a-4456eaa5adeb
    internal-label: Governance
  - id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
    internal-label: Privacy
---
# Adobe Analytics and CCPA

This document describes what you need to do in Adobe Analytics to support your data subjects' CCPA access and delete rights.

## Adobe Overview

>[!IMPORTANT]
>
>The contents of this document are not legal advice and are not meant to substitute for legal advice. Please consult your company's legal department for advice concerning CCPA.

On January 1, 2020, the California Consumer Privacy Act (CCPA) goes into effect. For more information about Adobe's response and what this means for you as an Adobe customer, see [Adobe's Privacy Center.](https://www.adobe.com/privacy.html)

When Adobe is providing software and services to an enterprise, Adobe is acting as a data processor for any personal data it receives and stores on behalf of our customers, as part of providing the services. As a data processor, Adobe processes personal data in accordance with your company's permission and instructions (for example, as set out in your agreement with Adobe).

As the data controller, you determine the personal data that Adobe processes and stores on your behalf. If you use Adobe CX Enterprise solutions, Adobe might host personal data for you depending on the solutions you use and the information you choose to send to your Adobe CX Enterprise account. For a list of examples, see [Adobe CX Enterprise privacy.](https://www.adobe.com/privacy/marketing-cloud.html#collect)

## How Adobe Handles CCPA Data

Adobe CX Enterprise provides an integrated solution that connects your brand's data governance infrastructure with the Adobe tools it uses to create and manage consumer experiences. The data governance features of Adobe CX Enterprise enable a direct linkage of data governance policy to data usage.

Familiarize yourself with [how Adobe Analytics handles GDPR](https://www.adobe.com/data-analytics-cloud/analytics/general-data-protection-regulation.html) which discusses steps for privacy readiness and how to integrate with the Adobe CX Enterprise Privacy Service API.

## CCPA Readiness and your Adobe Analytics Data

Adobe realizes that you are most familiar with the custom data in your report suites and we are giving you the opportunity to define your data governance settings and preferences.
To that end, Adobe Analytics provides a Data Governance user interface that lets you, as the data controller, set [privacy labels](/help/admin/tools/privacy-labeling/labels.md#data-governance-labels) on your Analytics report suites and all the dimensions and metrics in those report suites. You can identify the columns in your data set that contain directly identifiable data or indirectly identifiable data so that you can submit your access and delete requests to address that data. For each request, the labels defined in the Analytics Data Governance user interface will be honored for the specific identifier that corresponds to that request.

See [Label Report Suite Data](/help/admin/tools/privacy-labeling/labeling-overview.md) for more information on how to set the labels.
