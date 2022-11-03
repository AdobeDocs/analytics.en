---
title: Consent Management Opt-In
description: See which privacy settings a visitor opted in to.
---
# Consent Management Opt-In

The 'Consent Management Opt-In' dimension displays which privacy settings that a visitor has opted in to. You can use this dimension to filter data based on privacy settings, or see the most common privacy opt-in reasons.

## Populate this dimension with data

This dimension collects data from the following [Context data variables](/help/implement/vars/page-vars/contextdata.md):

* `contextData.['opt.dmp']` when set to `Y`. If `opt.dmp` equals `N`, the [Consent Management Opt-Out](cm-opt-out.md) dimension is populated instead.
* `contextData.['opt.sell']` when set to `Y`. If `opt.sell` equals `N`, the [Consent Management Opt-Out](cm-opt-out.md) dimension is populated instead.

Your organization determines the logic to implement these context data variables. They do not persist beyond the hit that they are set on, so you must set each context data variable on each page.

## Dimension items

Dimension items include the following two values:

* **`DMP`**: The visitor opted in to sharing to data management platforms. This dimension item is present when the context data variable `opt.dmp` equals `Y`.
* **`SELL`**: The visitor opted in to the sharing or selling of the data to third parties. This dimension is present when the context data variable `opt.sell` equals `Y`.
