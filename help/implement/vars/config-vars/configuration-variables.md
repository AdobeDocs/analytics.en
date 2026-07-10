---
title: Configuration variables
description: Use configuration variables to help determine how data is collected.
feature: Appmeasurement Implementation
exl-id: 3f017a94-b71d-47da-8ab4-daf32475ed34
role: Admin, Developer
TQID: https://experienceleague.adobe.com/amtLWIgyADqWBOv38xdJ6AF4IjhJ0aGVrvYqXLckfkI
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
    internal-label: Implementations
subfeature_v2:
  - id: c069c44e-5426-4c1a-accc-8028662f2fde
    internal-label: Functions
  - id: e7d92df1-c5ba-4e93-85df-f83171b889be
    internal-label: Variables
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
    internal-label: Measurement
  - id: d3cdead0-685a-4489-9250-4bb709942f66
    internal-label: Data collection
---
# Configuration variables overview

Configuration variables control the way data is captured and processed in reporting. They do not typically contain dimension or metric values.

## Setting configuration variables

In implementations using the Web SDK extension or Analytics extension, configuration variables are typically found in the extension's settings:

1. Log in to [Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) using your Adobe ID credentials.
1. Click the desired tag property.
1. Click the [!UICONTROL Extensions] tab, then Click [!UICONTROL Configure] under the extension.

In JavaScript implementations using `AppMeasurement.js`, configuration variables are typically set at the top of the JS file.

>[!IMPORTANT]
>
>Make sure that all configuration variables are set before calling a tracking method ([`t()`](../functions/t-method.md) or [`tl()`](../functions/tl-method.md)). Avoid setting configuration variables in the [`doPlugins()`](../functions/doplugins.md) function.

## Retired configuration variables

The following configuration variables are retired. They are documented here for reference if you encounter them in a legacy implementation.

* **`account`**: Determined the report suite that data was sent to. Report suite is now handled through tracking object instantiation (the [`s_gi()`](../functions/s-gi.md) method). Use the [`s.sa()`](../functions/sa-method.md) method if you need to change the report suite after the tracking object is instantiated.
* **`cookieDomain`**: Determined the domain on which AppMeasurement set cookies. Current versions of AppMeasurement automatically detect the correct cookie domain, making this variable obsolete.
* **`cookieDomainPeriods`**: Helped AppMeasurement determine where to store cookies when a domain contained multiple periods. Current versions of AppMeasurement automatically detect the correct domain, making this variable obsolete.
* **`fpCookieDomainPeriods`**: The first-party equivalent of `cookieDomainPeriods`, used to set cookies in the correct location when a first-party domain's suffix contained an extra period (such as `example.co.uk`). Current versions of AppMeasurement automatically detect the correct domain, making this variable obsolete.
* **`trackingServer`**: Specified the domain used to send data to Adobe over HTTP. It is deprecated in favor of secure data collection over HTTPS. Use [`trackingServerSecure`](trackingserversecure.md) instead.
* **`trackInlineStats`**: Enabled or disabled previous versions of [Activity Map](/help/analyze/activity-map/overview.md).
* **`visitorMigrationKey`**: Carried a key used to migrate visitors from third-party to first-party cookies. It is retired because modern libraries set a first-party fallback cookie (`fid`) and rely on the Visitor ID Service for identity.
* **`visitorMigrationServer`**: Specified the server used during the third-party to first-party cookie migration.
* **`visitorMigrationServerSecure`**: The HTTPS equivalent of `visitorMigrationServer`.
* **`visitorNameSpace`**: Helped determine the third-party cookie domain. It is retired in favor of using the [`trackingServerSecure`](trackingserversecure.md) variable for implementations that do not use the Visitor ID Service.
