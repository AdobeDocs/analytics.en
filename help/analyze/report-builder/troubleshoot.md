---
description: Ways you can optimize report builder delivery, and a list of error messages that could occur occasionally.
title: Troubleshooting and best practices for Report Builder
uuid: 36a08143-dc78-40f5-9ce9-7d16980aa27b
feature: Report Builder
role: User, Admin
exl-id: 41a640ce-2316-439b-b3ba-f0bace9af268
---
# Troubleshooting and best practices for Report Builder

Ways you can optimize report builder delivery, and a list of error messages that could occur occasionally.

## Report Builder 5.0 users and opening 5.1 workbooks {#section_C29898775999453FABB5FB0E098415C8}

Adobe changed the separator between dimensions and classifications from an underscore character (_) to ||. This change has compatibility implications for a Report Builder 5.0 user who opens a Report Builder v5.1 workbook with classification requests. Each time a workbook from a version older than v5.1 is opened, all its serialized classifications requests will be converted to this format.

This introduces a forward compatibility problem: Once converted to v5.1, if a workbook is shared with a user on Report Builder v5.0, that user will not be able to recognize the classification request (indeed, it is looking for "_" but v5.1 serialized "||").

You will experience the following side effect when opening a ARB v5.1 workbook with classification request:

* When opening the workbook, you will get the following warning: "This workbook was last saved using Report Builder v5.1. This version has introduced some features that are incompatible with the Report Builder version installed on this computer. It is highly recommended that you upgrade to the latest Report Builder version before updating this workbook." 
* If you right-click an ARB request with classification, the Report Builder context menus (edit request, add dependent request...) will not show up.
* If you perform a Refresh All, by clicking the third button, or by refreshing a set of requests from the Request Manager form, the classification request will execute without error. However, the classifications values will not be written out.
* You can still edit the request by opening the Request Manager, then going from row to row, until it reaches the right request.
* If you edit the request and leave all parameters the same and then click Finish, the response will be properly written out. Indeed, editing the request resolves the problem as the Response Layout parameters are re-serialized. So there is a workaround, although it is time consuming.

## Authentication issues in Report Builder {#section_FD79104DF1414FE2B36591606C963DE6}

Report Builder requires authentication to create data requests from your report suites. Sometimes there are issues logging in to report builder depending on your settings within [!DNL Analytics] or your network.

* **Invalid Login Company**: This error most commonly occurs when either the login company is improperly entered, or if there are network activity issues. Do the following:
  * Check the login company spelling to ensure that there is not a typo or an errant space.
  * Log in to Analytics with the same login company to ensure that it is correct. If you are not able to log in with those credentials, contact one of your organization's administrators to obtain the correct login company.
* **Firewall**: Report Builder uses ports 80 and 443. Ensure that these ports are allowed through your organization's firewall. See also Adobe's Internal IP Addresses for additional firewall exclusions.

## Recommendations for optimizing requests {#section_33EF919255BF46CD97105D8ACB43573F}

The following factors can increase request complexity and result in slower processing.

* **Factors that can slow down deliveries**: Too many bookmarks, dashboards, and Report Builder workbooks were scheduled within a few hours. Also consider too many Report Builder workbooks were scheduled at around the same time. When this occurs, the report API queue becomes backlogged.
* **Factors that can slow down workbook runtime**: Significant increase in classifications, or increasing the request date range over time.
* **Causes that result in workbook delivery failure**: Complex Excel formulas in a workbook, particularly ones that involve date and time.
* **Cells returning 0s (no values)**: An apostrophe or single quote in the Excel sheet name will cause report builder to return no values. (This is a Microsoft Excel limitation.)
* **Individual request performance**: Processing speed can be affected by the following settings: 

  | Setting | Faster Performance | Slower Performance |
  |--- |--- |--- |
  |Breakdowns and the breakdown order|Few|Many|
  ||Example: If you break down A by Z, the number of items for A should always be less than the number of items for Z. If it is the other way around, the request time can increase significantly.|
  |Date range|Small range|Wide range|
  |Filtering|Specific filtering|Most Popular filtering|
  |Granularity|Aggregated|Hourly<ul><li>Daily</li><li>Weekly</li><li>Monthly</li><li>Quarterly</li><li>Yearly</li></ul>|
  |Number of entries|Small data set|Large data set|

