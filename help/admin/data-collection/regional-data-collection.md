---
title: Regional Data Collection
seo-title: Adobe Analytics Regional Data Collection
description: Information on Regional Data Collection
seo-description: 
---

# Regional Data Collection

Learn about regional data collection (RDC) and how to change your collection network, if needed.

RDC is the default data collection method for Adobe Analytics. It includes Data Collection Centers (DCC) that are geographically distributed to optimize data speed, reduce latency, and minimize data loss associated with Adobe image requests. After data is collected at DCC sites, it is sent to the DPC associated with its report suite. Therefore, a hit collected by a DCC in Singapore might be sent to Oregon for processing, even though there is a DCC at that site.

RDC includes the following networks:

| Collection Network | DCC Locations | DPC Locations |
|---------------------|-----------|-----------|
| Standard | San Jose, Virginia, London, Singapore | Singapore |
| All 10 | Standard DCCs plus additional DCCs in Hongkong, Sydney, Amsterdam | London |
| US Only | San Jose, Virginia | San Jose |
| EU Only | London, Amsterdam | London |
| APAC Only | Hongkong, Sydney, Singapore | Singapore |
| China Only | Within China | Within China |
| India Only | Within India | Within India |

## How Regional Data Collection Works

The following list describes the data collection process used by Adobe:

* When a hit is sent, the Adobe image request automatically routes to the DCC nearest the visitor.
* The DCC uses a secure data pipe to immediately forward the data to the DPC, where it is processed and made available to the products in the Adobe Marketing Cloud.
* The RDC domain also routes Data Insertion API requests through the nearest DCC.


## Benefits of Regional Data Collection
| Benefit |	Description |
|---------|-----------|
| Performance | With RDC, your visitors will be connecting to the closest DCC. This means the response times on your page will decrease (lower is better), resulting in more accurate tracking and faster loading times. More detailed information on response time can be found in Performance Improvements with RDC.|
| Security | Without RDC, only HTTPS hits are encrypted between the browser and the data collection center. When using RDC, the hit is encrypted after it hits the data collection center. This means that all data sent from the data collection center to the data processing center is encrypted. |
| Redundancy | In case of a disruption in communication between the DCC and your DPC, Adobe's RDC infrastructure behaves as follows: <br><br>- Attempts are made to route data to your data processing center through another DCC. <br><br>- Saves data locally, then forwards it to the DPC when communications are restored. Due to limits on storage space, this option is available only for short-term disruptions.<br><br>- For major disruptions, the Adobe Network Operations team reconfigures the global DNS system used by RDC to forward your data through another data collection center.<br><br> *Note: Data is not stored at DCCs unless there is a network failure between the DCC and the DPC. If a network failure occurs, the data is stored only until the connection is restored.* |

 ## Documentation Revision History
 
| Update | Description |
|--------|---------|
| December 1, 2015 | Added [Test if your Site Is Enabled for Regional Data Collection](https://marketing.adobe.com/resources/help/en_US/whitepapers/rdc/test-regional-data-collection.html). |
| September 18, 2015 | Revisions throughout. |
| September 4, 2014 | Added details on the [Marketing Cloud Visitor ID Service](https://marketing.adobe.com/resources/help/en_US/mcvid/). This service sets a first-party cookie using JavaScript, so you no longer need to migrate to a CNAME to get the benefits of first party cookies.<br> With the introduction of this service, we no longer recommend all customers implement a CNAME along with RDC migration, instead we recommend most customers migrating to the Marketing Cloud Visitor ID service to get first-party cookies. See [Visitor ID Service Migration Decision Points](https://marketing.adobe.com/resources/help/en_US/mcvid/?f=visid_mig_overview) for details. |
| November 13, 2012 | We now require that SSL certificates be licensed for installation on up to 10 servers. |
| February 20, 2019 | Revisions throughout. Added RDC network information.
