---
description: Learn about Data Warehouse and how to filter the data, letting you create and run custom reports.
title: Data Warehouse Overview
feature: Data Warehouse
uuid: 768557dd-1644-4ce6-bfc2-8c46dd6e1cd1
exl-id: 6a051d53-397b-4a55-9cca-1c83b31c9448
TQID: https://experienceleague.adobe.com/Vkn9mWvBzaiIBf1KYIEUK8cRwTuzw41MT-v-thMBg38
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
    internal-label: Reports
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
    internal-label: Analysis Workspace
subfeature_v2:
  - id: e3e906cf-5493-4e0a-9a33-bf0ac37393d6
    internal-label: Custom reports
  - id: ef60b66e-5984-4336-ba72-6d978b1b6f87
    internal-label: Report suites
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
---
# Data Warehouse overview

Data Warehouse allows you to copy Adobe Analytics data for storage and for creating custom reports, which you can run by filtering the data. 

## Reports overview

Data Warehouse reports can display advanced data relationships from raw data based on your unique questions. They can include an unlimited number of rows in a single request (for individual, scheduled, and downloaded reports).

>[!NOTE]
>
>Data Warehouse reports the first value encountered in the reporting period.

>[!IMPORTANT]
>
>When segmenting on classified values, Analysis Workspace and Data Warehouse treat 'unspecified' values differently. 'Unspecified' in Workspace refers to values that are not classified, whereas 'Unspecified' in Data Warehouse refers to values that you classified as "Unspecified".

## Delivery overview

Data Warehouse reports are emailed or sent to a cloud storage provider, and can take up to 72 hours to process. Processing time depends on the complexity of the query and the amount of data requested.

Data Warehouse automatically zips any file that exceeds 1 MB in size. The maximum email attachment size is 10 MB.

## Access

Adobe enables Data Warehouse for administrator-level users only, for specific report suites. (It can be enabled for global and child report suites, but not for rollup report suites.) The administrator can create a group that has access to Data Warehouse, and then associate non-administrator level users to that group.

See [Manage Data Warehouse permissions](/help/export/data-warehouse/t-dw-group.md).

## Create a Data Warehouse request

For information about how to create a Data Warehouse request, see [Create a Data Warehouse request](/help/export/data-warehouse/create-request/t-dw-create-request.md).

## Manage Data Warehouse requests

For information about how to manage Data Warehouse requests, see [Manage Data Warehouse requests](/help/export/data-warehouse/data-warehouse-requests-manage.md).

