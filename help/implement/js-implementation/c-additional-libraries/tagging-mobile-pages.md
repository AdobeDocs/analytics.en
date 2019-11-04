---
description: Mobile tracking code is placed on the page in the form of a server-generated image tag.
keywords: Analytics Implementation;mobile tracking;mobile protocols;prevent caching;alt tag;default image type
seo-description: Mobile tracking code is placed on the page in the form of a server-generated image tag.
seo-title: Tagging pages for mobile protocols
solution: Analytics
title: Tagging pages for mobile protocols
topic: Developer and implementation
uuid: 5788beaf-f309-4918-a99c-a3e591668205
---

# Tagging pages for mobile protocols

Mobile tracking code is placed on the page in the form of a server-generated image tag.

 Mobile tracking code is placed on the page in the form of a server-generated image tag. Because scripting languages like JavaScript and WMLScript are not generally supported across mobile devices, the tracking beacon cannot be generated dynamically via a scripting language.

· While the mobile beacon image is actually 2x2 pixels, to ensure support for all mobile devices, you should set height and width properties to 5. For example:

```
<img sr c="https://metric.mydomain.com/b/ss/<Report_Suite_Name>/5/<random_number>?pageName=" alt="" width="5" height="5"/>
```

## Use a Random Number to Prevent Caching {#section_BF5C344A16034C439C8704632CF673A7}

While Adobe servers instruct browsers not to cache the tracking beacon, not all browsers are guaranteed to follow those instructions. To further prevent caching of the beacon, it is recommended that the Web server dynamically generate a random number in the image URL path. Doing so insures greater accuracy of reporting. The random number should be in the last section of the path, as shown here:

```js
<img src="https://rsid.112.2O7.net/b/ss/rsid/5/H.5--WAP/12345?pageName=" />.
```

## Include an ALT Tag {#section_FBD8B2FD1EA0429580C2B933DA300B07}

Some mobile browsers require that all images have alt text included in the image tag. The following shows how the ALT attribute should appear in the image tag:

```js
<img src="https://rsid.112.2O7.net/b/ss/rsid/5/H.5--WAP/12345?pageName=" alt=""/>.
```

It is important that the /5/ always appears correctly in the path. This is used by Adobe servers to identify mobile devices. If the standard /1/ is used, Adobe servers attempt to set a cookie on the mobile device.

## Change the Default Image Type {#section_2F969909010D4A64BF6E092A32ABADB7}

If the default image type is not supported on a particular device, no data is returned. To avoid this, you can force the Adobe data collection server to return a particular graphic type that the mobile device supports. The code following the report suite name specifies the image type:

* `/5/` returns the default image type.
* `/5.1/` or `/1/` always returns a GIF image.

* `/5.5/` always returns a WBMP image.

See [Identifying Visitors using Mobile Protocols](/help/implement/js-implementation/c-unique-visitors/visid-mobile.md).
