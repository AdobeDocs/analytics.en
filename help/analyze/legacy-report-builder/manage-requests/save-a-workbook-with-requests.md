---
description: Learn about saving rports with embedded requests.
title: About saving a workbook with requests
uuid: 31611031-0982-4124-9fc7-7888124aa603
feature: Report Builder
role: User, Admin
exl-id: 192ac2f6-cfb8-447b-8fc1-19ad786ef924
TQID: https://experienceleague.adobe.com/0UMDDWbeilsUp-yB-tzMVcWkGfUXtf4lh2ciaAg4AEk
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
    internal-label: Reports
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
    internal-label: Analysis Workspace
  - id: f73667dc-d296-4875-8975-ac3fdc3adc42
    internal-label: Dashboards
subfeature_v2:
  - id: ac8a38fa-dec3-4581-8f64-178fde9f64e8
    internal-label: Report Builder
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
---
# Save a workbook with requests

{{legacy-arb}}

When you create reports with embedded requests, you can save them using **File** > **Save** or **File** > **Save As** in Excel. Report Builder detects whether the report contains requests. When you select one of the save options, complete the **Save Workbook As** form.

* As a best practice for any extensive work with Windows applications, Adobe recommends that you save your requests in the spreadsheet often and regularly to avoid an unexpected loss of requests in your worksheet.
* When naming your workbook, consider using a version number in the file name so that you can preserve a work history. For example, name your first workbook [!DNL web_forecast_01_01.xlsx].
* If you have already saved the report, the [!UICONTROL Save Template] form is not displayed when saving the report a second time. If the report contains no requests, this dialog box is not displayed. Instead, the standard Excel [!UICONTROL Save As] form is displayed.

## Filenames and location {#section_2406629E9B644CE08430826948977D5D}

The [!UICONTROL Save Template] form has some of the same functions as the standard Excel [!UICONTROL File] > [!UICONTROL Save As] dialog box, such as a text box for entering the file name of the spreadsheet report using the conventional [!DNL .xls] file extension.

Any file name you use must contain 255 characters or less. In addition, the file name may not contain the following characters:

\ ? | > < : / &#42; ' "

Finally, you cannot use Unicode characters beyond the set of extended ASCII characters.

When saving the file to a location on your local or network drives, you may enter the full path in the text box, or click on the browse button  ![browse_button.gif](assets/browse_button.gif) adjacent to the [!UICONTROL Save As] text box.
