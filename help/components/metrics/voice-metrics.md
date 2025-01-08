---
title: Voice analytics metrics
description: Voice analytics metrics
feature: Metrics
exl-id: 3c1b4e4e-d8d2-446f-9582-a2ce5580a8d3
---
# Voice analytics metrics

When you enable [!UICONTROL Voice and Chatbots] on [[!UICONTROL Application reporting]](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/app-reporting.md), the following metrics (and [dimensions](../dimensions/voice-dimensions.md)) are created. You can use [Context data variables](/help/implement/vars/page-vars/contextdata.md) to set them to a value of `1` (or more if applicable). When enabled in report suite settings, [Processing rules](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/c-processing-rules/processing-rules.md) are automatically created that map voice analytics metrics to their associated context data variable.

| Metric name | Description | Context data variable |
| --- | --- | --- |
| Voice Utterances | Triggers when a command is issued to a voice assistant. | `a.voiceutterances` |
| Voice End Session | Triggers when the voice app is closed. | `a.voiceendsession` |
| Voice Error | Triggers when the voice app encounters an error. | `a.voiceerror` |

{style="table-layout:auto"}
