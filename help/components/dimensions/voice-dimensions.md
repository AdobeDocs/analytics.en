---
title: Voice analytics dimensions
description: Voice analytics dimensions
feature: Dimensions
exl-id: 6e1275c4-3b17-4c65-a308-d420ea1acdf6
---
# Voice analytics dimensions

When you enable [!UICONTROL Voice and Chatbots] on [[!UICONTROL Application reporting]](/help/admin/tools/c-manage-report-suites/c-edit-report-suites/app-reporting.md), the following dimensions (and [metrics](../metrics/voice-metrics.md)) are created. You can use [Context data variables](/help/implement/vars/page-vars/contextdata.md) to set them to the desired string value. When enabled in report suite settings, [Processing rules](/help/admin/tools/c-manage-report-suites/c-edit-report-suites/general/processing-rules/pr-overview.md) are automatically created that map voice analytics dimensions to their associated context data variable.

| Dimension name | Description | Context data variable |
| --- | --- | --- |
| Voice Error Type | The type of error encountered. | `a.voiceerrortype` |
| Voice Language | The language that the user interacts with your voice app. | `a.voicelanguage` |
| Voice Intent | The command that the user intends to run. | `a.voiceintent` |
| Voice App Response | The response that the voice app returned to the user. | `a.voiceappresponse` |
| Voice Authentication | The authenticated state of the user when interacting with the voice app. | `a.voiceauthentication` |
| Point of Interest ID | The point of interest ID. | `a.loc.poi.id` |

{style="table-layout:auto"}
