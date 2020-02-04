---
title: Regional Data Collection
description: Information on Regional Data Collection
---

# Regional Data Collection

The Adobe Experience Cloud uses Regional Data Collection (RDC) so that interactions between your end users and the Adobe Experience cloud occur as close to your end users as possible. This improves your site/app performance and ensures that data is collected as quickly as possible to optimize the end user experience. Once data from your digital properties is collected regionally at a Data Collection Center (DCC), it is forwarded over a secure connection to a Data Processing Center (DPC) where it is processed and made available to products in the Adobe Experience Cloud.

RDC currently includes the following locations (subject to change):

## Third-party and HTTP data collection

| RDC Type | Data Collection Centers |
|---------------------|-------------------|
| Default | Oregon, Virginia, Ireland, Paris, Mumbai, Singapore, Tokyo, Sydney |
| China | Beijing |

Note: If your Analytics image request is sent to the `2o7.net` or `omtdrc.net` endpoints, then you have third-party data collection. You can determine this if you see either endpoint in the URL of your requests.

## First-party HTTPS data collection

| RDC Type | Data Collection Centers |
|---------------------|-------------------|
| Global (Default) | Oregon, Virginia, Ireland, Paris, Mumbai, Singapore, Tokyo, Sydney |
| Americas Only | Oregon, Virginia |
| Europe Only | Ireland, Paris |
| Asia Pacific Only | Mumbai, Singapore, Tokyo, Sydney |

Note: Experience Edge Global provides the best performance for your end users.  If you desire to use an alternate RDC type, please contact Adobe Custome Care for assistance.

## How RDC works

The following list describes the data collection process used by Adobe:

1. DNS automatically resolves the collection hostname to the IP address of the Data Collection Center nearest the visitor.
1. The visitor sends the data to that location.
1. The data is immediately forwarded over a secure connection to the Data Processing Center, where it is processed and made available to the products in the Adobe Experience Cloud.

## Benefits of RDC

| Benefit | Description |
|---------|-----------|
| Performance | With RDC, your visitors will be connecting to the closest DCC. This means the response times on your page will decrease (lower is better), resulting in more accurate tracking and faster loading times.|
| Redundancy | In case of a disruption in communication with a DCC, data collection is automatically routed to the next nearest DCC ensuring service continuity. |
| Redundancy | In case of a disruption in communication between the DCC and your DPC, Adobe's RDC infrastructure saves data locally, then forwards it to the DPC when communications are restored.|

## Documentation revision history

| Update | Description |
|--------|---------|
| February 4, 2020 | Update RDC locations |
| February 20, 2019 | Complete rewrite. Added RDC network information.|
