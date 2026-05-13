---
title: Data sources overview
description: Import data into Adobe Analytics using external files.
exl-id: 5ec8bc51-dfd2-497c-aebc-a32d87efc97e
feature: Data Sources
role: Admin
TQID: https://experienceleague.adobe.com/AOl1PUYf4TL0FrYB8eHL-JLiWvz6ixJYKUPpIZEFqj8
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
    internal-label: Reports
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
  - id: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
    internal-label: API
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
    internal-label: Measurement
---
# Data sources overview

Adobe Analytics data sources let you import additional online or offline data for reporting. They are valuable to help understand facets of your business outside your website, and how they interact with your site. The general workflow to use data sources consists of the following steps:

1. Your organization collects data from other sources. Examples include pre-click data, call center data, or information on transactions that occurred outside of your site.
1. Data is formatted in a way that Adobe Analytics understands using a tab-delimited text file.
1. You upload the text file to an FTP site Adobe provides, along with an accompanying `.fin` file.
1. Adobe ingests the text file and displays that data alongside dimensions and metrics collected on your site.

There are two general types of data sources that Adobe offers. All data source templates are based on one of these two types:

* **Summary data source**: Provides an easy way to import high-level data in Adobe Analytics. You specify the timestamp, variable value, and associated metrics. Those metrics for each dimension item are then increased accordingly. It is valuable if you want to see offline and online data side by side. However, it does not link online and offline data together.
* **Transaction ID data source**: If a hit sent by AppMeasurement and a data sources row contain matching transaction ID's, the dimension and metric values in the data source append to that hit.

**Full processing data sources** are no longer offered as a data source type as of 25 March 2021. See the [End-of-life announcement](full-processing-eol.md) for more information.

Adobe also offers the [Data sources API](https://developer.adobe.com/analytics-apis/docs/1.4/guides/data-sources/), which allows you to create data sources and upload data without using the product UI or an FTP location.

## Next steps

[Getting started with data sources](getting-started.md): Upload a simple data source to a development report suite.
