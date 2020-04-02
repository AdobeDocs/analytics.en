---
title: AM/PM
description: Determines if the hit happened during AM or PM hours.
---

# AM/PM

The 'AM/PM' dimension provides insight on if the hit happened during AM or PM hours. The time of the hit is based on the [report suite's time zone](../../admin/admin/general-acct-settings-admin.md).

## Populate this dimension with data

This dimension works out of the box. It does not have any settings to change. It's only dependency is on the report suite's time zone, which determines which hours are AM and which are PM.

## Dimension values

This dimension always contains exactly two dimension values: "AM" and "PM". The dimension value "AM" applies to all hits from 12:00 AM to 11:59 AM, while the dimension value "PM" applies to all hits from 12:00 PM to 11:59 PM.
