---
description: Customer attributes are stored in new type of element called VisAttr, which can be configured as a dimension or a metric.
title: Customer attributes
feature: Report Builder
role: User, Admin
exl-id: b5855ce0-6d17-4690-a2c2-366b66ab8e83
TQID: https://experienceleague.adobe.com/J-KoYBPg-bECW1utOk2L0YLtBWd9-jHT6gwAEm54fs4
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
    internal-label: Analysis Workspace
  - id: f73667dc-d296-4875-8975-ac3fdc3adc42
    internal-label: Dashboards
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
---
# Customer attributes

{{legacy-arb}}

Customer attributes are stored in new type of element called VisAttr, which can be configured as a dimension or a metric.

 For more detailed information on how to upload customer attributes, see the [Experience Cloud help](https://experienceleague.adobe.com/docs/core-services/interface/customer-attributes/attributes.html).

* If it's configured as a metric, VisAttr is exposed both as metric and "dimension".

  ![Screenshot showing metric and dimension Customer Attributes.](assets/ca_metrics.png)  ![](assets/ca_dimension.png)

* It supports the same breakdown as an eVar (anything can be broken down by anything).
* VisAttr supports all eVar metrics.
* VisAttr as a metric supports "bucketization" (like Time Spent on Site: 0 to 30, 31 to 60, …) 
* VisAttr is available as a segmentation dimension.
