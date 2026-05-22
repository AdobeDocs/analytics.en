---
description: Learn how sorting by metric makes Data Warehouse reports easy to interpret and to compare with other Analytics breakdown reporting views.
title: Sort by Metric
feature: Data Warehouse
exl-id: 6bd82951-c3b4-4ba2-8e4d-b7c9b351911b
TQID: 'https://experienceleague.adobe.com/YPqL6i9RWACubLdf2ywm8xuPyeQkZ30L6rO6FAbhpJI'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
    internal-label: Reports
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
  - id: b8734a57-d5fb-44a8-8ee1-65225cecaeae
    internal-label: Data configuration and collection
subfeature_v2:
  - id: f47edbe0-f963-46ff-a667-71011396f5f3
    internal-label: Data Warehouse
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
---
# Sort by metric

Provides ranked breakdown reports in Data Warehouse, sorted by descending metric value.

Sorting by metric makes Data Warehouse reports easier for you to interpret, and makes these reports easier to compare with other Analytics breakdown reporting views.

The following shows how enabling the "Metrics Sort" option will reorder rows in a Data Warehouse report.

There are four possible ways that Data Warehouse reports may be organized with "Metrics Sort", based on how date granularity, reporting dimensions, or metrics are configured, and whether "Max rows" is set:

* **Layout 1**: Line items are sorted in dictionary order (default). If "Max rows" is set, only the first N rows are provided in the report.
* **Layout 2**: Data Warehouse applies a metric sort over all rows in the report. Ties in the first metric value are broken by the 2nd metric, and then the 3rd, and so on. When all metrics are tied, the standard dictionary ordering of breakdown line items is applied.
* **Layout 3**: As Layout 2, with only the top N rows (i.e., the number set in "max rows") being output in the report.
* **Layout 4**: As Layout 2, with the exception that line items for each date granularity period are grouped together and sorted within that respective time range.

Please reference the "Report layout" column in this table to determine how "Metrics Sort" interacts with other Data Warehouse reporting options.

|  Sort by Metric?  | Has Metrics?  | Has Breakdowns?  | Date Granularity?  | Max rows set?  | Report Layout  |
|---|---|---|---|---|---|
|  No  | Yes or No  | Yes or No  | Yes or No  | Yes or No  | 1  |
|  Yes  | No  | Yes or No  | Yes or No  | Yes or No  | 1  |
|  Yes  | Yes  | No  | No  | N/A  | 1  |
|  Yes  | Yes  | No  | Yes or No  | No  | 1  |
|  Yes  | Yes  | Yes  | No  | No  | 2  |
|  Yes  | Yes  | No  | Yes  | Yes  | 3  |
|  Yes  | Yes  | Yes  | Yes or No  | Yes  | 3  |
|  Yes  | Yes  | Yes  | Yes  | No  | 4  |
