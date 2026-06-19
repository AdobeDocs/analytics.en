---
title: Domain
description: The organization or ISP the visitor uses to access the internet.
feature: Dimensions
exl-id: 292dc256-e9e7-47be-8586-774f1c047011
TQID: https://experienceleague.adobe.com/D-qRVSeU1Gx9YMDXvcDYLbSo9tCcR-0mUiD-2KsN3g4
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
  - id: c8add8f2-4250-4fd9-9cde-9707036c567d
    internal-label: Methods
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
---
# Domain

The 'Domain' [dimension](overview.md) reports the access points that visitors use to access the internet.

>[!NOTE]
>
>Data Warehouse includes a retired '[!UICONTROL Domains]' (plural) dimension that reports similar information. Adobe recommends using this dimension, '[!UICONTROL Domain]' (singular), for consistency.

## Populate this dimension with data

Adobe partners with [Digital Element](https://www.digitalelement.com/) to determine the access point domain. Several methods, including reverse DNS lookup, are used to determine the access point domain. It does not require any configuration, and does not have a variable to populate.

* For AppMeasurement implementations, this dimension works out of the box.
* For Web SDK implementations, enable [!UICONTROL Network Lookup] when [configuring a datastream](https://experienceleague.adobe.com/docs/experience-platform/datastreams/configure.html).

## Dimension items

Example dimension items include `comcast.net`, `rr.com`, `sbcglobal.net`, and `amazonaws.com`. These domains are access points, and not necessarily the domain representing an ISP or organization.

Dimension values of `None` mean that the owner of the access point IP address did not provide a domain.
