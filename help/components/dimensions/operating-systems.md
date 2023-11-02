---
title: Operating system
description: The operating system of the visitor.
feature: Dimensions
exl-id: e3911ae0-d242-4da2-a4bc-b2f4877f9dd2
---
# Operating system

The 'Operating system' [dimension](overview.md) shows the operating system and version that the visitor used. If you have features on your web-property that are OS-specific, this dimension helps you understand which operating systems are most common.

## Populate this dimension with data

This dimension references a lookup table internal to Adobe. The lookup value is based on the `User-Agent` HTTP header in image requests. Adobe partners with [DeviceAtlas](https://deviceatlas.com/) to maintain lookups between user agent and operating system.

* For AppMeasurement implementations, this dimension works out of the box.
* For Web SDK implementations, enable [!UICONTROL Device Lookup] when [configuring a datastream](https://experienceleague.adobe.com/docs/experience-platform/datastreams/configure.html).

## Dimension items

Dimension items include operating systems that visitors use. Examples include `"Windows 10"`, `"OS X 10.15.7"`, and `"Android 9"`.

## Tracking accurate OS versions

As the industry moves toward client hints, some operating systems versions are potentially conflated. For example, "Windows 10" and "Windows 11" can both be grouped under "Windows 10" if you don't collect high-entropy client hints. See [Client hints](/help/technotes/client-hints.md) in the Technotes guide for details.
