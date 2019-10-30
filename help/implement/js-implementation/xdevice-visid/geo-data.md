---
description: Geo-segmentation data is recorded based on the first hit of the visit, and does not change for a single visit regardless of the device used.
keywords: Analytics Implementation
seo-description: Geo-segmentation data is recorded based on the first hit of the visit, and does not change for a single visit regardless of the device used.
seo-title: Geo-segmentation data
solution: Analytics
title: Geo-segmentation data
topic: Developer and implementation
uuid: 8449bf11-c367-4698-a73e-f6cb59f8c945
---

# Geo-segmentation data

>[!IMPORTANT]
>
>This method of identifying visitors across devices is no longer recommended. Please refer to the [Adobe Experience Cloud Device Co-op Documentation](https://marketing.adobe.com/resources/help/en_US/mcdc/).

Geo-segmentation data is recorded based on the first hit of the visit, and does not change for a single visit regardless of the device used.

 If a customer browses your site from his or her home computer, and then from a mobile device within 30 minutes, the geo-segmentation data is not changed. If you are using VISTA to populate an eVar with geo-segmentation data, it is based on the IP address in each hit. This could result in multiple geo-segmentation data values if the IP address changes for the same visit.
