---
title: Exit link
description: The name of the exit link.
---

# Exit link

The 'Exit link' dimension reports the names of exit links implemented on your site. This dimension is valuable when you want to understand which links are most popular that point to domains outside your site.

## Populate this dimension with data

This dimension collects data from the [`pev2` query string](/help/implement/validate/query-parameters.md) in image requests for hits that also have the `pe` query string with the value of `lnk_e`. If the `pe` query string has a different value in the hit, this dimension does not collect data.

If you want to send data to this dimension using AppMeasurement:

* Populate the [`linkName`](/help/implement/vars/config-vars/linkname.md) variable with the desired value.
* Set the [`linkType`](/help/implement/vars/config-vars/linktype.md) variable to `"e"`.
* Send a [`tl()`](/help/implement/vars/functions/tl-method.md) image request.

## Dimension values

Since this variable is based on a custom string in your implementation, your organization determines what the dimension values are. Adobe recommends that you group links into meaningful categories based on your reporting needs.
