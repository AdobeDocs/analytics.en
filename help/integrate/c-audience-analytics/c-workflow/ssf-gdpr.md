---
description: null
seo-description: null
seo-title: GDPR/ePrivacy compliance and server-side forwarding
title: GDPR/ePrivacy compliance and server-side forwarding
uuid: 1b90c567-3321-4dbd-a699-38c04e809fa4
index: y
internal: n
snippet: y
---

# GDPR/ePrivacy compliance and server-side forwarding

This section explains recent enhancements to server-side forwarding that were prompted by the [EU cookie compliance regulation](https://ec.europa.eu/ipg/basics/legal/cookies/index_en.htm), which went into effect on Sept. 30, 2017.

Server-side forwarding is used to share data from Adobe Analytics to other Experience Cloud Solutions, such as Audience Manager, in real time. When enabled, server-side forwarding also allows Analytics to push data to other Experience Cloud solutions and for those solutions to push data to Analytics during the data collection process.

Until recently, server-side forwarding did not have a way to delineate between consent and pre-consent events/hits. As of November 1, 2018, you as the data controller (Adobe Analytics customer) have the option to restrict pre-consent data to Adobe Analytics, and prevent it from being forwarded to AAM. A new implementation context variable lets you flag hits where consent has not been received. The variable, when set, prevents these hits from being sent to AAM until consent has been received.

When this new context variable, “cm.ssf=1”, exists on a hit, this hit gets flagged and does not get server-side-forwarded to AAM. Conversely, if this string does not appear on a hit, the hit gets forwarded to AAM.

Server-side forwarding is bi-directional, meaning that when it is applied to a hit and that hit gets forwarded to AAM, Audience Analytics receives segment information for that hit from AAM and sends it back to Analytics. As a result, any hits that are not server-side forwarded from Analytics to AAM will not be enriched with the list of segment IDs from AAM. Thus, there will be a subset of traffic/hits that will not get segment ID information from AAM.

## Implementation Details {#section_FFA8B66085BF469FAB5365C944FE38F7}

Depending on your implementation method, follow these steps. 

<table id="table_307D170C33DD493488BB21D65BCAA422"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Implementation method </th> 
   <th colname="col2" class="entry"> Steps </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Launch </p> </td> 
   <td colname="col2"> <p>Assuming you have the Adobe Analytics extension installed, add the following context data variable definition to the custom code editor within the Action configuration of a Rule: </p> 
    <codeblock>
      s.contextData['cm.ssf']&amp;nbsp;=&amp;nbsp;'1' 
    </codeblock> <p>Note:  Define the contextdata variable and set it to 1 if a customer does not consent to targeted marketing. Set the contextdata variable to 0 for customers who consented to targeted marketing. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>DTM </p> </td> 
   <td colname="col2"> <p>Add the context data variable definition to the Custom Page Code editor: </p> 
    <codeblock>
      s.contextData['cm.ssf']&amp;nbsp;=&amp;nbsp;'1' 
    </codeblock> <p>Note:  Define the contextdata variable and set it to 1 if a customer does not consent to targeted marketing. Set the contextdata variable to 0 for customers who consented to targeted marketing. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>AppMeasurement </p> </td> 
   <td colname="col2"> <p>Add the context data variable definition to the AppMeasurement.js file: </p> 
    <codeblock>
      s.contextData['cm.ssf']&amp;nbsp;=&amp;nbsp;'1' 
    </codeblock> <p>Note:  Define the contextdata variable and set it to 1 if a customer does not consent to targeted marketing. Set the contextdata variable to 0 for customers who consented to targeted marketing. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Reporting (Optional) {#section_6AD4028EC11C4DABA2A34469DDC99E89}

You can use Adobe Analytics to report on how much of your traffic is consent based and as a result has been server-side forwarded versus how much of your traffic isn’t consent based and has not been forwarded to AAM.

To configure this type of reporting, map the new context variable to a custom traffic variable (prop) via processing rules. To do so

1. Implement the “cm.ssf” variable (as shown above.) 
1. [Enable the prop.](traffic_var.md#concept_E3D0FEC81E1F4987B39CC467F19FFCFF) 
1. Use processing rules to map the context variable to the prop.

    1. Go to  **[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Report Suites]** , then select a report suite. 
    1. Click  **[!UICONTROL Edit Report Suite]** > **[!UICONTROL General]** > **[!UICONTROL Processing Rules]** . 
    1. Click **[!UICONTROL Add Rule.]** 
    1. Under **[!UICONTROL Always Execute]**, overwrite the value of the prop you had enabled with the context variable “cm.ssf(Context Data)”. 
    1. Click **[!UICONTROL Save]**.

