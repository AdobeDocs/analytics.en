---
description: Information about the Data Source .txt template.
subtopic: Data sources
title: Import file reference
topic-fix: Developer and implementation
feature: Data Sources
exl-id: 7966b156-04bf-4d39-a720-ab47a665d1e2
---
# Import file reference

Information about the Data Source .txt template.

 Use the Data Sources Wizard to generate an import template. The Data Sources import file includes the following data:

* A pound symbol (#) identifies that row as a comment.
* You can add additional comments to the file, as needed.
* A comment that lists the template file title.
* A comment that lists the external metric and data dimension names specified in the [!UICONTROL Data Source Activation Wizard].

Column headings are used to identify the data in each column of the Data Source file. There are three types of column headings:

**Date**: (Required) A time stamp for each data row in the file, in the format `m/d/yyyy`.

**Variables**: The names of the reporting variables mapped to the data source's data dimensions.

**Events**: The names of the events mapped to the data source's metrics.

Use the Data Source template to create a Data Sources file that contains data that you want to upload. When creating a Data Sources file, remember the following:

* Effectively, each row in the Data Sources file contains one data record, where each record is made up of a series of tab-separated fields. The column headers in the Data Source template define the order of these fields. For example:

  ```
    #Sample data file for mycorp_report_suite 
    #Imported data for ad impressions applied to Event 6
    Date     Tracking Code      Event 6 
    1/1/2009     NYT8453A      8754
    1/1/2009     WSJ4453B      9492
    1/1/2009     BHG44563      10553
    1/2/2009     NYT8453A      6452
    1/2/2009     WSJ4453B      7237
    1/2/2009     BHG44563      9031
  ```

* If you upload multiple data files, Data Sources loads them in alphabetical order. Files that need to be in processed chronologically must be named such that their alphabetical order corresponds to their chronological order. For example:

  ```
  log_2009-01-01_13:00.txt
  log_2009-01-01_13:15.txt
  log_2009-01-01_13:30.txt
  ```

* To speed processing of your Data Sources file, Adobe recommends aggregating event (metric) data into a single row per date.

  For example, if your Data Sources file maps ad impression data to Event 6, create a single data row that includes the total number of ad impressions for each day, rather than creating a separate data row entry for each ad impression that occurred on a particular day.
* If you need to upload data from dates prior your report suite's creation date, contact your Account Manager to change the oldest date for which you can run reports.

**.FIN file**

When you have finished filling out your Data Source file, you can FTP it into Analytics. However, an additional file is needed in order for your data to be processed. You will need to upload an empty text file with the same name of your data file, but with a [!DNL .fin] extension.

For example, if you upload a (tab-delimited) data file called [!DNL myproductdata.txt], you would also need to upload an empty text file called [!DNL myproductdata.fin]. Without the [!DNL .fin] file, data would never be processed.
