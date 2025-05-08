---
description: The importer lets you bulk-upload classifications data to analytics reporting in a file. The import requires a specific file format for successful data uploads.
title: Classification data files
feature: Classifications
exl-id: aa919a03-d461-4d12-adc1-6441fb467e63
---
# Classification data files (legacy)

The importer lets you bulk-upload classifications data to analytics reporting in a file. The import requires a specific file format for successful data uploads.

To help you create valid data files, you can download a template file that provides a file structure into which you can paste the classifications data. For more information, see [Download Classifications Template](/help/components/classifications/importer/c-download-saint-data.md).

See [General File Structure](/help/components/classifications/importer/c-saint-data-files.md) for more information about character limits in classifications.

## General file structure

The following illustration is a sample data file:

![](assets/completed-saint-file.png)

A data file must adhere to the following structure rules:

* Classifications cannot have a value of 0 (zero).
* Adobe recommends that you limit the number of import and export columns to 30.
* Uploaded files should use UTF-8 without BOM character encoding.
* Special characters, such as a tabs, newlines, and quotes can be embedded within a cell provided the v2.1 file format is specified and the cell is properly [escaped](/help/components/classifications/importer/importer-faq.md). Special characters include:

  ```text
  \t     tab character 
  \r     form feed character 
  \n    newline character 
  "       double quote
  ```

  The comma is not a special character.

* Classification names cannot contain a caret (^) since this character is used to denote a subclassification.
* Use care when using a hyphen. For example, if you use a hyphen (-) in a Social term, Social recognizes the hyphen as a [!DNL Not] operator (the minus sign). For example, if you specify *`fragrance-free`* as a term using the import, Social recognizes the term as fragrance *`minus`* free and collects posts that mention *`fragrance`*, but not *`free`*.
* Character limits are enforced to classify report data. For example, if you upload a classifications text file for products ( *`s.products`*) with product names longer than 100 characters (bytes), the products will not display in reporting. Tracking Codes and all custom conversion variables (eVars) allow 255 bytes. This policy also extends to classification and subclassification column values, which are subject to the same 255 bytes limit.
* Tab-delimited data file (create the template file using any spreadsheet application or text editor).
* Either a `.tab` or `.txt` file extension.
* A pound sign (#) identifies the line as a user comment. Adobe ignores any line that begins with #.
* A double-pound sign followed by SC (`## SC`) identifies the line as a pre-processing header comment used by reporting. Do not delete these lines.
* Classification exports can have duplicate keys due to newline characters in the key. In an FTP or browser export, this can be resolved by turning on quoting for the FTP account. This will place quotes surrounding each key with newline characters.
* Cell C1 in the first line of the import file contains a version identifier that determines how classifications handle the use of quotes throughout the remainder of the file.

  * v2.0 ignores quotes and assumes they are all part of the keys and values specified. For example, consider this value: "This is ""some value""". v2.0 would interpret this literally as: "This is ""some value""".
  * v2.1 tells classifications to assume that quotes are part of the file formatting used in Excel files. So v2.1 would format the above example to: This is "some value".
  * Problems can arise when v2.1 is specified in the file, but what is actually wanted is v2.0 - namely, when quotes are used in ways that is illegal under Excel formatting. For example, if you have a value: "VP NO REPS" S/l Dress w/ Overlay. With v2.1, this is incorrect formatting (the value should be surrounded by opening and closing quotes and quotes that are part of the actual value should be escaped by quotes) and classifications will not work beyond this point.
  * Make sure that you do one of the following: change your file format to v2.0 by changing the header (cell C1) in the files you upload, OR properly implement Excel quoting throughout your files.

* The first (non-comment) row of the data file contains the column headings used to identify the classification data in that column. The importer requires a specific format for column headings. For more information, see [Column Heading Format](/help/components/classifications/importer/c-saint-data-files.md).
* Immediately following the header row in a data file are the data rows. Each line of data should contain a data field for each column heading.
* The data file supports the following control codes, which Adobe uses to provide structure to the file, and correctly import classifications data: 

<table id="table_0548F2E58B6644208147434EB9B3C21B"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> CONTROL CODE </th> 
   <th colname="col2" class="entry"> DESCRIPTION </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>&lt;New Line&gt; </p> </td> 
   <td colname="col2"> <p>A new line character is the only supported delimiter between data lines/records in the data file. Typically, you only need to specifically insert these characters when writing a program to automatically generate data files. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>~autogen~ </p> </td> 
   <td colname="col2"> <p>Requests that Adobe automatically generate a unique id for this element. </p> <p>In the campaign context, this control value instructs Adobe to assign an identifier to each creative element. See <a href="/help/components/classifications/importer/c-saint-data-files.md"  > Key </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>~period~ </p> </td> 
   <td colname="col2"> <p>Designates that the data column represents the date range associated with the item. See <a href="/help/components/classifications/importer/c-saint-data-files.md"  > Date </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Empty field </p> </td> 
   <td colname="col2"> <p>Represents a NULL value for the current field. Use this if a particular data column does not apply to the current record. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>PER Modifiers </p> </td> 
   <td colname="col2"> <p>Designates that the data column represents a <span class="wintitle"> PER Modifier </span> field. See <a href="/help/components/classifications/importer/c-saint-data-files.md"  > PER Modifier Headings </a>. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Column heading format

>[!NOTE]
>
>Adobe recommends that you limit the number of import and export columns to 30.

Classification files support the following column headings:

### Key

Each value must be unique across the entire system. The value in this field corresponds to a value assigned to the [!DNL Analytics] variable in your Web site's [!DNL JavaScript] beacon. Data in this column might include ~autogen~ or any other unique tracking code.

### Classification column heading

>[!NOTE]
>
>The values in the [!UICONTROL Classifications] column heading must exactly match the classification's naming convention, or the import fails. For example, if the administrator changes [!UICONTROL Campaigns] to [!UICONTROL Internal Campaign Names] in the [!UICONTROL Campaign Set-up Manager], the file column heading must change to match. "Key" is a reserved classification (header) value. New classifications named "Key" are not supported.

Additionally, the data file supports the following additional heading conventions to identify subclassifications and other specialized data columns:

### Subclassification heading

For example, `Campaigns^Owner` is a column heading for the column containing `Campaign Owner` values. Similarly, `Creative Elements^Size` is a column heading for the column containing the `Size` subclassification of the `Creative Elements` classification.

## Troubleshooting classifications

* [Common Upload Issues](https://helpx.adobe.com/analytics/kb/common-saint-upload-issues.html): Knowledge Base article that describes issues arising from incorrect file formats and file contents.
