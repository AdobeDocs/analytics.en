---
description: You can download saved and unsaved projects in PDF and CSV formats.
title: Download PDF or CSV files
uuid: 8af5f3d7-5870-4ed6-8a9f-ef290a48ef5f
---

# Download PDF or CSV files

You can download saved and unsaved projects in PDF and CSV formats.

The name of the PDF or CSV file matches the current name of the project. For unsaved projects, the downloaded file includes the unsaved changes in the project. Note that you cannot schedule unsaved projects in PDF or CSV.

Keep this in mind:

* We also support the Fallout visualization in CSV format.
* When we render a project to PDF, we just render what is on the page. If a project has custom-sized visualizations and panels, you need to change them to be auto-sized (button in top-right corner) so that there will be no truncated content.
* PDFs downloaded in the browser can take several minutes to export. This is because we have to re-run the entire project on our servers before rendering it in PDF format. We recommend not leaving the project until the PDF downloads in your browser. However, you can continue to make changes to the project while you wait. 
* We are aware that if you have very long Workspace projects, PDFs currently export as one giant page, rather than as a paginated document. We are working on an improvement to Workspace PDF export that will allow for pagination.

1. Create or open a project.
1. Click **[!UICONTROL Project]** > **[!UICONTROL Download CSV (or Download PDF).]**

On April 11, 2019, several changes were made to **[!UICONTROL CSV downloads]** (and **[!UICONTROL Copy to Clipboard]**) from Analysis Workspace to remove formatting from exported data.
* The  **[!UICONTROL Thousands Separator]** is no longer included. (The decimal separator will continue to be included, and will adhere to the format defined under **[!UICONTROL Components > Report Settings > Thousands Separator]**).
* No currency symbols are shown.
* No percent symbols are shown.
* Percentages are in decimal form; e.g., 75% is represented as 0.75.
* Time is shown in seconds.
* Cohort Tables show raw values only; percentages are removed.
* If a number is invalid, an empty cell is displayed.
* No rounding is applied (even if specified in calculated metric) - raw values are shown.

>[!NOTE]
>
>Numeric values that use a comma as the decimal separator will continue to be quoted in the exported CSV.
