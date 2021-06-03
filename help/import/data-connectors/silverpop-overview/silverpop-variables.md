---
description: The Data Connectors integration for Silverpop uses Analytics variables to track various Silverpop metrics.
title: Analytics Integration Variables
uuid: 3aef3caf-e24e-4fe7-b4d7-50ca0f6703b5
exl-id: 0b8b31f5-65a8-41e0-97d1-d75fb1b91f62
---
# Analytics Integration Variables{#analytics-integration-variables}

The Data Connectors integration for Silverpop uses Analytics variables to track various Silverpop metrics.

After identifying the Event and eVars to use with the Silverpop integration, use the Adobe Analytics Admin Console to enable them (see [Report Suites](https://experienceleague.adobe.com/docs/analytics/admin/manage-report-suites/report-suites-admin.html)).

The following table describes the Analytics variables needed for the Silverpop integration.

## Required Variables {#section-3ca8dc46bab0436cba0c9ef827c8356a}

|  Variable Type  | Name  | Population Method  | Description  |
|---|---|---|---|
|  event (numeric)  | Bounces  | Automatically imported from Silverpop.  | The Bounces event lets you see the number of email messages that were not delivered to recipients due to a delivery problem.  |
|  event (numeric)  | Clicks  | Automatically imported from Silverpop.  | The Clicked event lets you see the number of visitors who clicked the email message.  |
|  event (numeric)  | Opens  | Automatically imported from Silverpop.  | The Opened event lets you see the number of visitors who opened the email message.  |
|  event (numeric)  | Sends  | Automatically imported from Silverpop.  | The Sends event lets you see the number of email messages that were sent.  |
|  event (numeric)  | Unsubscribes  | Automatically imported from Silverpop.  | The Unsubscribed event lets you see the number of visitors who opened the email message but then clicked the Unsubscribe link to opt-out of future email messages from your organization.  |
|  eVar  | Silverpop ID/Visitor ID  | Collected from query parameters in email links through the automated collection method or a JavaScript plug-in.  | Unique Visitor ID  |
|  eVar or s.campaign  | Mailing ID  | Collected from query parameters in email links through the automated collection method or a JavaScript plug-in.  | This is often stored in the campaign variable.  |

## Optional Variables {#section-5f0a32b0a2084c87a64b5f90c0d0fb53}

|  Variable Type  | Name  | Population Method  | Description  |
|---|---|---|---|
|  event (counter)  | File Downloaded  | Manually collected through Analytics tags.  | This event is used to identify users who downloaded a file on the site.  |
|  event (counter)  | Form Started  | Manually collected through Analytics tags.  | Form Started is used to identify users who begin a form, but do not complete it.  |
|  event (counter)  | Form Completed  | Manually collected through Analytics tags.  | Form Completed is used to identify visitors who begin a form and do not complete it.  |
|  eVar  | Email Address  | Manually collected through Analytics tags.  | Email Address is for manually collecting the email address on sign-up, log-in, or other pages that the email address is collected on. This variable is used to remarket to users who have opted-in to receive email, but may not have already clicked through an email in the past.  |
|  eVar  | Downloaded File  | Manually collected through Analytics tags.  | Downloaded File identifies which file a visitor downloaded.  |
|  eVar  | Form Name  | Manually collected through Analytics tags.  | Form Name identifies which form a visitor abandoned.  |
