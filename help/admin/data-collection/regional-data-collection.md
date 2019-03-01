---
title: Regional Data Collection
seo-title: Adobe Analytics Regional Data Collection
description: Information on Regional Data Collection
seo-description: 
---

# Regional Data Collection

Learn about regional data collection (RDC) and how to change your collection network, if needed.

RDC is the default data collection method for Adobe Analytics. It includes Data Collection Centers (DCC) that are geographically distributed to optimize data speed, reduce latency, and minimize data loss associated with Adobe image requests. After data is collected at DCC sites, it is sent to the DPC associated with its report suite. Therefore, a hit collected by a DCC in Singapore might be sent to Oregon for processing, even though there is a DCC at that site.

RDC currently includes the following locations (subject to change):

## 3rd Party data collection

| RDC Type | Data Collection Centers |
|---------------------|-------------------|
| Default | San Jose, Virginia, London, Singapore, Hong Kong, Sydney, Amsterdam |
| China Only | Beijing |

## First Party data collection

| RDC Type | Data Collection Centers |
|---------------------|-------------------|
| Standard | San Jose, Virginia, London, Singapore |
| All | Standard plus Hong Kong, Sydney, Amsterdam |
| US Only | San Jose, Virginia |
| EU Only | London, Amsterdam |
| India Only | Mumbai |

## How Regional Data Collection Works

The following list describes the data collection process used by Adobe:

* DNS automatically resolves the collection hostname to the IP address of the Data Collection Center nearest the visitor.
* The vistor sends the data to that location.
* The data is immediately forwarded over a secure connection to the right Data Processing Center, where it is processed and made available to the products in the Adobe Marketing Cloud.

## Benefits of Regional Data Collection

| Benefit | Description |
|---------|-----------|
| Performance | With RDC, your visitors will be connecting to the closest DCC. This means the response times on your page will decrease (lower is better), resulting in more accurate tracking and faster loading times. More detailed information on response time can be found in Performance Improvements with RDC.|
| Redundancy | In case of a disruption in communication with a DCC, data collection is automatically routed to the next nearest DCC ensuring service continuity.|
| Redundancy | In case of a disruption in communication between the DCC and your DPC, Adobe's RDC infrastructure saves data locally, then forwards it to the DPC when communications are restored.|

## Documentation Revision History
 
| Update | Description |
|--------|---------|
| December 1, 2015 | Added [Test if your Site Is Enabled for Regional Data Collection](https://marketing.adobe.com/resources/help/en_US/whitepapers/rdc/test-regional-data-collection.html). |
| September 18, 2015 | Revisions throughout. |
| September 4, 2014 | Added details on the [Marketing Cloud Visitor ID Service](https://marketing.adobe.com/resources/help/en_US/mcvid/). This service sets a first-party cookie using JavaScript, so you no longer need to migrate to a CNAME to get the benefits of first party cookies.<br> With the introduction of this service, we no longer recommend all customers implement a CNAME along with RDC migration, instead we recommend most customers migrating to the Marketing Cloud Visitor ID service to get first-party cookies. See [Visitor ID Service Migration Decision Points](https://marketing.adobe.com/resources/help/en_US/mcvid/?f=visid_mig_overview) for details. |
| November 13, 2012 | We now require that SSL certificates be licensed for installation on up to 10 servers. |
| February 20, 2019 | Revisions throughout. Added RDC network information. |
