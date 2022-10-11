---
title: Client hints
description: Learn about how client hints will gradually replace the User-Agent as the source of device information.
---

# Client hints overview and FAQ

Client hints are individual pieces of information about a user's device. They are provided by Chromium browsers such as Google Chrome and Microsoft Edge. For these browsers, client hints will gradually replace the User-Agent as the source of device information. Adobe Analytics will update its device lookup process so that it uses client hints in addition to User-Agent to determine device information.

Google divides User-Agent client hints into two categories: low-entropy and high-entropy hints.

* **Low-entropy hints** contain more generic information about devices. These hints are automatically supplied by Chromium browsers.

* **High-entropy** hints contain more detailed information. These hints are available only by request. Both AppMeasurement and Web SDK [can be configured](/help/implement/vars/config-vars/collecthighentropyuseragenthints.md) to request high-entropy hints. By default, both libraries do **not** request high-entropy hints.

>[!NOTE]
>
>Starting in October 2022, new versions of Chromium browsers will start 'freezing' the operating system version represented in the User-Agent string. Operating system version is a high-entropy hint, so to maintain accuracy of operating system version in your reporting it is necessary to configure your collection library to collect these high-entropy hints. Over time other device information of the User-Agent will be frozen, requiring client hints to maintain device reporting accuracy.

>[!NOTE]
>
>AAM requires high entropy hints to be collected to preserve full functionality. If you are using [server-side forwarding to AAM](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/server-side-forwarding/ssf.html) then you may want to enable collection of high entropy hints.

## Frequently asked questions

+++**Where can I learn more about client hints?**

This [Google blog post](https://web.dev/user-agent-client-hints/) is a good reference and starting point.

+++

+++**How do I enable the collection of client hints?**

Low-entropy hints are automatically provided by the browser and included in Adobe's process for deriving device and browser information. Newer versions of AppMeasurement (starting with 2.23.0) and Web SDK (starting with 2.12.0) can be configured to collect high-entropy hints. For both libraries, collection of high-entropy hints is **disabled by default**. 

+++

+++**How do I capture high-entropy hints?**

High-entropy hints can be configured with the Web SDK and AppMeasurement libraries via their respective Tags extensions or directly with the collectHighEntropyUserAgentHints flag.

+++

+++**Can I choose which high-entropy hints I collect?**

Not at this time. You can choose to collect all high-entropy hints or none.

+++

+++**What are the various client hints values?**

The table below describes the client hints as of October 2022.

| Hint | Description | High or Low Entropy | Example | 
| --- | --- | --- | --- | 
| Sec-CH-UA  |  Browser and significant version  | Low |  "Google Chrome 84" |
| Sec-CH-UA-Mobile |  Mobile device (true or false) |  Low |  TRUE |  
| Sec-CH-UA-Platform |  Operating System/Platform |  Low  | "Android" | 
| Sec-CH-UA-Arch |  Architecture of the site |  High |  "arm"  |  
| Sec-CH-UA-Bitness  | Architecture bitnes  | High  | "64"  |  
| Sec-CH-UA-Full-Version  | Complete version of the browser |  High  | "84.0.4143.2" |  
| Sec-CH-UA-Full-Version-List |  List of brands with their version | High | "Not A;Brand";v="99", "Chromium";v="98", "Google Chrome";v="98"  |  
| Sec-CH-UA-Model |  Device model |  High |  "Pixel 3" |  
| Sec-CH-UA-Platform-Version |  Operating System/Platform version |  High |  "10" |  

+++

+++**Will there be any changes to device reporting in Analytics?**

The device fields available for reporting will not change. The data captured for those fields may change depending on which field and how you have configured collection for client hints.

+++

+++**Which Analytics reporting fields are derived from the User-Agent?**

These fields are directly derived from the User-Agent but User-Agent may be used to help derive values for other device related fields, depending on the device details.

* [Browser](https://experienceleague.adobe.com/docs/analytics/components/dimensions/browser.html?lang=en) 
* [Browser Type](https://experienceleague.adobe.com/docs/analytics/components/dimensions/browser-type.html?lang=en)
* [Operating System](https://experienceleague.adobe.com/docs/analytics/components/dimensions/operating-systems.html?lang=en)
* [Operating System Types](https://experienceleague.adobe.com/docs/analytics/components/dimensions/operating-system-types.html?lang=en)
* [Mobile Device and Mobile Device Type](https://experienceleague.adobe.com/docs/analytics/components/dimensions/mobile-dimensions.html?lang=en)

+++

+++**Which Analytics reporting fields are derived from values stored in high-entropy hints?**

This will change over time as Google 'freezes' more parts of the User Agent. The first field to be directly impacted is "Operating System" which includes the operating system version According to Google's published timeline for "freezing" User-Agent hints, operating system version will be frozen starting late October 2022 with Chromium version 107. At that point the operating system version in the User Agent will be inaccurate in some cases. 

Refer to the [timeline published by Google](https://blog.chromium.org/2021/09/user-agent-reduction-origin-trial-and-dates.html) to see the timing for freezing of other portions of the User-Agent. 

+++

+++**How will Adobe use client hints to derive device information?**

Adobe uses a third-party, Device Atlas, who will use both the client hints and User-Agent to derive device information.

+++

+++**Which browsers are affected by client hints?**

Client hints apply only to Chromium browsers such as Google Chrome and Microsoft Edge. There is no change to data from other browsers or mobile apps.

+++

+++**Are client hints supported over insecure connections?**

No. Client hints can only be collected through a secure HTTP connection, such as HTTPS.

+++

+++**Will client hints be available in data sent to AEP and CJA via the Adobe Source Connector?**

Adobe plans to include client hints in data via Adobe Source Connector in the first half of 2023.

+++

+++**How are client hints represented in XDM?**

See the [schema documentation](https://github.com/adobe/xdm/blob/master/components/datatypes/browserdetails.schema.json#L121) in Adobe Experience Platform.

+++

+++**What portions of the User-Agent are being "frozen" and when?** 

See the [timeline published by Google](https://blog.chromium.org/2021/09/user-agent-reduction-origin-trial-and-dates.html). This may be subject to change.

+++

+++**Will AAM server-side forwarding support client hints?** 

Yes. Client hints will be included in the data forwarded to AAM. Note that AAM requires high-entropy hints to be collected to preserve full functionality. If you are using [server-side forwarding to AAM](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/server-side-forwarding/ssf.html) then you may want to enable collection of high-entropy hints.

+++

