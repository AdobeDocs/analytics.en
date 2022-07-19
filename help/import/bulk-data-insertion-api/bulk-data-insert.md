---
title: Bulk Data Insertion API
description: Bulk Data Insertion API (BDIA) is an Adobe Analytics capability that lets you upload server call data in batches of files instead of using client-side libraries such as AppMeasurement. The server calls in these batch files can be either current (live) data or historical data. It is a more scalable successor to the Data Insertion API in previous versions of the Adobe Analytics API.
solution: Analytics
feature: API
exl-id: c9d23fae-2800-42bb-8f8d-adf915cadc62
---
# Bulk Data Insertion API

Bulk Data Insertion solves several use cases, such as:

* Ingesting historical data from a previous analytics system

* An internal analytics collection system that makes it unfeasible to use AppMeasurement. You can use Extract-Transform-Load (ETL) processes to put data into batch files then use BDIA to upload them to Adobe Analytics.

* Data collection from devices that have only intermittent connectivity to the internet. These devices store up the interactions until they receive a connection. The device can then upload the data all at once via BDIA.

Refer to the [developer documentation for Bulk Data Insert API](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/bulk-data-insertion/) for more information.

[Data Insertion API](https://github.com/AdobeDocs/analytics-1.4-apis/blob/master/docs/data-insertion-api/index.md) and [Bulk Data Insertion API](../bulk-data-insertion-api/bulk-data-insert.md) are both methods to submit server-side collection data to Adobe Analytics. Data Insertion API calls are made one event at a time. Bulk Data Insertion API accepts CSV formatted files containing event data, one event per row. If you are working on a new implementation of server-side collection, we recommend using Bulk Data Insertion API.
