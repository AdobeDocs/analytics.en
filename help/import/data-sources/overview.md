---
title: Data sources overview
description: Import data into Adobe Analytics using external files.
---

# Data sources overview

Adobe Analytics data sources let you import additional online or offline data for reporting. They are valuable to help understand facets of your business outside your website, and how they interact with your site. The general workflow to use data sources consists of the following steps:

1. Your organization collects data from other sources. Examples include pre-click data, call center data, or information on transactions that occurred outside of your site.
1. Data is formatted in a way Adobe Analytics understands in a tab-delimited text file.
1. You upload the text file to an FTP site Adobe provides, along with an accompanying .fin file.
1. Adobe ingests the text file and displays that data alongside dimensions and metrics collected on your site.

There are three types of data sources that Adobe offers:

* **Summary data source**: Provides an easy way to import high-level data in Adobe Analytics. You specify the variable value and associated metrics, and those metrics are increased accordingly. It is valuable if you want to see offline and online data side-by-side. However, it does not link online and offline data together.
* **Transaction ID data source**: If a hit sent by AppMeasurement and a data sources row contain matching transaction ID's, the dimension and metric values in the data source append to that hit.

**Full processing data sources** is no longer offered as a data source type as of 25 March 2021. See the [End-of-life announcement](full-processing-eol.md) for more information.

## Next steps

* [Getting started with data sources](getting-started.md): Upload a simple data source to a development report suite. Example files for all three data source types are included.
