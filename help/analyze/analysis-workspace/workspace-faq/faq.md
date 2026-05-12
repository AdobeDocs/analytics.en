---
description: Get answers on common questions about Analysis Workspace.
title: Frequently Asked Questions
feature: Workspace Basics
role: User, Admin
exl-id: cf7a9a73-bcbe-4bf5-b5dc-913199ab229c
TQID: https://experienceleague.adobe.com/Cp7KvN1Y7Mxr4iGWNF08TYBzJWqhVWVSHApX0989lZ4
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
    internal-label: Analysis Workspace
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
    internal-label: Implementations
  - id: f73667dc-d296-4875-8975-ac3fdc3adc42
    internal-label: Dashboards
subfeature_v2:
  - id: b0a1f9d5-5795-42a3-a6d0-bd0e2748fd06
    internal-label: Components
  - id: c069c44e-5426-4c1a-accc-8028662f2fde
    internal-label: Functions
  - id: ef60b66e-5984-4336-ba72-6d978b1b6f87
    internal-label: Report suites
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
  - id: d3cdead0-685a-4489-9250-4bb709942f66
    internal-label: Data collection
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
    internal-label: Administration
---
# Frequently asked questions

+++What are the prerequisites for using Analysis Workspace?
[Send data to Adobe Analytics using the Adobe Analytics extension](/help/implement/launch/validate-publish-prod.md): Using Analysis Workspace requires a working implementation. Make sure that your organization sends data to Adobe before using the tool. Other implementations, such as legacy manual implementations, can work as well.
+++

+++What are the Administration and access requirements for Analysis Workspace?
See [Administration Requirements](/help/analyze/analysis-workspace/workspace-faq/frequently-asked-questions-analysis-workspace.md).
+++

+++Will using Analysis Workspace affect data collection?
Since Analysis Workspace is a reporting tool, it has no impact on data collection. There are no repercussions to indiscriminately dragging components into a project to see what works. Drag different combinations of dimensions and metrics into your workspace project to see what is available to you. If you accidentally drag an invalid component to your workspace project or would like to go back a step, press ctrl+Z (Windows) or cmd+Z (Mac) to undo the last action made. You can also start with a clean slate by clicking **[!UICONTROL Project]** > **[!UICONTROL New]** in the upper left menu.
+++

+++How many report suites can be displayed in an Analysis Workspace project?
You can now create projects in Analysis Workspace with data from more [multiple report suites](/help/analyze/analysis-workspace/build-workspace-project/multiple-report-suites.md).
+++

+++How do you implement Analysis Workspace?
No special implementation is required. Analysis Workspace is available to all companies with Analytics Standard or Premium. However, standard permissions to content (such as report suites and project components) apply, and for curating and sharing projects. See [Administration and Access Requirements](/help/analyze/analysis-workspace/workspace-faq/frequently-asked-questions-analysis-workspace.md).
+++

+++Can I use Analysis Workspace for Data Warehouse?
Analysis Workspace is not recommended for bulk data export. It is a visualization workspace creating dashboard-like analysis projects.
+++

+++How can I optimize performance of Analysis Workspace?

See [Optimizing Performance](/help/analyze/analysis-workspace/workspace-faq/optimizing-performance.md).

+++

+++How does data get into your Analysis Workspace project?

See ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Data into Analysis Workspace](https://experienceleague.adobe.com/en/docs/analytics-learn/tutorials/analysis-workspace/analysis-workspace-basics/understanding-how-data-gets-into-your-analysis-workspace-project){target="_blank"} for a demo video.

+++

+++How can I track Workspace usage?

See ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Log tracking](https://experienceleague.adobe.com/en/docs/analytics-learn/tutorials/administration/logs/usage-log-tracking-for-analysis-workspace){target="_blank"} for a demo video.

+++

+++When I drag a metric over, it says 'Invalid data'. How do I resolve this issue?

Invalid data means that Adobe cannot return data using the combination of dimensions and metrics used in the report. For example, two metrics stacked on top of each other cannot be returned as data, as there is no way to display two metrics that way. Instead, place the metrics side by side.

+++

+++When I drag a metric over, I don't see any actual data - just zeros. How can I troubleshoot this issue?

If you successfully created a workspace report but there's no data, there are a few things you can check:

* Double check the report suite and make sure it is populated with data.
* If you applied a segment in your report, the segment criteria might not match any data. Try removing the segment or adjusting the segment definition.
* Check the date range in the upper right corner and make sure it's set to a value that you'd expect.
* Navigate to your website and use the [Debugger](https://experienceleague.adobe.com/docs/debugger/using/experience-cloud-debugger.html) to validate that data is being collected.


+++

+++As a read-only user, what actions can I perform in Analysis Workspace?
When a project is shared as read only, all editing functions and features are completely disabled and recipients can only change the drop-down menu to apply a filter to the panel in a predefined manner.
+++
