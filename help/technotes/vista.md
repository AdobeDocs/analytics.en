---
title: VISTA rules in Adobe Analytics
description: Learn more about VISTA rules and their capabilities.
exl-id: fab2acc3-b037-48f9-bb20-625ccb75b4cc
feature: Analytics Basics
TQID: https://experienceleague.adobe.com/x3pRtt4sTKGPnD30xXJWIX6OEjaDWHED-S2-0BXCcDg
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: a421fb65-2c82-457a-921c-28c46b697a39
    internal-label: Analytics basics
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: d3cdead0-685a-4489-9250-4bb709942f66
    internal-label: Data collection
---
# VISTA rules in Adobe Analytics

VISTA rules are an alternate form of custom data modification that you can apply between data collection and processing. See [Processing order](processing-order.md) for more information around the exact stage in the data pipeline that VISTA rules apply. VISTA rules only impact current data as it is collected; it does not alter existing data.

Some common use cases of VISTA rules include:

* Copy an Analytics hit from one report suite to another, optionally altering data to the copied report suite
* Custom IP exclusion that exceeds the use cases offered by [Exclude by IP](/help/admin/tools/exclude-ip.md)
* Conditionally or globally modify any variable value
* Duplicate variable values to other variables
* Upload files to an Adobe FTP site that can impact variable values

Many use cases to VISTA rules are already offered by [Processing rules](/help/admin/tools/manage-rs/edit-settings/general/processing-rules/pr-overview.md), [Bot rules](/help/admin/tools/manage-rs/edit-settings/general/bot-removal/bot-rules.md), [Virtual report suites](/help/components/vrs/vrs-about.md), or simply updating your Adobe Analytics implementation. Adobe recommends VISTA rules only as a last resort.

>[!IMPORTANT]
>
>VISTA rules implementation and configuration require a paid agreement between your organization and Adobe Professional Services. Contact your Adobe Account Team if you want to create or update a VISTA rule.
>
>Please note:
>
>* VISTA rule creation includes only the initial implementation. Ongoing maintenance or VISTA rule updates require a separate paid engagement.
>
>* VISTA rules rely on specific conditions in your data. For example, changes to your Adobe Analytics implementation, the types of data or lengths of strings being collected, changes to the tables used for DB VISTA, or other changes to input data patterns could cause a VISTA rule to stop functioning as expected. Adobe recommends reviewing your VISTA rules regularly to determine if updates or removal are needed.

## Create a VISTA rule {#create}

You must work with Adobe Professional Services in order to create a VISTA rule. Contact your Adobe Account Team if you want to create a VISTA rule.

## See existing VISTA rules {#see}

Adobe does not offer a UI to view existing VISTA rules. Contact your Adobe Account Team or Customer Care with the desired report suite to retrieve a list of existing VISTA rules.
