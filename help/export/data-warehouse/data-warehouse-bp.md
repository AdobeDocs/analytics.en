---
description: Data warehouse provides a flexible interface to run custom reports. Following these guidelines can help reduce the time it takes to retrieve data.
keywords: best practices;failure;timeout;troubleshooting
title: Data Warehouse best practices
feature: Data Warehouse
uuid: d71c9138-22d9-4f92-885e-593f83f2bb59
exl-id: 7e21534b-a7ec-4231-89f1-0ad5013e70cf
---
# Data Warehouse best practices

Data Warehouse provides a flexible interface to run custom reports. Use the following guidelines to help reduce the time it takes to retrieve data:

| Guideline | Description |
|--- |--- |
|Run Page Views, Visits, Visitors, and other standard reports in Reports & Analytics|Before creating a Data Warehouse report, see if the information you are looking for is already available in reports. If so, the report will be delivered much faster due to the pre-processing performed by Reports & Analytics for common metrics.|
|Understand the amount of data you are requesting|A multi-year report on a large report suite can contain tens of billions of data rows. Processing and evaluating this data can take days, or even weeks. Evaluate how the report is being used to determine if some of the multi-year data is available, or if you can break the report into multiple requests.|
|Match the report period to the granularity|Reporting granularity requires additional processing time. If you are reporting monthly granularity for an entire year, your reports process much faster if you submit a report request for each month.|
|Report on completed data ranges|Data Warehouse reports are generated when the date range requested is complete. For example, if you request a report for the current week on Wednesday, the report isn't generated until Sunday of the following week.|
|Generate pathing reports in Data Warehouse|Pathing metrics (entries, exits, bounces, etc.) are not available in data warehouse.|
|Virtual report suites|Data Warehouse reporting on virtual report suites supports the alternative time zone configured on the virtual report suite.|
