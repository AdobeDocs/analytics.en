---
title: Customer loyalty
description: Categories based on the number of previous purchases a visitor has made.
feature: Dimensions
exl-id: 48ac1fdf-9a32-4bcc-8b23-bf58358a3470
TQID: https://experienceleague.adobe.com/Essa0dflFlsqwtTQ4JdaSEOkX6T-zEYrQGhgXBWhfcI
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
    internal-label: Reports
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
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
---
# Customer loyalty

The 'Customer loyalty' [dimension](overview.md) reports the number of visitors to your site that have made 0 prior purchases, 1 prior purchase, 2 prior purchases, or 3+ prior purchases. This dimension is valuable to understand how your site affects purchasing behavior. You can also use this dimension in a segment to focus on visitors that return to make a purchase, so that you can encourage similar behavior for new visitors.

## Populate this dimension with data

Adobe automatically populates this dimension based on the [`purchase`](/help/implement/vars/page-vars/events/event-purchase.md) event in your implementation. If you implement the `purchase` event on your site, this dimension always works.

## Dimension items

Dimension items include the following:

* **Not a customer**: At the time of the hit, the visitor has never made a purchase before.
* **New customers**: At the time of the hit, the visitor made a single purchase before.
* **Return customers**: At the time of the hit, the visitor made two purchases before.
* **Loyal customers**: At the time of the hit, the visitor made three or more purchases before.

When a visitor makes a purchase (triggers the `purchase` event), that hit and all subsequent hits move into the next "bucket". For example, if a visitor buys a product from your site for the first time, they move from "Not a customer" to "New customers", with the order attributed to "New customers". The dimension item "Not a customer" cannot have orders attributed to it.
