---
title: Client hints
description: Learn about 
---

# Client hints overview and FAQ

Client hints are individual pieces of information about a user's device. They are provided by Chromium browsers such as Google Chrome and Microsoft Edge. For these browsers, client hints will gradually replace the User Agent as the source of device information. Adobe Analytics will update its device lookup process so that it uses client hints in addition to User Agent to determine device information.

Google divides User Agent client hints into two categories: low-entropy and high-entropy hints.

* Low-entropy hints have more generic information about devices. These hints are automatically supplied by Chromium browsers.

* High-entropy hints have more detailed information. These hints are available only by request. Both AppMeasurement and Web SDK can be configured to request high-entropy hints. By default, both libraries do **not** request high-entropy hints.

>[!NOTE]
>
>Starting in October 2022, new versions of Chromium browsers will start 'freezing' the operating system version represented in the User Agent string. This means that, over time, operating version information as represented in the User Agent will become less accurate. Operating system version is a high-entropy hint, so to maintain accuracy of operating system version in your reporting it is necessary to configure your collection library to collect these high-entropy hints. Over time other device information of the User Agent will be frozen, requiring client hints to maintain device reporting accuracy.

## Frequently asked questions

+++**How do I enable the collection of client hints?**

Low-entropy hints are automatically provided by the browser and included in Adobe's process for device information. Newer versions of AppMeasurement (starting TBD) and Web SDK (starting TBD) can be configured to collect high-entropy hints. For both libraries, collection of high-entropy hints is **disabled by default**. See here for details on how to implement this.

+++**Can I choose which high-entropy hints I collect?**

Not at this time. You can choose to collect all high-entropy hints or none.

+++**Will there be any changes to device reporting in Analytics?**

The device fields available for reporting will not change. The data captured for those field may change depending on which field and how you have configured collection for client hints.

+++**Which Analytics reporting fields are derived from the User Agent?**

* [Browser](https://experienceleague.adobe.com/docs/analytics/components/dimensions/browser.html?lang=en) 
* [Browser Type](https://experienceleague.adobe.com/docs/analytics/components/dimensions/browser-type.html?lang=en)
* [Operating System](https://experienceleague.adobe.com/docs/analytics/components/dimensions/operating-systems.html?lang=en)
* [Operating System Types](https://experienceleague.adobe.com/docs/analytics/components/dimensions/operating-system-types.html?lang=en)
* [Mobile Device and Mobile Device Type](https://experienceleague.adobe.com/docs/analytics/components/dimensions/mobile-dimensions.html?lang=en)??
* Data Feeds (Note that users must update to capture these fields. In addition, there is a dependency where we cannot expose mobile ID along with device info.)
* Analytics Source Connector (not ready)

+++**Which Analytics reporting fields are derived from values stored in high-entropy hints?**

As of September 2022, Google's published timeline for freezing User-Agent hints indicates the operating system version will stop being updated starting October 2022. Without high-entropy hints the accuracy of operating system version, included in Analytics "Operating System" dimension, will gradually degrade.

See the [timeline published by Google](https://blog.chromium.org/2021/09/user-agent-reduction-origin-trial-and-dates.html) to see the timing for freezing of the user agent.

+++**Which browsers are affected by client hints?**

Client hints only apply to Chromium browsers such as Google Chrome and Microsoft Edge. There is no change to data from other browsers or mobile apps.

+++**How will Adobe use client hints to derive device information?**

Adobe uses a third-party, Device Atlas, who will use both the client hints and user agent to derive device information.

+++**Will client hints be available in data feeds?**

Yes. Please see documentation (to follow).

+++**Will client hints be available in data sent to AEP and CJA via the Adobe Source Connector?**

We plan to include client hints in data via Adobe Source Connector in the first half of 2023.

+++**How are client hints represented in XDM?**

See the [schema documentation](https://github.com/adobe/xdm/blob/master/components/datatypes/browserdetails.schema.json#L121) in Adobe Experience Platform.

+++**Where can I learn more about client hints?**

This [Google blog post](https://web.dev/user-agent-client-hints/) is a good reference and starting point.

+++**What are the various hint fields? Which ones affect device reporting?**

The table below describes the client hints as of September 2022.

| Hint (header) | Hint | High or Low Entropy | Example | Analytics Reporting Fields |
| --- | --- | --- | --- | --- |
| Sec-CH-UA  |  Browser and significant version  | Low |  Google Chrome 84  | [Browser](https://experienceleague.adobe.com/docs/analytics/components/dimensions/browser.html?lang=en) and [Browser Type](https://experienceleague.adobe.com/docs/analytics/components/dimensions/browser-type.html?lang=en) |
| Sec-CH-UA-Mobile |  Mobile device (true or false) |  Low |  TRUE |  [Mobile Device and Mobile Device Type](https://experienceleague.adobe.com/docs/analytics/components/dimensions/mobile-dimensions.html?lang=en)?? |
| Sec-CH-UA-Platform |  Operating System/Platform |  Low  | Android |  [Operating System](https://experienceleague.adobe.com/docs/analytics/components/dimensions/operating-systems.html?lang=en) |
| Sec-CH-UA-Arch |  Architecture of the site |  High |  "arm"  |  None? |
| Sec-CH-UA-Bitness  | Sec-CH-UA-Bitness  | High  |   |  None? |
| Sec-CH-UA-Full-Version  | Complete version of the browser |  High  | "84.0.4143.2" |  None? |
| Sec-CH-UA-Full-Version-List |  ???  | High |  ??? |  None? |
| Sec-CH-UA-Model |  Device model |  High |  "Pixel 3" |  None? |
| Sec-CH-UA-Platform-Version |  Operating System/Platform version |  High |  "10" |  [Operating System](https://experienceleague.adobe.com/docs/analytics/components/dimensions/operating-systems.html?lang=en) |

+++**How do I capture high-entropy hints?**

High-entropy hints can be configured

* For AppMeasurement directly [link to flag entry in Implementation Guide]
* In the Tags Analytics Extension
* In the Web SDK.

+++**What data is being removed from the User Agent and when?** 

See the [timeline published by Google](https://blog.chromium.org/2021/09/user-agent-reduction-origin-trial-and-dates.html). This may be subject to change.

+++