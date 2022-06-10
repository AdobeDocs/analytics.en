---
title: AM/PM
description: Determines if the hit happened during AM or PM hours.
feature: Dimensions
exl-id: 93fcdb9f-2ba3-402c-a389-b02ed8c990d2
---
# AM/PM

The 'AM/PM' dimension provides insight on if the hit happened during AM or PM hours. The time of the hit is based on the [report suite's time zone](/help/admin/admin/general-acct-settings-admin.md).

## Populate this dimension with data

This dimension works out of the box. It does not have any settings to change. Its only dependency is on the report suite's time zone, which determines which hours are AM and which are PM.

## Dimension items

This dimension always contains exactly two dimension items: `"AM"` and `"PM"`. The dimension item `"AM"` applies to all hits from 12:00 AM to 11:59 AM, while the dimension item `"PM"` applies to all hits from 12:00 PM to 11:59 PM.
