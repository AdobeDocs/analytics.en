---
title: Domain
description: The organization or ISP the visitor uses to access the internet.
feature: Dimensions
exl-id: 292dc256-e9e7-47be-8586-774f1c047011
---
# Domain

The 'Domain' [dimension](overview.md) reports the access points that visitors use to access the internet.

## Populate this dimension with data

Adobe partners with [Digital Element](https://www.digitalelement.com/) to determine the access point domain. Several methods, including reverse DNS lookup, are used to determine the access point domain. It does not require any configuration, and does not have a variable to populate.

* For AppMeasurement implementations, this dimension works out of the box.
* For Web SDK implementations, enable [!UICONTROL Network Lookup] when [configuring a datastream](https://experienceleague.adobe.com/docs/experience-platform/datastreams/configure.html).

## Dimension items

Example dimension items include `comcast.net`, `rr.com`, `sbcglobal.net`, and `amazonaws.com`. These domains are access points, and not necessarily the domain representing an ISP or organization.

Dimension values of `None` mean that the owner of the access point IP address did not provide a domain.
