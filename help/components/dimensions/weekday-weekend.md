---
title: Weekday/Weekend
description: Determines if the hit happened during a weekday or a weekend.
---

# Weekday/Weekend

The 'Weekday/Weekend' dimension provides insight on if the hit happened during a weekday (Monday - Friday) or weekend (Saturday - Sunday). The time of the hit is based on the [report suite's time zone](/help/admin/admin/general-acct-settings-admin.md).

## Populate this dimension with data

This dimension works out of the box for all implementations. If a report suite contains data, this dimension works.

## Dimension values

This dimension always contains exactly two dimension values: `"Weekday"` and `"Weekend"`. The dimension value `"Weekday"` applies to all hits Monday through Friday, while the dimension value `"Weekend"` applies to all hits on Saturday and Sunday.
