---
description: Understand reporting differences between Analysis Workspace, data warehouse, and data feeds
title: Reporting differences between Analysis Workspace, data warehouse, and data feeds
feature: Analytics Basics
---
# Reporting differences between Analysis Workspace, data warehouse, and data feeds

**Analysis Workspace** uses a combination of data that is processed in the Analytics pipeline and data that is processed at report time. (For more information, see [Report time attribution]().) 

**Data feeds and data warehouse** exclusively use data that is processed in the Analytics pipeline, prior to report time.

Because of these processing differences, you might see discrepencies when comparing data in Analysis Workspace to data in data feeds and data warehouse. 

Following are examples of reporting differences you might see when comparing data in Analysis Workspace to data in data feeds and data warehouse

| Dimensions that are affected by processing differences | Analysis Workspace | Data warehouse and data feeds |
|---------|----------|---------|
| Geography-related dimensions (DMA, Country, City, and so forth)  | Because geography-related dimensions are calculated at report time in Analysis Workspace, the value of these dimensions can change during the visit. <p>For example, IP addresses on mobile devices are sometimes inaccurate and can change, such as when transitioning from wifi to cellular during a visit. If your IP address changes in the middle of a visit, that can impact your geo dimension values.</p>  | Because geography-related dimensions are calculated in the Analytics pipeline (prior to report time) for data feeds and data warehouse, the value of these dimensions persist throughout the visit. <p>For example, this means that your geo dimension values remain the same for the entire visit, regardless of changes that might occur, such as when transitioning from wifi to cellular during a vist.</p> |
| Technology-related dimensions (Operating system, Browser, and so forth) | Because technology-related dimensions are calculated at report time in Analysis Workspace, the value of these dimensions can change during the visit. <p>For example, IP addresses on mobile devices are sometimes inaccurate and can change, such as when transitioning from wifi to cellular during a visit. If your IP address changes in the middle of a visit, that can impact your technology dimension values.</p>  | Because technology-related dimensions are calculated in the Analytics pipeline (prior to report time) for data feeds and data warehouse, the value of these dimensions persist throughout the visit. <p>For example, this means that your technology dimension values remain the same for the entire visit, regardless of changes that might occur, such as when transitioning from wifi to cellular during a vist.</p>  |
| A3 | B3 | C3 |
| A3 | B3 | C3 |
| A3 | B3 | C3 |


