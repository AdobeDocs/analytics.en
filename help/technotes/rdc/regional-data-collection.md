---
title: Regional Data Collection
description: Information on Regional Data Collection
exl-id: 295e9736-2a58-48a8-9968-5dfa33b70d95
---
# Regional Data Collection

The Adobe Experience Cloud uses Regional Data Collection (RDC) so that interactions between your end users and the Adobe Experience cloud occur as close to your end users as possible. This improves your site/app performance and ensures that data is collected as quickly as possible to optimize the end user experience. Once data from your digital properties is collected regionally at a Data Collection Center (DCC), it is forwarded over a secure connection to a Data Processing Center (DPC) where it is processed and made available to products in the Adobe Experience Cloud.

>[!IMPORTANT]
>
>The China RDC (China Performance Optimization) Add-On Package is a chargeable add-on to Adobe Analytics. Adobe' Performance Optimization in mainland China enables customers within China to send data directly to the China edge node, instead of other locations globally. This improves page load times and data accuracy over sending the data to nodes outside of China. Please contact your Adobe Sales representative for more information.

RDC currently includes the following locations (subject to change):

## Third-party and HTTP data collection

| RDC Type | Data Collection Centers |
|---------------------|-------------------|
| Default | Oregon, Virginia, Ireland, Paris, Mumbai, Singapore, Tokyo, Sydney, China* |

*China RDC requires the China Add-On package. See the 'Important' note above.

>[!NOTE]
>
>If your Analytics image request is sent to the `adobedc`, `2o7.net` or `omtrdc.net` endpoints, then you have third-party data collection. You can determine this if you see either endpoint in the URL of your requests.

## First-party HTTPS data collection

| RDC Type | Data Collection Centers |
|---------------------|-------------------|
| Global (Default) | Oregon, Virginia, Ireland, Paris, Mumbai, Singapore, Tokyo, Sydney |
|
| Americas Only | Oregon, Virginia |
| Europe Only | Ireland, Paris |
| Asia Pacific Only | Mumbai, Singapore, Tokyo, Sydney |
| China only* | Beijing |

*China RDC requires the China Add-On package. See the 'Important' note above.

>[!NOTE]
>
>Experience Edge Global provides the best performance for your end users.  If you want to use an alternate RDC type, please contact Adobe Customer Care for assistance.

## Benefits of RDC

| Benefit | Description |
| --- | --- |
| Performance | With RDC, your visitors will connect to the closest DCC. This provides the fastest response time, resulting in more accurate tracking and faster loading times. |
| Redundancy | In case of a disruption in communication between the DCC and your DPC, Adobe’s RDC infrastructure saves data locally, then forwards it to the DPC when communications are restored. |

## How RDC works

The following list describes the data collection process used by Adobe:

1. DNS automatically resolves the collection hostname to the IP address of the Data Collection Center nearest the visitor.
1. The visitor sends the data to that location.
1. The data is immediately forwarded over a secure connection to the Data Processing Center, where it is processed and made available to the products in the Adobe Experience Cloud.
