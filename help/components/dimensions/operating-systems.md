---
title: Operating system
description: The operating system of the visitor.
feature: Dimensions
exl-id: e3911ae0-d242-4da2-a4bc-b2f4877f9dd2
---
# Operating system

The 'Operating system' dimension shows the operating system and version that the visitor used. If you have features on your web-property that are OS-specific, this dimension helps you understand which operating systems are most common.

## Populate this dimension with data

This dimension references a lookup table internal to Adobe. The lookup value is based on the `User-Agent` HTTP header in image requests. If you use an AppMeasurement library (such as through tags in Adobe Experience Platform), this dimension works out of the box.

## Dimension items

Dimension items include operating systems that visitors use. Examples include `"Windows 10"`, `"OS X 10.15"`, and `"Android 9"`.

## Changes in labeling and definition

Below is a list of specific issues with how operating system has been represented in the User Agent and in Adobe Analytics reporting. 

### Change to naming convention for Apple operating system: 

Starting with Version 11 we will use OS X instead of Mac OS to refer to the Apple operating system.

Examples:

* MacOS version 10.15.7 (see note below about version 10.15.7 over representation in UA strings).
* OS X version 11.0.0

### Mac OS version is incorrect in the User Agent after version 10.15.7  

As of January 2023, the User Agent in all browsers shows the Mac OS version as 10.15.7, even for newer versions. This was done because including version 11 in the UA apparently caused problems with some websites. Apple also notes that including an incorrect OS version in the UA provides some privacy benefits. 

Note that client hints include the correct version in the platform version hint ("Sec-CH-UA-Platform-Version"). This is a high-entropy hint so is not automatically collected by Adobe. See the [Adobe Analytics Hints FAQ](https://experienceleague.adobe.com/docs/analytics/technotes/client-hints.html?lang=en) for details on how to collect high-entropy hints.

### Windows version is incorrect in the User Agent starting with Windows 11

As of January 2023, The User Agent in all browsers shows represents Windows 11 as Windows 10. 

Note that client hints include the correct version in the platform version hint ("Sec-CH-UA-Platform-Version"). This is a high-entropy hint so is not automatically collected by Adobe. See the [Adobe Analytics Hints FAQ](https://experienceleague.adobe.com/docs/analytics/technotes/client-hints.html?lang=en) for details on how to collect high-entropy hints.
