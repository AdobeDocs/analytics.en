---
title: Implementing with hardcoded image requests
description: Implement Adobe Analytics using an HTML image tag (hardcoded image request)
---

# Implementing with hardcoded image requests

AppMeasurement libraries provided by Adobe compile variables present on the page, then send them as an image request to Adobe. You can bypass AppMeasurement libraries altogether and manually send an image request to Adobe. This method requires that you manually formulate the image request and query string.

This implementation method can be used on any platform that displays images from external sources. It does not rely on JavaScript at all.

> [!NOTE] While hardcoded image requests are easy to set up, they are difficult to debug, maintain, and scale across larger projects. Make sure that hardcoded image requests are the best option for you before proceeding.

## Image request syntax

The following is an example hardcoded image request using HTML:

```html
<img src="https://example.sc.omtrdc.net/b/ss/examplersid/1?AQB=1&g=http%3A%2F%2Fexample.com&pageName=Example%20hardcoded%20hit&v1=Example%20value&AQE=1"/>
```

* `https://` designates the protocol. Match the protocol used in the image request with the protocol that the rest of your site uses.
* `example.sc.omtrdc.net` is the value contained in the `trackingServer` variable.
* `/b/ss/` is included in all image requests. It is part of the file structure for images stored on Adobe data collection servers.
* `examplersid` is the report suite ID you want to send data to.
* `/1/` is the hit source. See `hit_source` under [Data column reference](../../export/analytics-data-feed/c-df-contents/datafeeds-reference.md) in the Export user guide. Controls the order that cookies and other methods use to identify visitors.
* Everything after the query string delimiter (`?`) is data that you want to include in reports. See [Data collection query parameters](../validate/query-parameters.md) for the full list of parameters you can include in an image request.

## FAQ

Learn about common questions using hardcoded image requests.

**Are query string parameters case-sensitive?**

Yes. Make sure that query string parameters exactly match, or else they are not recorded. For example, `pagename` is not a valid query string parameter, while `pageName` is.

**Can I include spaces in the query string?**

Values for each of the query string parameters are URL encoded. URL encoding converts characters that are normally illegal in URLs into legal characters. For example, a space character is converted into `%20`. Make sure that any character that is not alpha-numeric is URL encoded. Adobe automatically URL decodes values when image requests reach data collection servers.

See [HTML URL Encoding Reference](https://www.w3schools.com/tags/ref_urlencode.asp) on W3Schools for more information on how URL encoding works.

**What is the maximum number of characters a single value can have?**

Each variable has a different maximum length. Most traffic variables hold up to 100 bytes, while most conversion variables hold up to 255 bytes. When an image request reaches data collection servers, Adobe automatically truncates these values to their maximum length.
