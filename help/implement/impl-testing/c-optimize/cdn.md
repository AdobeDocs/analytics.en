---
description: Content Delivery Services or Content Distribution Networks (CDNs) such as Akamai and Speedera push Web content closer to the edge of the network, keeping frequently-requested documents close to the location where they are accessed.
keywords: Analytics Implementation
seo-description: Content Delivery Services or Content Distribution Networks (CDNs) such as Akamai and Speedera push Web content closer to the edge of the network, keeping frequently-requested documents close to the location where they are accessed.
seo-title: Content Delivery Services/Networks
solution: Analytics
subtopic: Troubleshooting
title: Content Delivery Services/Networks
topic: Developer and implementation
uuid: 6cb57c59-d0f9-4ca5-9f15-0e74e585a4a1
index: y
internal: n
snippet: y
---

# Content Delivery Services/Networks

Content Delivery Services or Content Distribution Networks (CDNs) such as Akamai and Speedera push Web content closer to the edge of the network, keeping frequently-requested documents close to the location where they are accessed.

Typically, this reduces access latency, bandwidth usage, and infrastructure cost.

Your [!DNL AppMeasurement] for JavaScript library file can be delivered via a CDN to enhance performance and delivery of the file to the site visitor. Adobe customers need to ensure they have configured their CDN services correctly. CDNs are a common reason for fluctuations in download times and should be considered the most probable cause for any changes in download times.

Tag manager stores all JavaScript on a CDN.
