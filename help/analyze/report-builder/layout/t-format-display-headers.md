---
description: Learn how to name your report and configure how to display row and column headers.
title: How to format display headers
uuid: cd0e167b-9463-43fd-87b2-724d1c79de68
feature: Report Builder
role: User, Admin
exl-id: 168daa6b-965c-4f8b-97b7-651a7ad55d6c
---
# Format display headers

You can name your report and configure how to display row and column headers. The Format Options link is available for the Pivot and Custom Layout types.

1. Create a request on the [!UICONTROL Request Wizard: Step 1].
1. Click **[!UICONTROL Next]**.
1. On the [!UICONTROL Request Wizard: Step 2] form, add dimensions and metrics data to the request, as desired.
1. Click **[!UICONTROL Format Options]**.
1. Configure the [!UICONTROL Display] options:

   | Element| Description|
   |--- |--- |
   |Report Name|Displays either the name of the report type you selected from the tree in the  Request Wizard: Step 1 (for example, [!DNL Traffic Report]), or the name you type in the [!DNL Name this Request] field.|
   |Filters Parameters|Displays the dimension filters, such as a search filter.|
   |Segment|Displays the segment parameter.|
   |Data Recency|Displays data recency parameters. For example:    Data Recency: Page Views (1.5 hr ago), Exits (30 mins ago)  See [Options](/help/analyze/report-builder/options.md) for information about current data processing.|

   Regarding display order, if the [!UICONTROL Row Label] grid (on Step 2) contains an item, it is displayed first in the request. If not, the system uses the first item present in the [!UICONTROL Column Label] grid. If no row or column items exist, the first item in the [!UICONTROL Metrics] grid is displayed.

   **Display Row and Column Headers:** Adds a row and column to display these items.

   In version 3.11, you could display a header for each item. Version 4 displays all of these items or none of them. If you created a request in version 3.11 and open it in version 4.x, Report Builder prompts you in Step 2 to update the range by one cell for items that are missing a header.

   **Change Headers to Excel Auto-Filters:** Available only if row and column headers are displayed. This setting creates an Excel auto filter and appends it to the data Report Builder returns for this request.

   >[!NOTE]
   >
   >Excel supports only one auto-filter per worksheet. If you create a new auto filter in a worksheet where an auto filter already exists, Excel does not provide a warning that the existing auto-filter is going to be replaced.

   **Perform Auto-Outline:** Transforms the date returned by Report Builder from a list view to a tree view.

   **Name this Request:** Lets you type a user-defined name for the request, or use the default name selected on Step 1. This name appears as the [!UICONTROL Report] name in the [!UICONTROL Request Manager]. See [Name a Request](/help/analyze/report-builder/layout/name-a-request.md).

1. Click **[!UICONTROL OK]**.
