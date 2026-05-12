---
title: Cities
description: The city where the hit originated from.
feature: Dimensions
exl-id: c04525bb-50d6-4d28-b5dc-335d089e184b
TQID: https://experienceleague.adobe.com/tAr9M0IgZcpRzElFfQSJx43JJjIXEtlo-pgDAKpSwq0
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
    internal-label: Reports
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
    internal-label: Implementations
subfeature_v2:
  - id: d2311670-43bd-4c2e-bc98-1da2aaba9cef
    internal-label: Appmeasurement implementation
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
    internal-label: Calculated Metrics
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
    internal-label: Measurement
  - id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
    internal-label: Privacy
---
# Cities

The 'Cities' [dimension](overview.md) reports the city where the hit originated from. This dimension is useful to help determine what the most popular cities visitors originate from when visiting your site. You could use this data to focus on local advertising in these cities, such as billboards or commercials.

## Populate this dimension with data

This dimension references lookup rules internal to Adobe. The lookup value is based on the IP address sent with the hit. Adobe partners with [Digital Element](https://www.digitalelement.com/) to maintain lookups between IP address and city.

* For AppMeasurement implementations, this dimension works out of the box.
* For Web SDK implementations, enable [!UICONTROL Geo Lookup] when [configuring a datastream](https://experienceleague.adobe.com/docs/experience-platform/datastreams/configure.html).

## Dimension items

Dimension items include cities all over the world. Example values include `"New York (New York, United States)"`, `"Bangalore (Karnataka, India)"`, or `"London (London, United Kingdom)"`.

Some dimension items can include `"AOL"`, a dial-up internet service provider. Subscribers to this service are assigned an access point based on the country where their account number is established. AOL users use the IP address of this access point. Since this dimension is based on IP address, the geolocation of the access point is used instead of the visitor's actual location.

## Differences between reported and actual location

Since this dimension is based on IP address, some scenarios can show a difference between reported location and actual location:

* **IP addresses that represent corporate proxies**: These visitors can appear as traffic coming through the user's corporate network, which can be a different location if the user is working remotely.
* **Mobile IP addresses**: Mobile IP targeting works at varying levels depending on the location and the network. Some carriers backhaul IP traffic through centralized or regional points of presence.
* **Satellite ISP users**: Identifying the specific location of these users is difficult, as they typically appear to originate from the uplink location.
* **Military and government IPs**: Represents personnel traveling around the globe and entering through their home location, rather than the base or office where they are currently stationed.
* **Proxies that obscure IP addresses for privacy reasons**: Services like Apple's Private Relay hide the true IP address by randomly sending data through an intermediary or proxy. This proxy then substitutes a different IP address before forwarding to Adobe.
