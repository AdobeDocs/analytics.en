---
description: Workspace FAQs
title: Frequently asked questions and troubleshooting Workspace
feature: Workspace Basics
role: User, Admin
exl-id: cf7a9a73-bcbe-4bf5-b5dc-913199ab229c
---
# Frequently asked questions

| Question | Answer |
|--- |--- |
|What are the prerequisites for using Analysis Workspace?|[Send data to Adobe Analytics using tags in Adobe Experience Platform](/help/implement/launch/validate-publish-prod.md): Using Analysis Workspace requires a working implementation. Make sure your organization is sending data to Adobe before using the tool. Other implementations, such as legacy manual implementations, can work as well.|
|What are the Administration and access requirements for Analysis Workspace?|See [Administration Requirements](/help/analyze/analysis-workspace/workspace-faq/frequently-asked-questions-analysis-workspace.md).|
|Will using Analysis Workspace affect data collection?|Since Analysis Workspace is a reporting tool, it has no impact on data collection. There are no repercussions to indiscriminately dragging components into a project to see what works. Drag different combinations of dimensions and metrics into your workspace project to see what is available to you. If you accidentally drag an invalid component to your workspace project or would like to go back a step, press ctrl+Z (Windows) or cmd+Z (Mac) to undo the last action made. You can also start with a clean slate by clicking *[!UICONTROL Project] > [!UICONTROL New]* in the upper left menu.|
| How does data get into my Analysis Workspace project? | Watch this video: >[!VIDEO](https://video.tv.adobe.com/v/31072/?quality=12) |
|How many report suites can be displayed in an Analysis Workspace project?|You can now create projects in Analysis Workspace with data from more [multiple report suites](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/build-workspace-project/multiple-report-suites.html).|
|How do you implement Analysis Workspace?|No special implementation is required. Analysis Workspace is available to all companies with Analytics Standard or Premium. However, standard permissions to content (such as report suites and project components) apply, and for curating and sharing projects. See [Administration and Access Requirements](/help/analyze/analysis-workspace/workspace-faq/frequently-asked-questions-analysis-workspace.md).|
|Does Analysis Workspace change pre-configured reports in Adobe Analytics?|No. Because this is a separate environment, there are no changes to your existing or any pre-configured reports in Adobe Analytics. You can still employ standard Reports & Analytics and Report Builder reports using Analysis Workspace.|
|Can I use Analysis Workspace for Data Warehouse?|Analysis Workspace is not recommended for bulk data export. It is a visualization workspace creating dashboard-like analysis projects.|
|How can I optimize performance of Analysis Workspace?|See [Optimizing Performance](/help/analyze/analysis-workspace/workspace-faq/optimizing-performance.md).|

## Troubleshooting

**When I drag a metric over, it says 'Invalid data'.**

Invalid data means that Adobe cannot return data using the combination of dimensions and metrics used in the report. For example, two metrics stacked on top of each other cannot be returned as data, as there is no way to display two metrics that way. Instead, place the metrics side by side.

**When I drag a metric over, I don't see any actual data - just zeros.**

If you successfully created a workspace report but there's no data, there are a few things you can check:

* Double check the report suite and make sure it is populated with data.
* If you applied a segment in your report, the segment criteria might not match any data. Try removing the segment or adjusting the segment definition.
* Check the date range in the upper right corner and make sure it's set to a value that you'd expect.
* Navigate to your website and use the [Debugger](https://experienceleague.adobe.com/docs/debugger/using/experience-cloud-debugger.html) to validate that data is being collected.