* **Scheduling time**: Stagger scheduling over 24-hour period (see table below). Existing bookmarks , dashboards, and Report Builder workbooks scheduled close together may cause delays. Schedule larger, more complex requests in the early morning to allow for manual pulls and refreshing to occur during the business day.

  | Scheduling Time | 1 a.m. - 2 a.m. | 2 a.m. - 7 a.m. | 7 a.m. - 6 p.m. | 6 p.m. - Midnight |
  |--- |--- |--- |--- |--- |
  |Report Builder usage|Quiet|Very busy|Client-side usage.<br>Higher volumes of users refreshing locally and requesting to "Send immediately."<br>Additionally, verify whether the API queue is cleared when scheduled workbooks time out.|Not busy|

* **Timeouts**: Any scheduled report times out after four hours. The system attempts scheduling three more times, potentially resulting in a failure. (Generally, the larger the data set the longer it takes to run.) These can be seen in [!DNL Analytics] reporting and Report Builder:

## Error message descriptions {#section_3DF3A1EEDAD149CB941BEABEF948A4A5}

A list of error messages that could occur occasionally while you are using Report Builder.

>[!NOTE]
>
>This is only a selection of error messages, and not an exhaustive list. For more information about resolving errors, contact your administrator.

* **This feature can only be applied on an open workbook.**: If no workbooks (spreadsheet documents) are open in Excel, and you click one of the icons in the report builder toolbar, this message is displayed. In addition, the toolbar becomes disabled until you open a spreadsheet. However, you can click the on-line help icon while the toolbar is still enabled without causing this error.
* **You first need to exit the [!UICONTROL Request Wizard]before activating the [!UICONTROL Request Manager].**: While the [!UICONTROL Request Manager] and the [!UICONTROL Request Wizard] are linked functionally, it is not possible to start working with the [!UICONTROL Request Manager] before completing or cancelling actions taken in the [!UICONTROL Request Wizard].
* **There is no request associated with this range.**: This error message occurs if you click on the [!UICONTROL From Sheet] button in the [!UICONTROL Request Manager] when a cell of the spreadsheet contains no requests. To identify which cells in the spreadsheet contain requests, click individual requests listed in the table in the [!UICONTROL Request Manager]. If a request is associated with cells, the cells will show up highlighted when the request is selected in the table.
* **The selected Range is not valid. Please select another Range.**: If a cell of the spreadsheet is selected and already has a request mapped to it, this error occurs. Either delete the request mapped to the cells or choose another range of cells to map. When you want to delete cells, it is important to locate cells containing requests and delete the request before deleting the cells (removing rows or columns).
* **Please Exit the Excel Cell with focus before using this feature.**: If you are in *edit mode* in an Excel cell and click one of the Report Builder icons, this error message appears. Edit mode in an Excel cell means that the cell is selected and the cursor appears inside the cell. You are also in edit mode in an Excel cell when you type directly into the [!UICONTROL Formula] bar or into the [!UICONTROL Name Box] at the top of Excel.
* **The range selected intersects another request's range. Please change your selection.**: If you have already mapped a set of cells to the spreadsheet, this error is displayed.
* **Repairs to workbook (Removed Records: Formula from /xl/calcChain.xml part)**: Sometimes a workbook's formulas get corrupted when saving or transferring. When the file is opened, Excel tries to run these formulas and fails. You can resolve this issue by removing `calcChain.xml` from the spreadsheet, forcing Excel to refresh its formula calculations.
  1. Rename the workbook's file extension from `.xlsx` to `.zip`.
  2. Unzip the contents and open the `/xl/` folder.
  3. Delete `calcChain.xml`.
  4. Re-zip the contents, and change the file extension back to `.xlsx`.
  5. Open the workbook in Excel and refresh all Report Builder requests.
* **Excel cells associated with the input filters or output range may have been deleted**: Report Builder uses Excel Names to attach data requests to cells. If you delete Excel Names from the Names Manager, you can see this error. Requests cannot be recovered if Excel Names are deleted. If the workbook was scheduled, you can either download a copy from the Scheduling Manager, or open previously delivered copies of the workbook.
