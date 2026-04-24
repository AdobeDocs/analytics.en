---
title: Voice analytics metrics
description: Voice analytics metrics
feature: Metrics
exl-id: 3c1b4e4e-d8d2-446f-9582-a2ce5580a8d3
TQID: https://experienceleague.adobe.com/snDtqM3TiX--cjPjKj8cGkaFxMIxRprvD4ia9OnBXJk
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
# Voice analytics metrics

When you enable [!UICONTROL Voice and Chatbots] on [[!UICONTROL Application reporting]](/help/admin/tools/manage-rs/edit-settings/app-reporting.md), the following metrics (and [dimensions](../dimensions/voice-dimensions.md)) are created. You can use [Context data variables](/help/implement/vars/page-vars/contextdata.md) to set them to a value of `1` (or more if applicable). When enabled in report suite settings, [Processing rules](/help/admin/tools/manage-rs/edit-settings/general/processing-rules/pr-overview.md) are automatically created that map voice analytics metrics to their associated context data variable.

| Metric name | Description | Context data variable |
| --- | --- | --- |
| Voice Utterances | Triggers when a command is issued to a voice assistant. | `a.voiceutterances` |
| Voice End Session | Triggers when the voice app is closed. | `a.voiceendsession` |
| Voice Error | Triggers when the voice app encounters an error. | `a.voiceerror` |

{style="table-layout:auto"}
