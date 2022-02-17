---
title: Mobile dimensions
description: Dimensions based on the IP address of the device.
feature: Dimensions
exl-id: fa460888-513d-4d14-93b1-33d308e0758a
---
# Mobile dimensions

*This page references properties of mobile devices accessing your website. If you want to track devices on a mobile app, see [Implement Analytics for mobile devices](/help/implement/mobile-device-sdk.md) in the Implement user guide.*

Mobile dimensions provide insight around the properties of mobile devices that visit your site. You can use these dimensions to help understand what features a mobile device supports.

## Populate these dimensions with data

These dimensions reference lookup rules that are internal to Adobe. [!UICONTROL Mobile Carrier] lookups are determined by IP address, using data we get from NetAcuity (a Digital Elements product). 
If you use an AppMeasurement library (such as through tags in Adobe Experience Platform), all mobile dimensions work out of the box.

## Mobile dimension descriptions

>[!NOTE]
>
>Dimension items labeled `"None"` are non-mobile devices. If you want a report that only includes mobile devices, drag the 'Mobile device' dimension into the segment area of the Workspace canvas.

* **Mobile audio support**: Determines file formats that the device can play. Example values include `"MP3"`, `"AAC"`, and `"MIDI Monophonic"`. Values in this dimension are not mutually exclusive; a single hit can attribute to multiple dimension items.
* **Mobile carrier**: Values for this dimension are populated by looking up 3rd-party (Digital Elements) data based on the IP addresses that Analytics captured. Example values include `"Reliance Jio"`, `"Airtel"`, `"Vodafone"`, and `"Verizon"`.
* **Mobile color depth**: The color depth of the mobile device, in bits.
* **Mobile cookie support**: Determines if the mobile device supports cookies. This report does not state if the browser accepts cookies. Dimension items include `"Supported"`, `"Not supported"`, and `"Unknown"`.
* **Mobile device**: The mobile device that the visitor uses.
* **Mobile device number**: Determines if the mobile device transmits its number. Dimension items include `"Supported"`, `"Not supported"`, and `"Unknown"`.
* **Mobile device type**: The type of mobile device. Example values include `"Mobile phone"`, `"Tablet"`, `"Media player"`, and `"Gaming console"`.
* **Mobile DRM**: The type of DRM the mobile device supports. Example values include `"DRM OMA forward"`, `"DRM OMA combined delivery"`, and `"DRM OMA separate delivery"`.
* **Mobile image support**: The types of images that a mobile devices supports. Example values include `"PNG"`, `"JPEG"`, and `"GIF 87"`. Values in this dimension are not mutually exclusive; a single hit can attribute to multiple dimension items.
* **Mobile information services**: The types of news services supported by the device. Recent devices typically do not report this information.
* **Mobile Java VM**: The versions of Java that the device supports.
* **Mobile mail decoration**: Determines if the device supports Decomail, a feature once popular on Japanese devices.
* **Mobile manufacturer**: Groups mobile devices by manufacturer. Example values include `"Apple"`, `"Samsung"`, `"Huawei"`, and `"Motorola"`.
* **Mobile max bookmark length**: The maximum number of bytes that the mobile device supports in bookmarked URLs. Recent devices typically do not have a limit.
* **Mobile max browser URL length**: The maximum number of bytes that the mobile device supports in URLs. Recent devices typically do not have a limit.
* **Mobile max email length**: The maximum number of bytes that the mobile device supports in an email. Recent devices typically do not have a limit.
* **Mobile net protocols**: The types of protocol the device supports when accessing the internet. Example values include `"EDGE"`, `"GPRS"`, `"UMTS"`, and `"LTE"`.
* **Mobile operating system (deprecated)**: Use the [Operating system](operating-systems.md) dimension instead.
* **Mobile push to talk**: Determines if the device supports PTT (Push to talk), which allows the mobile device to behave similar to a two-way radio. Recent devices typically do not report this feature.
* **Mobile screen height**: The height of the screen, in pixels. Note that iPhones always report `"480"` due to the inability to determine iPhone device version. See the section below on determining iPhone device version.
* **Mobile screen size**: The full dimensions of the mobile device in pixels. The reported screen size does not indicate the orientation of the device. Regardless of screen orientation, each device has a fixed screen resolution in the report. This size is based on research that determines which orientation is more likely. You can see sizes such as `"768x1024"` and `"1024x768"` in the same report with each size representing one or more different devices.
* **Mobile screen width**: The width of the screen, in pixels.
* **Mobile video support**: The video file formats and codecs that the mobile device supports. Several dimension items exist for different codecs of MP4 and 3GPP files. Values in this dimension are not mutually exclusive; a single hit can attribute to multiple dimension items.

## Separating iPhone by model or version

Mobile devices report their firmware version in the user agent string, not the device version. For example, a current-gen iPhone contains an identical user agent as its last generation iPhone if they are on the same firmware version. Since there is no way to determine an iPhone's device version using JavaScript, all iPhones belong in the same bucket. Mobile dimensions are strictly based on lookups that reference user agent, so you'll find that all iPhones report a mobile screen size of `320 x 480`.

If you want to collect iPhone device version, there are two ways that you can circumvent this limitation.

* **Use the iOS SDK**: The mobile SDK contains dimensions that expose the device version for use in reporting. This method is more ideal for mobile apps than websites.
* **Use other variables available through JavaScript**: Some variables, such as `screen.height` and `screen.width`, can be used to infer device version. For example, you could use the following snippet of code on your site:

  ```js
  if (navigator.userAgent.indexOf('iPhone') > -1) {
    s.eVarXX = screen.width + "x" + screen.height;
    }
  ```

  This code block first detects if the device is an iPhone. If it is, the code uses JavaScript to pull the screen resolution into an eVar. This method allows you approximately detect the device version if screen resolutions are unique.
