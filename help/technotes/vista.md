---
title: VISTA rules in Adobe Analytics
description: Learn more about VISTA rules and their capabilities.
exl-id: fab2acc3-b037-48f9-bb20-625ccb75b4cc
---
# VISTA rules in Adobe Analytics

VISTA rules are an alternate form of custom data modification that you can apply between data collection and processing. See [Processing order](processing-order.md) for more information around the exact stage in the data pipeline that VISTA rules apply. VISTA rules only impact current data as it is collected; it does not alter existing data.

Some common use cases of VISTA rules include:

* Copy an Analytics hit from one report suite to another, optionally altering data to the copied report suite
* Custom IP exclusion that exceeds the use cases offered by [Exclude by IP](/help/admin/admin/exclude-ip.md)
* Conditionally or globally modify any variable value
* Duplicate variable values to other variables
* Upload files to an Adobe FTP site that can impact variable values

Many use cases to VISTA rules are already offered by [Processing rules](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/c-processing-rules/processing-rules.md), [Bot rules](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/bot-removal/bot-rules.md), [Virtual report suites](/help/components/vrs/vrs-about.md), or simply updating your Adobe Analytics implementation. Adobe recommends VISTA rules only as a last resort.

>[!IMPORTANT]
>
>VISTA rules require a paid agreement between your organization and Adobe Professional Services. Contact your Adobe Account Team if you want to create or update a VISTA rule.

## Create a VISTA rule

You must work with Adobe Professional Services in order to create a VISTA rule. Contact your Adobe Account Team if you want to create a VISTA rule.

## See existing VISTA rules

Adobe does not offer a UI to view existing VISTA rules. Contact your Adobe Account Team or Customer Care with the desired report suite to retrieve a list of existing VISTA rules.
