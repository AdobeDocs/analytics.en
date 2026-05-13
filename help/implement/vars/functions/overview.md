---
title: Functions and methods
description: Learn how you can use the functions and methods that Adobe offers in your implementation.
feature: Appmeasurement Implementation
exl-id: 9ef5bd92-fae1-4fe4-90ea-c735e8ff4b9c
role: Admin, Developer
TQID: https://experienceleague.adobe.com/dKPvTPeRa7-SIFyIDU-7Mlob-3jsrfvhWmKeAveHGEc
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
    internal-label: Implementations
subfeature_v2:
  - id: c069c44e-5426-4c1a-accc-8028662f2fde
    internal-label: Functions
  - id: c8add8f2-4250-4fd9-9cde-9707036c567d
    internal-label: Methods
  - id: e7d92df1-c5ba-4e93-85df-f83171b889be
    internal-label: Variables
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
    internal-label: Measurement
---
# Functions and methods

Adobe offers several functions and methods that you can use in your implementation. When you reference these functions or methods, they perform common tasks with a single line of code.

Some of these single lines of code belong to the following categories:

* **Tracking calls**: The most common methods, and vital in many implementations. They include the [`t()`](t-method.md) and [`tl()`](tl-method.md) methods.
* **AppMeasurement utilities**: In previous versions of AppMeasurement, implementations had to write their own code to perform these tasks. Adobe provides these utility methods to streamline these common tasks. AppMeasurement utilities include [`Util.cookieRead()`](util-cookieread.md), [`Util.cookieWrite()`](util-cookiewrite.md), and [`Util.getQueryParam()`](util-getqueryparam.md).
* **Register functions**: You can write your own functions and have AppMeasurement automatically execute them before or after sending a tracking call to Adobe. Variables that fall under this category are [`doPlugins()`](doplugins.md), [`registerPreTrackCallback()`](registerpretrackcallback.md), and [`registerPostTrackCallback()`](registerposttrackcallback.md).
