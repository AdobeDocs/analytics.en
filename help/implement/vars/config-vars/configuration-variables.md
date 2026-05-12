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

1. Log in to [Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) using your AdobeID credentials.
1. Click the desired tag property.
1. Click the [!UICONTROL Extensions] tab, then Click [!UICONTROL Configure] under the extension.

In JavaScript implementations using `AppMeasurement.js`, configuration variables are typically set at the top of the JS file.

>[!IMPORTANT]
>
>Make sure that all configuration variables are set before calling a tracking method ([`t()`](../functions/t-method.md) or [`tl()`](../functions/tl-method.md)). Avoid setting configuration variables in the [`doPlugins()`](../functions/doplugins.md) function.
