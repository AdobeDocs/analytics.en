---
description: You can download saved and unsaved projects in PDF and CSV formats.
seo-description: You can download saved and unsaved projects in PDF and CSV formats.
seo-title: Download PDF or CSV files
title: Download PDF or CSV files
uuid: 8af5f3d7-5870-4ed6-8a9f-ef290a48ef5f
---

# Download PDF or CSV files

You can download saved and unsaved projects in PDF and CSV formats.

The name of the PDF or CSV file matches the current name of the project. For unsaved projects, the downloaded file includes the unsaved changes in the project. Note that you cannot schedule unsaved projects in PDF or CSV.

>[!NOTE]
>
>We also support the Fallout visualization in CSV format.

>[!NOTE]
>
>When we render a project to PDF, we just render what is on the page. If a project has custom-sized visualizations and panels, you need to change them to be auto-sized (button in top-right corner) so that there will be no truncated content.

1. Create or open a project.
1. Click **[!UICONTROL Project]** > **[!UICONTROL Download CSV (or Download PDF).]**

On April 11, 2019, several changes were made to **[!CSV downloads]** (and **[!Copy to Clipboard]**) from Analysis Workspace to remove formatting from exported data.
* The thousands separator is no longer included. (The decimal separator will continue to be included, and will adhere to the format defined under **[!UICONTROL Components > Report Settings > Thousands Separator]**).
* No currency symbols are shown.
* No percent symbols are shown.
* Percentages are in decimal form; e.g., 75% is represented as 0.75.
* Time is shown in seconds.
* Cohort Tables show raw values only; percentages are removed.
* If a number is invalid, an empty cell is displayed.

>[!Note:]
>
> Numeric values that use a comma as the decimal separator will continue to be quoted in the exported CSV.
