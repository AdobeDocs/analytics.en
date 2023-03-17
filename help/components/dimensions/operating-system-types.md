---
title: Operating system types
description: The operating system regardless of version.
feature: Dimensions
exl-id: 0afd5261-98e8-4247-865a-1b8844c53ff4
---
# Operating system types

The 'Operating system types' dimension shows the overarching OS the visitor used, regardless of specific versions. This dimension is useful to understand not just which specific operating system and version is most common, but which typical OS platform visitors use.

## Populate this dimension with data

This dimension references a lookup table internal to Adobe. The lookup value is based on the `User-Agent` HTTP header in image requests. If you use an AppMeasurement library (such as through tags in Adobe Experience Platform), this dimension works out of the box.

## Dimension items

Dimension items include the type of operating systems used. Examples include `"Microsoft Windows"`, `"Apple Macintosh"`, `"Google Android"`, and `"Apple iOS"`.
