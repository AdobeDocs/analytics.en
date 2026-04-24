---
title: Classifications overview
description: Customize the grouping of dimension items.
feature: Classifications
exl-id: 0d2c77ea-610f-48e0-b6a2-6e91794783b1
TQID: https://experienceleague.adobe.com/raB90u-JEBgDroQPLC1eCSmxs4V-J7Av8Snr6oeKwvk
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
  - id: a004cc84-67b9-4a33-a3a7-8ec7273ef4dc
    internal-label: Metadata
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
---
# Classifications overview

A classification is a way of categorizing Analytics variable data, then displaying the data in different ways when you generate reports. You establish a relationship between a variable value and metadata related to that value. Classifications can be used on most custom dimensions, such as [Tracking code](/help/components/dimensions/tracking-code.md), [props](/help/components/dimensions/prop.md), and [eVars](/help/components/dimensions/evar.md).

* **Classification sets** are the primary components to classify data. [Classification sets](/help/components/classifications/sets/overview.md) allow you to create and manage classifications in a single, simplified interface.

* **Legacy classifications** documents the legacy classification methods to classify data. These methods will be deprecated in the near future and will no longer be accessible.

  * [Classification rules](/help/components/classifications/crb/classification-rule-builder.md): Create rules that assign a given dimension item to a classification dimension item. This method to classify data is best when a dimension frequently encounters new unique values or where manual classifications would be frequent and burdensome. This functionality will be deprecated after February 28, 2027.

  * [Classification importer](/help/components/classifications/importer/c-working-with-saint.md): Export a template spreadsheet with dimension items in each row. Columns represent each classification for a dimension. This method to classify data is best when all dimension items are known and does not require frequent updating. This functionality will be deprecated after August 31, 2026. With the deprecation, you will no longer be able to import classifications using standard FTP.

A single dimension can have multiple classification dimensions. For example, you can classify [!UICONTROL Product IDs] with additional product attributes, such as product name, color, size, description, and SKU. Each of these attributes would be a separate classification dimension belonging to the same parent dimension. Augmenting your reports with these attributes provides deeper and more complex reporting opportunities. Once a dimension contains classification data, the classification dimension is available in reporting that contains only classification dimension items. Any parent dimension item that does not contain a classification value is grouped under [Unspecified](/help/technotes/unspecified.md)
