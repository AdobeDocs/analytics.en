---
title: Implementing with hardcoded image requests
description: Implement Adobe Analytics using an HTML image tag (hardcoded image request)
exl-id: 84247daf-c94b-456c-9824-6d4a0b3e6065
---
# Implementing with hardcoded image requests

AppMeasurement libraries provided by Adobe compile variables present on the page, then send them as an image request to Adobe. You can bypass AppMeasurement libraries altogether and manually send an image request to Adobe. This method requires that you manually formulate the image request and query string.

This implementation method can be used on any platform that displays images from external sources. It does not rely on JavaScript at all.

>[!NOTE]
>
>While hardcoded image requests are easy to set up, they are difficult to debug, maintain, and scale across larger projects. Make sure that hardcoded image requests are the best option for you before proceeding.

## Image request syntax

The following is an example hardcoded image request using HTML:

```html
<img src="https://example.data.adobedc.net/b/ss/examplersid/1/s234234238479?AQB=1&g=http%3A%2F%2Fexample.com&pageName=Example%20hardcoded%20hit&v1=Example%20value&AQE=1"/>
```

* `https://` designates the protocol. Match the protocol used in the image request with the protocol that the rest of your site uses.
* `example.data.adobedc.net` is the value contained in the [`trackingServer`](/help/implement/vars/config-vars/trackingserver.md) variable.
* `/b/ss/` is included in all image requests. It is part of the file structure for images stored on Adobe data collection servers.
* `examplersid` is the report suite ID you want to send data to. For multiple report suites, separate the IDs with commas and no spaces (such as `examplersid1,examplersid2` and so on).
* `/1/` is the hit source. See `hit_source` under [Data column reference](../../export/analytics-data-feed/c-df-contents/datafeeds-reference.md) in the Export user guide. Controls the order that cookies and other methods use to identify visitors.
* `/s234234238479` (`"s"` + a random number) prevents the browser from caching the image request.
* Everything after the query string delimiter (`?`) is data that you want to include in reports. See [Data collection query parameters](../validate/query-parameters.md) for the full list of parameters you can include in an image request.

## Hardcoded image requests in Microsoft Outlook

Since most emails are HTML-based, it is possible to track emails opened and send that data to Adobe Analytics. If your organization opts to use this method, note the following:

* Every email render can increment a billable server call.
* Only email clients that support HTML and allow images are tracked. Some email clients, such as Microsoft Outlook, block external images by default. These emails are not tracked until the recipient opts to download external images.

To compose an Outlook email that includes an image request:

1. Open an HTML editor. If an HTML editor is not available, a plain text editor also works.
2. In a new HTML file, insert a hardcoded image request `<img>` tag wrapped in a `<body>` tag.
3. Save the HTML file.
4. Open Microsoft Outlook and compose an email.
5. Go to the Insert tab and click **Attach File**. Select your image request HTML file.
6. Click the pop-up menu next to Insert and select **Insert as Text**. If you click the Insert button without the pop-up menu, the HTML file becomes an attachment, which does not work.

Your email does not appear to change, as the image request is a 1x1 transparent pixel. If you want to see the image request for testing purposes, modify the HTML file to include a border, additional text, or other content.

## FAQ

Learn about common questions using hardcoded image requests.

### Are query string parameters case-sensitive?

Yes. Make sure that query string parameters exactly match, or else they are not recorded. For example, `pagename` is not a valid query string parameter, while `pageName` is.

### Can I include spaces in the query string?

Values for each of the query string parameters are URL encoded. URL encoding converts characters that are normally illegal in URLs into legal characters. For example, a space character is converted into `%20`. Make sure that any character that is not alpha-numeric is URL encoded. Adobe automatically URL decodes values when image requests reach data collection servers.

See [HTML URL Encoding Reference](https://www.w3schools.com/tags/ref_urlencode.asp) on W3Schools for more information on how URL encoding works.

### What is the maximum number of characters a single value can have?

Each variable has a different maximum length. Most traffic variables hold up to 100 bytes, while most conversion variables hold up to 255 bytes. When an image request reaches data collection servers, Adobe automatically truncates these values to their maximum length.
