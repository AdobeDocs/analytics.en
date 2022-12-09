---
title: Consent Management Opt-Out
description: See which privacy settings that a visitor opted out of.
exl-id: 2bf4d22c-5b24-47fb-b489-49388fcca5b1
---
# Consent Management Opt-Out

The 'Consent Management Opt-Out' dimension displays which privacy settings that a visitor has explicitly opted out of. You can use this dimension to filter data based on privacy settings, or see the most common privacy opt-out reasons.

## Populate this dimension with data

This dimension collects data from the following [Context data variables](/help/implement/vars/page-vars/contextdata.md):

* `contextData.['cm.ssf']` when set to `1`. If `cm.ssf` equals `0` or is blank, this variable does nothing.
* `contextData.['opt.dmp']` when set to `N`. If `opt.dmp` equals `Y`, the [Consent Management Opt-In](cm-opt-in.md) dimension is populated instead.
* `contextData.['opt.sell']` when set to `N`. If `opt.sell` equals `Y`, the [Consent Management Opt-In](cm-opt-in.md) dimension is populated instead.

Your organization determines the logic to implement these context data variables. They do not persist beyond the hit that they are set on, so you must set each context data variable on each page.

## Dimension items

Dimension items include the following three values:

* **`SSF`**: The visitor opted out of [Server-side forwarding](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/c-server-side-forwarding/ssf.md). This dimension item is present when the context data variable `cm.ssf` equals `1`. See [Data privacy overview](https://experienceleague.adobe.com/docs/audience-manager/user-guide/overview/data-privacy/data-privacy.html) in the Audience Manager user guide for more information. The hit is not forwarded to Adobe Audience Manager.
* **`DMP`**: The visitor opted out of sharing to data management platforms. This dimension item is present when the context data variable `opt.dmp` equals `N`. Similar to `SSF`, the hit is not forwarded to Adobe Audience Manager.
* **`SELL`**: The visitor opted out of the sharing or selling of the data to third parties. This dimension is present when the context data variable `opt.sell` equals `N`.
