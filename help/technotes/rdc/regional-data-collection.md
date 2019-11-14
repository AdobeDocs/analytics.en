---
title: Regional Data Collection
description: Information on Regional Data Collection
---

# Regional Data Collection

Learn about regional data collection (RDC) and how to change your collection network, if needed.

To improve data collection performance, all Adobe Experience Cloud customers have been converted to Regional Data Collection (RDC) so that collection occurs as close to your end users as possible. This improves your site/app performance and ensures that data is collected as quickly as possible to optimize the end user experience. Once data from your digital properties is collected regionally at a Data Collection Center (DCC), it is forwarded over a secure connection to a Data Processing Center (DPC), where it is processed and made available to products in the Adobe Experience Cloud. RDC has been the default for new implementations since 2009.

RDC currently includes the following locations (subject to change):

## Third-party data collection

| RDC Type | Data Collection Centers |
|---------------------|-------------------|
| Default | San Jose, Virginia, London, Singapore, Hong Kong, Sydney, Amsterdam |
| China Only | Beijing |

Note: If your Analytics image request is sent to the `2o7.net` or `omtdrc.net` endpoints, then you have third-party data collection. You can determine this if you see either endpoint in the URL of your requests.

## First-party data collection

| RDC Type | Data Collection Centers |
|---------------------|-------------------|
| Standard | San Jose, Virginia, London, Singapore |
| All | Standard plus Hong Kong, Sydney, Amsterdam |
| US Only | San Jose, Virginia |
| EU Only | London, Amsterdam |
| India Only | Mumbai |

## How RDC works

The following list describes the data collection process used by Adobe:

1. DNS automatically resolves the collection hostname to the IP address of the Data Collection Center nearest the visitor.
1. The visitor sends the data to that location.
1. The data is immediately forwarded over a secure connection to the Data Processing Center, where it is processed and made available to the products in the Adobe Experience Cloud.

## Benefits of RDC

| Benefit | Description |
|---------|-----------|
| Performance | With RDC, your visitors will be connecting to the closest DCC. This means the response times on your page will decrease (lower is better), resulting in more accurate tracking and faster loading times. More detailed information on response time can be found in Performance Improvements with RDC.|
| Redundancy | In case of a disruption in communication with a DCC, data collection is automatically routed to the next nearest DCC ensuring service continuity. |
| Redundancy | In case of a disruption in communication between the DCC and your DPC, Adobe's RDC infrastructure saves data locally, then forwards it to the DPC when communications are restored.|

## Documentation revision history

| Update | Description |
|--------|---------|
| February 20, 2019 | Complete rewrite. Added RDC network information.|
