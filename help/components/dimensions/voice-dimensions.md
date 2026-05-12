---
title: Voice analytics dimensions
description: Voice analytics dimensions
feature: Dimensions
exl-id: 6e1275c4-3b17-4c65-a308-d420ea1acdf6
TQID: https://experienceleague.adobe.com/OZ-lQkbS8hsv8ywUUa2BQoH40nfklRkJNd9SlEVkmEI
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
subfeature_v2:
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
    internal-label: Calculated Metrics
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
---
# Voice analytics dimensions

When you enable [!UICONTROL Voice and Chatbots] on [[!UICONTROL Application reporting]](/help/admin/tools/manage-rs/edit-settings/app-reporting.md), the following dimensions (and [metrics](../metrics/voice-metrics.md)) are created. You can use [Context data variables](/help/implement/vars/page-vars/contextdata.md) to set them to the desired string value. When enabled in report suite settings, [Processing rules](/help/admin/tools/manage-rs/edit-settings/general/processing-rules/pr-overview.md) are automatically created that map voice analytics dimensions to their associated context data variable.

| Dimension name | Description | Context data variable |
| --- | --- | --- |
| Voice Error Type | The type of error encountered. | `a.voiceerrortype` |
| Voice Language | The language that the user interacts with your voice app. | `a.voicelanguage` |
| Voice Intent | The command that the user intends to run. | `a.voiceintent` |
| Voice App Response | The response that the voice app returned to the user. | `a.voiceappresponse` |
| Voice Authentication | The authenticated state of the user when interacting with the voice app. | `a.voiceauthentication` |
| Point of Interest ID | The point of interest ID. | `a.loc.poi.id` |

{style="table-layout:auto"}
