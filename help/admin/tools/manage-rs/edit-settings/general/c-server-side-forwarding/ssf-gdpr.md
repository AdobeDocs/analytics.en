---
description: Explains enhancements to server-side forwarding that were prompted by the EU cookie compliance regulation.
title: GDPR/ePrivacy compliance and server-side forwarding
feature: Report Suite Settings
exl-id: 54e43a16-8f15-4ee8-9aa2-579af30be2c9
role: Admin
TQID: 'https://experienceleague.adobe.com/MH--f5MxzLFOkDV8B-JzqMULLbY1ota6efoJ8T1ne58'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b8734a57-d5fb-44a8-8ee1-65225cecaeae
    internal-label: Data configuration and collection
  - id: ff9b434a-2221-4df7-81d1-5bcbf5f80bce
    internal-label: Admin Tools
subfeature_v2:
  - id: c354699e-6555-4397-8706-1a9a89984069
    internal-label: Server side forwarding
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
    internal-label: Measurement
  - id: d3cdead0-685a-4489-9250-4bb709942f66
    internal-label: Data collection
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
    internal-label: Administration
  - id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
    internal-label: Privacy
---
# GDPR/ePrivacy compliance and server-side forwarding

This section explains enhancements to server-side forwarding that were prompted by the [EU cookie compliance regulation](https://wikis.ec.europa.eu/display/WEBGUIDE/04.+Cookies+and+similar+technologies), which went into effect on Sept. 30, 2017.

Server-side forwarding is used to share data from Adobe Analytics to other CX Enterprise solutions, such as Audience Manager, in real time. When enabled, server-side forwarding also allows Analytics to push data to other CX Enterprise solutions and for those solutions to push data to Analytics during the data collection process.

Previously, server-side forwarding did not have a way to delineate between consent and pre-consent events/hits. As of November 1, 2018, you as the data controller (Adobe Analytics customer) have the option to restrict pre-consent data to Adobe Analytics, and prevent it from being forwarded to Adobe Audience Manager. A new implementation context variable lets you flag hits where consent has not been received. The variable, when set, prevents these hits from being sent to Adobe Audience Manager until consent has been received.

When this new context variable, `cm.ssf=1`, exists on a hit, this hit gets flagged and does not get server-side-forwarded to Adobe Audience Manager. Conversely, if this string does not appear on a hit, the hit gets forwarded to Adobe Audience Manager.

Server-side forwarding is bi-directional, meaning that when it is applied to a hit and that hit gets forwarded to Adobe Audience Manager, Audience Analytics receives segment information for that hit from Adobe Audience Manager and sends it back to Analytics. As a result, any hits that are not server-side forwarded from Analytics to Adobe Audience Manager will not be enriched with the list of segment IDs from Adobe Audience Manager. Thus, there will be a subset of traffic/hits that will not get segment ID information from Adobe Audience Manager.

## Implementation Details {#section_FFA8B66085BF469FAB5365C944FE38F7}

Depending on your implementation method, follow these steps.

|Implementation method|Steps|
|--- |--- |
| Tags in Adobe Experience Platform | Assuming that you have the Adobe Analytics extension installed, add the following context data variable definition to the custom code editor within the Action configuration of a Rule: <br/>`s.contextData['cm.ssf'] = '1'` <br/>Note:  Define the contextdata variable and set it to 1 if a customer does not consent to targeted marketing. Set the `contextdata` variable to *0* for customers who consented to targeted marketing.|
| AppMeasurement | Add the context data variable definition to the AppMeasurement.js file:  <br/>`s.contextData['cm.ssf'] = '1'` <br/>Note:  Define the contextdata variable and set it to 1 if a customer does not consent to targeted marketing. Set the contextdata variable to 0 for customers who consented to targeted marketing. |

## Reporting (Optional) {#section_6AD4028EC11C4DABA2A34469DDC99E89}

You can use Adobe Analytics to report on how much of your traffic is consent based and as a result has been server-side forwarded versus how much of your traffic isn't consent based and has not been forwarded to Adobe Audience Manager.

To configure this type of reporting, map the new context variable to a custom traffic variable (prop) via processing rules. To do so

1. Implement the "cm.ssf" variable (as shown above.) 
1. [Enable the prop.](/help/admin/tools/manage-rs/edit-settings/c-traffic-variables/traffic-var.md) 
1. Use processing rules to map the context variable to the prop.

    1. Go to  **[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Report Suites]** , then select a report suite.
    1. Click  **[!UICONTROL Edit Report Suite]** > **[!UICONTROL General]** > **[!UICONTROL Processing Rules]** .
    1. Click **[!UICONTROL Add Rule.]** 
    1. Under **[!UICONTROL Always Execute]**, overwrite the value of the prop you had enabled with the context variable "cm.ssf(Context Data)".
    1. Click **[!UICONTROL Save]**.
