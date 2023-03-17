---
title: Packet analyzers
description: Packet analyzers let you view the data sent by your implementation to Adobe data collection servers.
keywords: packet sniffer, http status, 200, 302, charles
feature: Validation
exl-id: db077293-f72c-4933-8a30-f1e1963f332e
---
# Packet analyzers

Packet analyzers let you view the data sent by your implementation to Adobe data collection servers.

Similar to the Adobe Experience Cloud debugger, a packet monitor shows what data parameters are being passed in an image request; however, packet monitors provide added functionality:

* View custom link tracking image requests 
* View image requests using implementation methods other than JavaScript, such as hard-coded image requests or [!DNL Appmeasurement]

To view Analytics requests, filter outgoing requests using "b/ss".

In very rare cases, the debugger will report an image request although no request makes it to Adobe's [!DNL Analytics] processing servers. Using a packet monitor is a great way to be 100% sure that a specific image request is being fired successfully.

While Adobe does not provide an official packet monitor, there are a wide range of them on the internet. The following are some packet monitors others have found useful.

>[!TIP]
>
>These lists are not meant to be comprehensive, but rather information on frequently used monitors.

|  Firefox  | Internet Explorer  | Chrome  | Standalone Programs  |
|---|---|---|---|
|  [Observe Point](https://www.observepoint.com/product#plugin) (tag viewer)  | [HttpWatch](https://www.httpwatch.com/)  | [Observe Point](https://www.observepoint.com/product#plugin) (tag viewer)  | [Charles](https://www.charlesproxy.com/)  |
|  [HttpFox](https://addons.thunderbird.net/en-us/firefox/addon/httpfox/)  |  | [Chrome Developer Tools](https://code.google.com/chrome/devtools/docs/overview.html)  | [Fiddler](https://www.fiddler2.com/fiddler2/)  |
|  [Tamper Data](https://addons.mozilla.org/en-US/firefox/addon/tamper-data-for-ff-quantum/)  |  | [Firebug Lite](https://chrome.google.com/webstore/detail/firebug-lite-for-google-c/ehemiojjcpldeipjhjkepfdaohajpbdo)  | [Wireshark](https://www.wireshark.org/)  |
|  [HttpWatch](https://www.httpwatch.com/)  |  |  |  |
|  [Firebug](https://getfirebug.com/)  |  |  |  |

>[!NOTE]
>
>Adobe does NOT support or troubleshoot any issues you experience with these packet monitors. Consult the packet monitor's originating site for assistance.

## Typical HTTP response status codes

When AppMeasurement sends data to Adobe data collection servers, servers respond with a response status code.

* **200 OK**: The most common response from data collection servers. The image request was successfully received and a transparent image was returned.
* **302 FOUND**: There are a couple possible reasons to receive this response:
  * The first image request of a visitor: A redirect occurs if a user visits your site for the first time. This redirect is to obtain a visitor cookie. It does not affect data collection.
  * Integration between Comscore and Adobe: If your organization uses a Comscore/Analytics integration, each image request always results in a 302 response.
* **404 NOT FOUND**: This response means that the image request was not found, and data is not sent to Adobe data collection servers. This response is also possible when hardcoded image requests are not formatted correctly. Work with the individual or team who implemented Analytics to resolve this issue.

## NS_BINDING_ABORTED in response codes

This message occurs because the link tracking image request is designed to let the browser proceed to the next page before waiting for a response from the Adobe data collection servers.

Adobe's response to the image request is simply a blank 1x1 transparent image, which is not relevant to the content of the page. If you see a line item in your packet monitor from Adobe, either with a **[!UICONTROL 200 OK]** response or an **[!UICONTROL NS_BINDING_ABORTED]** response, the data has reached Adobe's servers. There is no need to have the page wait any longer.

Packet monitors integrated as a plug-in rarely see the full response. They tend to see the request as aborted because the full response was not received. These monitors also rarely make a distinction between whether it was the request or response that was aborted. A stand alone packet monitor typically has more detailed messages and reports the status more accurately. For example, a user may get a message in *Charles* saying "Client closed connection before receiving entire response." This means the data did reach our servers, just the browser moved on to the next page before the 1x1 pixel was received.

If an external packet monitor reports that the data collection request is aborted, rather than the response, this is a cause for concern. Adobe [!DNL Customer Care] can provide help in troubleshooting.
