---
description: (Optional) Before importing classifications into marketing reports, you can download a template that helps you create a classifications data file. The data file uses your desired classifications as column headings, then organizes the reporting data set under the appropriate classification headings.
title: Classification template
feature: Classifications
exl-id: e299509a-0c4f-4ba8-9e91-96356c386054
TQID: https://experienceleague.adobe.com/OR9THCLd93iUl58npPiinO4yAsK8KG3FU8qmBILHioY
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
    internal-label: Reports
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
subfeature_v2:
  - id: c80b99d6-98b9-4aeb-b5c4-933ef2ef705c
    internal-label: Marketing Channels
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
---
# Classification template (legacy)

{{classification-importer-deprecation}}

(Optional) Before importing classifications into reports and projects, you can download a template that helps you create a classifications data file. The data file uses your desired classifications as column headings, then organizes the reporting data set under the appropriate classification headings.

## Classification template {#concept_0F06847AD8D042F5BA818AE3C37E2417}

(Optional) Before importing classifications into marketing reports, you can download a template that helps you create a classifications data file. The data file uses your desired classifications as column headings, then organizes the reporting data set under the appropriate classification headings.

**[!UICONTROL Admin]** > **[!UICONTROL Classification Importer]**.

|  Element  | Description  |
| --- | ---|
|  Select Report Suite  | Select the report suite to use in the template. The report suite and data set must match.  |
|  Data Set to be Classified  | Select the type of data for the data file. The menu includes all reports in your report suites that are configured for classifications.  |
| Export Numeric 2 |**Important**: This option is not available for report suites enabled for the New Classification Architecture. |
|  Encoding  | Select the character encoding for the data file. The default encoding format is UTF-8.<br>**Important**: This option is not available for report suites enabled for the New Classification Architecture.|
|  Download  | Downloads the template file.  |

The template includes the currently defined classifications (column headings) of a specific data set without including the data associated with each classification.

>[!NOTE]
>
>The Template method limits your classification data download to a single report suite.

For more information about the data file structure, see [About Classification Data Files](/help/components/classifications/importer/c-saint-data-files.md).

## Download a classifications data template (optional) {#task_8DFCF309B6FD43ABB1D6FEE9AFAEC596}

The template provides the file format you must follow for classifications.

>[!NOTE]
>
>The Template method limits your data download to a single report suite.

1. Click **[!UICONTROL Admin]** > **[!UICONTROL Classification Importer]**.
1. On the **[!UICONTROL Download Template]** tab, specify the [data template configuration](/help/components/classifications/importer/c-download-saint-data.md).
1. Click **[!UICONTROL Download]**.
1. Save the template file to your local system.

   The template file is a tab-delimited data file ( [!DNL .tab] filename extension) that most spreadsheet applications support.
