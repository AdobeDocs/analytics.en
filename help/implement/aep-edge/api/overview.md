---
title: Implement Adobe Analytics using the Adobe Experience Platform Edge Network API
description: Use the Adobe Experience Platform Edge Network API to send data to Adobe Analytics.
exl-id: 1ede95b7-4f17-4d69-aba6-62b253b6693a
feature: Implementation Basics
role: Admin, Developer, Leader
TQID: 'https://experienceleague.adobe.com/lvnplKx6dPwmmbZWgSShGvZXD2TtUoigi-HNiKutZSg'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
    internal-label: API
  - id: eb9732ab-8232-4b21-bc4c-89de86dbe4d7
    internal-label: Integrations
subfeature_v2:
  - id: b3e5f43e-2e2f-43c0-810a-044a5f91e31a
    internal-label: Experience Platform Edge integration
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
  - id: f8a45b24-4be7-4f1b-909b-60d06b483a20
    internal-label: Leader
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: d3cdead0-685a-4489-9250-4bb709942f66
    internal-label: Data collection
---
# Implement Adobe Analytics using the Adobe Experience Platform Edge Network API

You typically use the Experience Platform Edge Network API to collect data server-side rather than client-side and when collecting data from devices like IoT devices, set-top boxes, desktop applications. Then you send that data to the Edge network and to services like Adobe Analytics.

Also consider the Edge Network API when you require sensitive data to be collected securely and authenticated across the network. See [Authentication](https://experienceleague.adobe.com/docs/experience-platform/edge-network-server-api/authentication.html) for more information.

A high-level overview of the implementation tasks:

![Adobe Analytics using the Analytics extension workflow](../../assets/edge-network-server-api-annotated.png)

<table style="width:100%">

<tr>
<th style="width:5%"></th><th style="width:60%"><b>Task</b></th><th style="width:35%"><b>More Information</b></th>
</tr>

<tr>
<td>1</td>
<td>Ensure you have <b>defined a report suite</b>.</td>
<td><a href="../../../admin/tools/manage-rs/report-suites-admin.md">Report Suite Manager</a></td>
</tr>

<tr>
<td>2</td>
<td><b>Setup schemas</b>. To standardize data collection for use across applications that leverage Adobe Experience Platform, Adobe has created the open and publicly documented standard, Experience Data Model (XDM).</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/xdm/ui/overview.html">Schemas UI overview</a></td>
</tr>

<tr>
<td>3</td>
<td><b>Configure a datastream</b>. A datastream represents the server-side configuration when using the API's from the Adobe Experience Platform Edge Network API.</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/datastreams/configure.html">Configure a datastream<a></td> 
</tr>

<tr>
<td>4</td>
<td><b>Implement and test data collection</b> using the Single event data and Batch event data collection APIs.</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/edge-network-server-api/data-collection/interactive-data-collection.html">Single-event data collection</a><br/><a href="https://experienceleague.adobe.com/docs/experience-platform/edge-network-server-api/data-collection/non-interactive-data-collection.html">Batch event data collection</a>
</tr>

<td>5</td>
<td><b>Add an Adobe Analytics service</b> to your datastream. That service controls whether and how data is sent to Adobe Analytics.</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/edge-network-server-api/interacting-other-adobe-solutions/interacting-adobe-analytics.html">Interacting with Adobe Analytics</a></td>
</tr>


</table>

See [Edge Network API documentation](https://experienceleague.adobe.com/docs/experience-platform/edge-network-server-api/overview.html) for more information.

