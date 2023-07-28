---
description: Data warehouse refers to the copy of Analytics data for storage and custom reports, which you can run by filtering the data. You can request reports to display advanced data relationships from raw data based on your unique questions. Data warehouse reports are emailed or sent to a cloud storage provider, and may take up to 72 hours to process. Processing time depends on the complexity of the query and the amount of data requested.
title: Data Warehouse overview
feature: Data Warehouse
uuid: 768557dd-1644-4ce6-bfc2-8c46dd6e1cd1
exl-id: 6a051d53-397b-4a55-9cca-1c83b31c9448
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

## FAQ

For a list of frequently asked questions, see [Data Warehouse FAQ](/help/export/data-warehouse/faq.md).