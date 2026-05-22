---
title: Bulk Data Insertion API
description: Bulk Data Insertion API (BDIA) is an Adobe Analytics capability that lets you upload server call data in batches of files instead of using client-side libraries such as AppMeasurement.
solution: Analytics
feature: API
exl-id: c9d23fae-2800-42bb-8f8d-adf915cadc62
role: Admin
TQID: 'https://experienceleague.adobe.com/TVa-LtTWKi6lQKGQKhH2bu5UcKsSJ2-KVqlfU5tQROQ'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
    internal-label: API
  - id: b8734a57-d5fb-44a8-8ee1-65225cecaeae
    internal-label: Data configuration and collection
subfeature_v2:
  - id: f46a60da-b0b2-4ca3-bd91-271173f4123d
    internal-label: Data sources
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
    internal-label: Measurement
  - id: d3cdead0-685a-4489-9250-4bb709942f66
    internal-label: Data collection
---
# Bulk Data Insertion API

Bulk Data Insertion solves several use cases, such as:

* Ingesting historical data from a previous analytics system

* An internal analytics collection system that makes it unfeasible to use AppMeasurement. You can use Extract-Transform-Load (ETL) processes to put data into batch files then use BDIA to upload them to Adobe Analytics.

* Data collection from devices that have only intermittent connectivity to the internet. These devices store up the interactions until they receive a connection. The device can then upload the data all at once via BDIA.

Data Insertion API and [Bulk Data Insertion API](https://www.adobe.io/apis/experiencecloud/analytics/docs.html#!AdobeDocs/analytics-2.0-apis/master/bdia.md)are both methods to submit server-side collection data to Adobe Analytics. Data Insertion API calls are made one event at a time. Bulk Data Insertion API accepts CSV formatted files containing event data, one event per row. If you are working on a new implementation of server-side collection, we recommend using Bulk Data Insertion API.
