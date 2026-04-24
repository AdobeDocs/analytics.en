---
title: Mobile lookup dimensions
description: Dimensions based on the IP address and user agent of the device.
feature: Dimensions
exl-id: fa460888-513d-4d14-93b1-33d308e0758a
TQID: https://experienceleague.adobe.com/X80x0MIx5gd16J20VU37fNSExDO2NSXPrHR8EKqsMqw
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
    internal-label: Implementations
subfeature_v2:
  - id: c77ba355-6681-41fe-b719-563d3f507fdb
    internal-label: Mobile SDK
  - id: d2311670-43bd-4c2e-bc98-1da2aaba9cef
    internal-label: Appmeasurement implementation
  - id: e7d92df1-c5ba-4e93-85df-f83171b889be
    internal-label: Variables
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
    internal-label: Calculated Metrics
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
    internal-label: Measurement
---
# Mobile lookup dimensions

*This page references the properties of mobile devices accessing your website. See [Mobile lifecycle dimensions](lifecycle-dimensions.md) or [Mobile lifecycle metrics](../metrics/lifecycle-metrics.md) for tracking within a mobile app.*

Mobile lookup [dimensions](overview.md) provide insight around the properties of mobile devices that visit your site. These properties are based on the user agent and IP address of the hit. You can use these dimensions to help understand what features that a mobile device supports.

## Populate these dimensions with data

These dimensions reference lookup rules that are internal to Adobe.

* For the [!UICONTROL Mobile Carrier] dimension, Adobe partners with [Digital Element](https://www.digitalelement.com/) using NetAcuity to maintain lookups between IP address and mobile carrier.
* For all other mobile dimensions, Adobe partners with [DeviceAtlas](https://deviceatlas.com/) to maintain lookups between user agent and each respective mobile dimension.

Availability of these dimensions depends on implementation type:

* For AppMeasurement implementations, these dimensions work out of the box.
* For Web SDK implementations, enable [!UICONTROL Geo Lookup] (for Mobile Carrier) or [!UICONTROL Device Lookup] (for all other dimensions) when [configuring a datastream](https://experienceleague.adobe.com/docs/experience-platform/datastreams/configure.html).

## Mobile dimension descriptions

>[!NOTE]
>
>Dimension items labeled `"None"` are non-mobile devices. If you want a report that only includes mobile devices, drag the 'Mobile device' dimension into the segment area of the Workspace canvas.

* **[!UICONTROL Mobile audio support]**: Determines file formats that the device can play. Example values include `"MP3"`, `"AAC"`, and `"MIDI Monophonic"`. Values in this dimension are not mutually exclusive; a single hit can attribute to multiple dimension items.
* **[!UICONTROL Mobile carrier]**: The phone or data provider for the device. Example values include `"Reliance Jio"`, `"Airtel"`, `"Vodafone"`, and `"Verizon"`.
* **[!UICONTROL Mobile color depth]**: The color depth of the mobile device, in bits.
* **[!UICONTROL Mobile cookie support]**: Determines if the mobile device supports cookies. This dimension does not state if the browser accepts cookies. Dimension items include `"Supported"`, `"Not supported"`, and `"Unknown"`.
* **[!UICONTROL Mobile device]**: The mobile device that the visitor uses.
* **[!UICONTROL Mobile device number]**: Determines if the mobile device transmits its number. This dimension does not provide the mobile number itself. Dimension items include `"Supported"`, `"Not supported"`, and `"Unknown"`.
* **[!UICONTROL Mobile device type]**: The type of mobile device. Example values include `"Mobile phone"`, `"Tablet"`, `"Media player"`, and `"Gaming console"`.
* **[!UICONTROL Mobile DRM]**: The type of DRM that the mobile device supports. Example values include `"DRM OMA forward"`, `"DRM OMA combined delivery"`, and `"DRM OMA separate delivery"`.
* **[!UICONTROL Mobile image support]**: The types of images that the mobile device supports. Example values include `"PNG"`, `"JPEG"`, and `"GIF 87"`. Values in this dimension are not mutually exclusive; a single hit can attribute to multiple dimension items.
* **[!UICONTROL Mobile information services]**: The types of news services supported by the device. Modern devices typically do not report this information.
* **[!UICONTROL Mobile Java VM]**: The versions of Java that the device supports.
* **[!UICONTROL Mobile mail decoration]**: Determines if the device supports [Decome](https://en.wikipedia.org/wiki/Decome), a feature once popular on Japanese devices.
* **[!UICONTROL Mobile manufacturer]**: Classifies mobile devices by manufacturer. Example values include `"Apple"`, `"Samsung"`, `"Huawei"`, and `"Motorola"`. 
* **[!UICONTROL Mobile max bookmark length]**: The maximum number of bytes that the mobile device supports in bookmarked URLs. Modern devices typically do not have a limit.
* **[!UICONTROL Mobile max browser URL length]**: The maximum number of bytes that the mobile device supports in URLs. Modern devices typically do not have a limit.
* **[!UICONTROL Mobile max email length]**: The maximum number of bytes that the mobile device supports in an email. Modern devices typically do not have a limit.
* **[!UICONTROL Mobile net protocols]**: The types of protocol the device supports when accessing the internet. Example values include `"EDGE"`, `"GPRS"`, `"UMTS"`, and `"LTE"`.
* **[!UICONTROL Mobile operating system (deprecated)]**: Use the [Operating system](operating-systems.md) dimension instead.
* **[!UICONTROL Mobile push to talk]**: Determines if the device supports PTT (Push to talk), which allows the mobile device to behave similar to a two-way radio. Modern devices typically do not report this feature.
* **[!UICONTROL Mobile screen height]**: The height of the screen, in pixels. iPhones always report `"480"` due to the inability to determine iPhone device version. See the section below on determining the iPhone device version.
* **[!UICONTROL Mobile screen size]**: The full dimensions of the mobile device in pixels. The reported screen size does not indicate the orientation of the device. Regardless of screen orientation, each device has a fixed screen resolution in the report. This size is based on research that determines which orientation is more likely. You can see sizes such as `"768x1024"` and `"1024x768"` in the same report with each size representing one or more different devices.
* **[!UICONTROL Mobile screen width]**: The width of the screen, in pixels.
* **[!UICONTROL Mobile video support]**: The video file formats and codecs that the mobile device supports. Several dimension items exist for different codecs of MP4 and 3GPP files. Values in this dimension are not mutually exclusive; a single hit can attribute to multiple dimension items.

## Separating iPhone by model or version

Mobile devices report their firmware version in the user agent string, not the device version. For example, a current-gen iPhone contains an identical user agent as its last generation iPhone if they are on the same firmware version. Since there is no way to determine an iPhone's device version using JavaScript, all iPhones belong in the same bucket. Mobile dimensions are strictly based on lookups that reference user agent, resulting in all iPhones displaying a mobile screen size of `320 x 480`.

If you want to collect the iPhone device version, there are two ways that you can circumvent this limitation.

* **Use the Mobile SDK**: The Mobile SDK contains dimensions that expose the device version for use in reporting. This method is more ideal for mobile apps than websites.
* **Use other variables available through JavaScript**: Some variables, such as `screen.height` and `screen.width`, can be used to infer device version. For example, you could use the following snippet of code on your site:

  ```js
  if (navigator.userAgent.indexOf('iPhone') > -1) {
    s.eVarXX = screen.width + "x" + screen.height;
    }
  ```

  This code block first detects if the device is an iPhone. If it is, the code uses JavaScript to pull the screen resolution into an eVar. This method allows you to approximately detect the device version if screen resolutions are unique.
