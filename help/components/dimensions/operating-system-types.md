---
title: Operating system types
description: The operating system regardless of version.
feature: Dimensions
exl-id: 0afd5261-98e8-4247-865a-1b8844c53ff4
---
# Operating system types

The 'Operating system types' [dimension](overview.md) shows the overarching OS the visitor used, regardless of specific versions. This dimension is useful to understand not just which specific operating system and version is most common, but which typical OS platform visitors use.

## Populate this dimension with data

This dimension references a lookup table internal to Adobe. The lookup value is based on the `User-Agent` HTTP header in image requests. Adobe partners with [DeviceAtlas](https://deviceatlas.com/) to maintain lookups between user agent and operating system type.

* For AppMeasurement implementations, this dimension works out of the box.
* For Web SDK implementations, enable [!UICONTROL Device Lookup] when [configuring a datastream](https://experienceleague.adobe.com/docs/experience-platform/datastreams/configure.html).

## Dimension items

Dimension items include the type of operating systems used. Examples include `"Microsoft Windows"`, `"Apple Macintosh"`, `"Google Android"`, and `"Apple iOS"`.
