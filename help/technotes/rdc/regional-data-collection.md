---
title: Regional Data Collection
description: Information on Regional Data Collection
feature: Regional Data Collection
exl-id: 295e9736-2a58-48a8-9968-5dfa33b70d95
---
# Regional Data Collection

The Adobe Experience Cloud uses Regional Data Collection (RDC) so that interactions between your visitors and Adobe occur as close to your visitors as possible. Once data is collected regionally at a Data Collection Center (DCC), it is forwarded over a secure connection to a Data Processing Center (DPC). After processing, the data is available to products in the Adobe Experience Cloud. To change your RDC Type please contact Adobe Customer Care.

The regional data collection process uses the following steps:

1. DNS automatically resolves the collection hostname to the IP address of the Data Collection Center nearest to the visitor.
1. The visitor sends the data to that location.
1. The data is immediately forwarded over a secure connection to the Data Processing Center, where it is processed and made available to the products in the Adobe Experience Cloud.

Using regional data collection provides several benefits:

* **Performance**: With RDC, your visitors connect to the closest DCC. This optimization provides the fastest response time, resulting in more accurate tracking and faster loading times.
* **Redundancy**: If there is a disruption in communication between the DCC and your DPC, Adobe's RDC infrastructure saves data locally, then forwards it to the DPC when communications are restored.

RDC currently includes the following locations (subject to change):

## Third-party data collection

| RDC Type | Data Collection Centers |
| --- | --- |
| Default | Oregon, Virginia, Ireland, Paris, Mumbai, Singapore, Tokyo, Sydney, China* |

{style="table-layout:auto"}

*China RDC requires the China Add-On package. See [China Performance Optimization](#china-performance-optimization) below.

>[!NOTE]
>
>If your Analytics image request is sent to the `adobedc.net`, `2o7.net` or `omtrdc.net` endpoints, then you have third-party data collection. You can determine this if you see either endpoint in the URL of your requests.

## First-party data collection

| RDC Type | Data Collection Centers |
| --- | --- |
| Global (Default) | Oregon, Virginia, Ireland, Paris, Mumbai, Singapore, Tokyo, Sydney |
| Global + China* | China*, Oregon, Virginia, Ireland, Paris, Mumbai, Singapore, Tokyo, Sydney |
| Americas Only | Oregon, Virginia |
| Europe Only | Ireland, Paris |
| Asia Pacific Only | Mumbai, Singapore, Tokyo, Sydney |
| China Only* | Beijing |

{style="table-layout:auto"}

*China Only and Global + China RDC types require the China Add-On package. Global + China routes data originating inside China to Adobe's China RDC while routing data originating outside of China to the nearest RDC outside of China. See [China Performance Optimization](#china-performance-optimization) below.

## China Performance Optimization

The China RDC (China Performance Optimization) add-on package is a chargeable add-on to Adobe Analytics. Adobe's Performance Optimization in Mainland China enables customers with users inside China to have that data sent directly to Adobe data collection servers inside China instead of other locations globally. This optimization improves page load times and data accuracy over sending the data to locations outside of China. Data is ultimately transferred to one of Adobe's Data Processing Centers (DPC) outside of China. Contact your Adobe Sales representative for more information.

>[!NOTE]
>
>The China RDC add-on package is not supported for the [Web SDK](/help/implement/aep-edge/overview.md). 

