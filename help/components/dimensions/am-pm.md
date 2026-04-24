---
title: AM/PM
description: Determines if the hit happened during AM or PM hours.
feature: Dimensions
exl-id: 93fcdb9f-2ba3-402c-a389-b02ed8c990d2
TQID: https://experienceleague.adobe.com/R1syrJ7ylIe2ywH1isX4sjR2O84-8eL-jooYhjUdKhI
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
subfeature_v2:
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
    internal-label: Calculated Metrics
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
---
# AM/PM

The 'AM/PM' [dimension](overview.md) provides insight on if the hit happened during AM or PM hours. The time of the hit is based on the [report suite's time zone](/help/admin/tools/manage-rs/edit-settings/general/general-acct-settings-admin.md).

## Populate this dimension with data

This dimension works out of the box. It does not have any settings to change. Its only dependency is on the report suite's time zone, which determines which hours are AM and which are PM.

## Dimension items

This dimension always contains exactly two dimension items: `"AM"` and `"PM"`. The dimension item `"AM"` applies to all hits from 12:00 AM to 11:59 AM, while the dimension item `"PM"` applies to all hits from 12:00 PM to 11:59 PM.
