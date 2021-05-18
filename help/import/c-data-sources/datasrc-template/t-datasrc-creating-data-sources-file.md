---
description: The import template file is designed to get you started with the import.
subtopic: Data sources
title: Generate an import file template
topic-fix: Developer and implementation
uuid: bcd90e34-42e6-4cd1-b67e-87586dea25d8
exl-id: c2717936-a011-4224-8a9e-94753abbcb33
---
# Generate an import file template

The import template file is designed to get you started with the import.

You are not limited to the columns defined in the template. You can add any additional columns as needed, as long as the metric or definition is supported for the selected data processing type. You can view the supported metrics and dimensions for each type in the following sections: [Web Log](/help/import/c-data-sources/c-datasrc-types/datasrc-web-log.md), [Traffic](/help/import/c-data-sources/c-datasrc-types/datasrc-traffic.md), [Conversion](/help/import/c-data-sources/c-datasrc-types/datasrc-conversion.md), [Transaction ID](/help/import/c-data-sources/c-datasrc-types/datasrc-transactionid.md), [Visitor ID](/help/import/c-data-sources/c-datasrc-types/datasrc-visitorid.md), [Full Processing](/help/import/c-data-sources/c-datasrc-types/datasrc-full-processing.md)). For example, for a traffic data type, you can add a column for any metric or dimensions listed in [Traffic](/help/import/c-data-sources/c-datasrc-types/datasrc-traffic.md).

Once created, you can download the template, input your data into the template, then upload the data to the Data Sources FTP site. Once processed by the Data Sources server, the imported data is available for use in your Analytics reports.

The Data Source template is a .txt file that you can open with any text editor. However, it is easiest to work with the template using Microsoft Excel or another spreadsheet application. The template content varies based on your selections in the Data Source Activation Wizard.

See [Import File Reference](/help/import/c-data-sources/datasrc-template/datasrc-import-file-reference.md) for additional details.

1. Log in to Analytics.
1. In the Suite header, select **[!UICONTROL Admin]** > **[!UICONTROL All admin]** > **[!UICONTROL Data sources]**.
1. On the **[!UICONTROL Data Sources Create]** tab, select a template category and type.
1. Review the Activation Instructions/Information, then click **[!UICONTROL Activate]**.

   Step Result 1. Select template generation options in the Data Source Activation Wizard.

    | Wizard Page | Field | Description |
    |--- |--- |--- |
    |1|Name|The template name that Analytics displays in The Data Sources Manager.|
    |1|Email|The email address that receives all notifications related to the use of this Data Source template.|
    |1|Associated Fees Checkbox|Select the checkbox to indicate your acceptance of the fees associated with using this Data Source template.|
    |2|Choose Metrics|Select the metrics to import using this Data Source. Analytics recommends certain metrics based on the Data Source Category and Type selected in Step 3.  To specify a different metric, type its name in a blank field, then select the check box to enable the metric.|
    |3|Map Metrics|Select a Analytics Event to receive each imported metric selected in Wizard page 2.  These should be new, unassigned Events that you have previously assigned names that correspond to the imported metric data they will receive through Data Sources.  If an eVar, Product, or Tracking Code variable is a destination variable, and the uploaded values match existing captured values, the uploaded events essentially add metrics to existing values. For example, you might create an "Offline Orders" metric with a Products data dimension that already has Product Views, Checkouts, and Orders as existing metrics.|
    |4|Choose Data Dimensions|Select the data dimensions to breakdown the imported metrics from this Data Source. Analytics recommends certain data dimensions based on the Data Source Type selected in Step 3.  To specify a different data dimension, type its name in a blank field, then select the check box to enable the data dimension.|
    |5|Map Data Dimensions|Select a standard report or eVar to receive each imported data dimension selected in Wizard page 4.|

1. After the template is generated, copy data into the appropriate columns of the Data Source template, making sure to adhere to the data format required for that data column.

   Step Result 1. Save the Data Sources file using a naming convention of your choice. Adobe recommends using a consistent naming convention for all Data Sources files. Use a common file extension such as .txt or .tsv (or don't use any extension).
