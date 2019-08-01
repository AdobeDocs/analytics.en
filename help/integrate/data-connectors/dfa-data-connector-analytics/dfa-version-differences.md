---
description: There are currently three versions of the DFA integration, versions 1.0, 1.5, and 2.0.
keywords: DFA
seo-description: There are currently three versions of the DFA integration, versions 1.0, 1.5, and 2.0.
seo-title: Version Differences
solution: Analytics
title: Version Differences
topic: Data connectors
uuid: e0ae70f0-369d-451a-9752-02660d270660
index: y
internal: n
snippet: y
---

# Version Differences{#version-differences}

There are currently three versions of the DFA integration, versions 1.0, 1.5, and 2.0.

The following table summarizes the features in each version of the integration. 

|  Feature  | Version 1.0  | Version 1.5  | Version 2.0  |
|---|---|---|---|
|  DFA Click and Impression Nightly Metrics  | Yes  | Yes  | Yes  |
|  Click-through and View-through Tracking  | Yes  | Yes  | Yes  |
|  Integration receives data on an Advertiser level  | No  | Yes  | Yes  |
|  Integration receives data on a Floodlight Configuration level  | No  | No  | Yes  |
|  Cost Metrics  | No  | No  | Yes  |
|  Creative Metrics  | No  | No  | Yes  |
|  Query strings beyond 2k bytes  | No  | Yes  | Yes  |
|  Uses Integrate module for optimal 3rd party data collection  | No  | Yes  | Yes  |
|  Timeout and Error tracking  | No  | Yes  | Yes  |
|  No need for negotiated Client Side ID  | No  | No  | Yes  |

## About Version 1.5 {#section-b5a3e967cfa141ea8f740612336181be}

Version 1.5 of the integration introduces the Integrate module to the landing page Java Script. The Integrate module allows for fixed sized requests to the DFA ad server (ad.doubleclick.net) which overcomes the 2K request limits of the previous integration. It also introduces a configurable timeout, *`s.maxDelay`*, to continue collecting Adobe visitor data when network outages occur. Errors and timeouts can also be captured into Analytics variables.

The following illustration shows network interactions on the landing page in version 1.5.

![](assets/DFA_About_1_5.png)

In version 1.5, the Integrate module (2) requests data from the Floodlight Server (3). The Floodlight Server will redirect to the DFA ad server, which will return data about the visitor in the same way as version 1.0. It will 302 redirect (4) to a special translator service on integrate.112.2o7.net, which will turn the response structure into a JSON object. The Integrate module consumes this JSON object and passes the information along to the Adobe Tracking (5).

Moving from Version 1.0 of the integration to 1.5 involves a JavaScript change. To obtain this JavaScript, log into your Adobe Online Marketing Suite account, choose the Genesis product, click Edit on your DFA integration, and proceed through the wizard. Provided a Client Site ID has previously been assigned, once you have saved the Integration you will immediately receive the new JavaScript code via email. Once you have this code, you will also new version of the core s_code will be needed which has the Integrate module. This code can be requested from your Account Manager or Implementation Consultant.

An important feature of the new JavaScript code is that there is no implementation change necessary between version 1.5 and version 2.0.

## About Version 2.0 {#section-afd56de0c56c4489bb5ddc5798d6709a}

The latest version of the DFA integration brings data for an entire Floodlight Configuration into the integration. Previous to version 2.0, individual integrations were tied to a single DFA Advertiser. With this change, Clicks, Impression, and Cost metrics for the entire Floodlight Configuration will be included in the integrated report suite. It is also possible to track cross-site view throughs, when those two sites are inside the same Floodlight Configuration.

Media Cost metrics are also available as of version 2.0 of the integration. To enable media cost metrics for an integration, you must choose a Reports & Analytics event for Media Cost in the Genesis wizard, as well as specify what currency the metric figures are in the DFA interface.

Timeouts are expected to decrease with the 2.0 integration, since the 302 redirects have been eliminated. Eliminating these hops should decrease timeouts, and increase the amount of DFA data you can integrate.

If a Floodlight Configuration is a shared configuration in DFA, the upgrade from version 1. 5 to 2.0 causes conversion data for all shared advertisers within the Floodlight Configuration to be included in the report suite.

## Upgrading to Version 2.0 {#section-f0bf90b9a7a1434ab1540b6c0999f4c7}

The following table outlines the owners for migration to newer versions of the integration:

|  Migration  | Owner  | Tasks  |
|---|---|---|
|  Version 1.0 to 1.5  | Client  | Implement Version 1.5 JavaScript with Integrate Module  |
|  Version 1.5 to 2.0  | Client  | Client begins discussion with Google about time frames for upgrading. After approval, Google enables Advanced Ad Serving.  |

