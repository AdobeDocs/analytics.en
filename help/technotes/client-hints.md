---
title: Client hints
description: Learn about how client hints will gradually replace the User-Agent as the source of device information.
exl-id: e0a74daa-12a2-4999-9920-2636b061dcc8
---
# Client hints overview and FAQ

Client hints are individual pieces of information about a user's device. They are provided by Chromium browsers such as Google Chrome and Microsoft Edge. For these browsers, client hints will gradually replace the User-Agent as the source of device information. Adobe Analytics will update its device lookup process so that it uses client hints in addition to User-Agent to determine device information.

Google divides User-Agent client hints into two categories: low-entropy and high-entropy hints.

* **Low-entropy hints** contain more generic information about devices. These hints are automatically supplied by Chromium browsers.

* **High-entropy** hints contain more detailed information. These hints are available only by request. Both AppMeasurement and Web SDK can be configured to request high-entropy hints. By default, both libraries do **not** request high-entropy hints. 

>[!NOTE]
>
>Client hints will be incorporated into Analytics device lookup process starting February 15, 2023. Both AppMeasurement and Web SDK currently support collection of hints data but it will not be used in device lookup until mid-February. As noted below operating system version was frozen starting in October but due to a gradual rollout and the fact that many User Agents already provide a frozen OS version (see more [here](https://experienceleague.adobe.com/docs/analytics/components/dimensions/operating-systems.html?lang=en)), we estimate that this will affect <3% of Chrome Visitors.

>[!NOTE]
>
>Starting in October 2022, new versions of Chromium browsers started 'freezing' the operating system version represented in the User-Agent string. Operating system version is a high-entropy hint, so to maintain accuracy of operating system version in your reporting it is necessary to configure your collection library to collect these high-entropy hints. Over time other device information of the User-Agent will be frozen, requiring client hints to maintain device reporting accuracy.

>[!NOTE]
>
> As of January 2023, Some versions of Mac and Windows operating systems are incorrectly represented in the User Agent but correctly represented in high entropy client hints. See [Operating System](https://experienceleague.adobe.com/docs/analytics/components/dimensions/operating-systems.html?lang=en) for more information.

>[!NOTE]
>
>AAM requires high entropy hints to be collected to preserve full functionality. If you are using [server-side forwarding to AAM](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/server-side-forwarding/ssf.html) then you may want to enable collection of high entropy hints.

## Frequently asked questions

+++**Where can I learn more about client hints?**

This [Google blog post](https://web.dev/user-agent-client-hints/) is a good reference and starting point.

+++

+++**How do I enable the collection of client hints?**

Low-entropy hints are automatically provided by the browser and ingested for deriving device and browser information. Newer versions of Web SDK (starting with 2.12.0) and AppMeasurement (starting with 2.23.0) can be configured to collect high-entropy hints via their respective Tags extensions or directly via a configuration option. See directions for [Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/user-agent-client-hints.html#enabling-high-entropy-client-hints) and [AppMeaurement](https://experienceleague.adobe.com/docs/analytics/implementation/vars/config-vars/collecthighentropyuseragenthints.html).

For both libraries, collection of high-entropy hints is **disabled by default**. 

For data submitted via API, such as via [Data Insertion API](https://github.com/AdobeDocs/analytics-1.4-apis/blob/master/docs/data-insertion-api/index.md) or [Bulk Data Insertion API](https://experienceleague.adobe.com/docs/analytics/import/bulk-data-insert.html?lang=en), hints must be explicitly included in the payload. See the respective documentation for details.

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

High entropy hints are collected via JavaScript call and passed via query pararmeter

+++

+++**Will there be any changes to device reporting in Analytics?**

The device fields available for reporting will not change. The data captured for those fields may change depending on which field and how you have configured collection for client hints.

+++

+++**Which Analytics reporting fields are derived from the User-Agent?**

These fields are directly derived from the User-Agent but User-Agent may be used to help derive values for other device related fields, depending on the device details.

* [Browser](https://experienceleague.adobe.com/docs/analytics/components/dimensions/browser.html) 
* [Browser Type](https://experienceleague.adobe.com/docs/analytics/components/dimensions/browser-type.html)
* [Operating System](https://experienceleague.adobe.com/docs/analytics/components/dimensions/operating-systems.html)
* [Operating System Types](https://experienceleague.adobe.com/docs/analytics/components/dimensions/operating-system-types.html)
* [Mobile Device and Mobile Device Type](https://experienceleague.adobe.com/docs/analytics/components/dimensions/mobile-dimensions.html)

+++

+++**What portions of the User-Agent are being "frozen" and when?** 

See the [timeline published by Google](https://blog.chromium.org/2021/09/user-agent-reduction-origin-trial-and-dates.html). This may be subject to change.

+++

+++**In what ways does Analytics depend on the User Agent?**

Device information in reporting is derived from the User Agent. We have updated our processes to use both User Agent and client hints where available. 

The Fallback ID ([s_fid](https://experienceleague.adobe.com/docs/id-service/using/reference/analytics-reference/analytics-ids.html?lang=en)) is derived from the User Agent and IP Address. This ID is only used if a cookie cannot be set so is not widely used 

+++

+++**Which Analytics reporting fields are derived from values stored in high-entropy hints?**

This will change over time as Google 'freezes' more parts of the User Agent. The first field to be directly impacted is "Operating System" which includes the operating system version According to Google's published timeline for "freezing" User-Agent hints, operating system version will be frozen starting late October 2022 with Chromium version 107. At that point the operating system version in the User Agent will be inaccurate in some cases. 

Refer to the [timeline published by Google](https://blog.chromium.org/2021/09/user-agent-reduction-origin-trial-and-dates.html) to see the timing for freezing of other portions of the User-Agent. 

+++

+++**How will Adobe use client hints to derive device information?**

Adobe uses a third party, Device Atlas, who will use both client hints and the User-Agent to derive device information.

+++

+++**Which browsers are affected by client hints?**

Client hints apply only to Chromium browsers such as Google Chrome and Microsoft Edge. There is no change to data from other browsers or mobile apps.

+++

+++**Are client hints supported over insecure connections?**

No. Client hints can only be collected through a secure HTTP connection, such as HTTPS.

+++

+++**How do I include client hint data when using API submission?**

See documentation for including these via [Bulk Data Insertion API](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/bulk-data-insertion/file-format/).

+++

+++**Will client hints be available in data sent to AEP and CJA via the Adobe Source Connector?**

Adobe plans to include client hints in data via Adobe Source Connector in the first half of 2023.

+++

+++**How are client hints represented in XDM?**

See the [schema documentation](https://github.com/adobe/xdm/blob/master/components/datatypes/browserdetails.schema.json#L121) in Adobe Experience Platform.

+++

+++**Will AAM server-side forwarding support client hints?** 

Yes. Client hints will be included in the data forwarded to AAM. Note that AAM requires high-entropy hints to be collected to preserve full functionality. If you are using [server-side forwarding to AAM](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/server-side-forwarding/ssf.html) then you may want to enable collection of high-entropy hints.

+++
