---
description: Packet analyzers let you view the data sent by your implementation to Adobe Data Collection Servers.
keywords: Analytics Implementation
seo-description: Packet analyzers let you view the data sent by your implementation to Adobe Data Collection Servers.
seo-title: Packet analyzers
solution: Analytics
subtopic: Debugger
title: Packet analyzers
topic: Developer and implementation
uuid: 3597c23a-1c72-46e6-909d-f861cbeef490
index: y
internal: n
snippet: y
---

# Packet analyzers

Packet analyzers let you view the data sent by your implementation to Adobe Data Collection Servers.

Simliar to the [!DNL DigitalPulse Debugger], a packet monitor shows what data parameters are being passed in an image request; however, packet monitors provide added functionality:

* View custom link tracking image requests 
* View image requests using implementation methods other than JavaScript, such as hard-coded image requests or [!DNL Appmeasurement]

To view Analytics requests, filter outgoing requests using "b/ss".

In very rare cases, the debugger will report an image request although no request makes it to Adobe's [!DNL Analytics] processing servers. Using a packet monitor is a great way to be 100% sure that a specific image request is being fired successfully.

While Adobe does not provide an official packet monitor, there are a wide range of them on the internet. The following are some packet monitors others have found useful.

>[!NOTE]
>
>These lists are not meant to be comprehensive, but rather information on frequently used monitors. If you have a packet monitor you successfully use and find useful, feel free to provide feedback using the [!UICONTROL Feedback] button on the right side of this window.

|  Firefox  | Internet Explorer  | Chrome  | Standalone Programs  |
|---|---|---|---|
|  [Observe Point](https://www.observepoint.com/product#plugin) (tag viewer)  | [HttpWatch](https://www.httpwatch.com/)  | [Observe Point](https://www.observepoint.com/product#plugin) (tag viewer)  | [Charles](https://www.charlesproxy.com/)  |
|  [HttpFox](https://addons.mozilla.org/en-US/firefox/addon/httpfox/)  |  | [Chrome Developer Tools](https://code.google.com/chrome/devtools/docs/overview.html)  | [Fiddler](https://www.fiddler2.com/fiddler2/)  |
|  [Tamper Data](https://addons.mozilla.org/en-us/firefox/addon/tamper-data/)  |  | [Firebug Lite](https://chrome.google.com/webstore/detail/bmagokdooijbeehmkpknfglimnifench)  | [Wireshark](https://www.wireshark.org/)  |
|  [HttpWatch](https://www.httpwatch.com/)  |  |  |  |
|  [Firebug](https://getfirebug.com/)  |  |  |  |

>[!NOTE]
>
>Adobe does NOT support or troubleshoot any issues you may experience with these packet monitors. Consult the packet monitor's originating site for assistance instead.

<!-- 

debugger_ns_binding.xml

 -->

This error occurs because the link tracking image request is designed to let the browser proceed to the next page before waiting for a response from the Adobe data collection servers.

Adobe's response to the image request is simply a blank 1x1 transparent image, which is not relevant to the content of the page. If you see a line item in your packet monitor from Adobe, either with a **[!UICONTROL 200 OK]** response or an **[!UICONTROL NS_BINDING_ABORTED]** response, the data has reached our servers. There is no need to have the page wait any longer.

Packet monitors integrated as a plug-in rarely see the full response. They tend to see the request as aborted because the full response was not received. These monitors also rarely make a distinction between whether it was the request or response that was aborted. A stand alone packet monitor typically has more detailed messages and reports the status more accurately. For example, a user may get a message in *Charles* saying "Client closed connection before receiving entire response." This means the data did reach our servers, just the browser moved on to the next page before the 1x1 pixel was received.

If an external packet sniffer is reporting that the data collection request is aborted, rather than the response, this is a cause for concern. Adobe [!DNL Customer Care] can provide help in troubleshooting. 
