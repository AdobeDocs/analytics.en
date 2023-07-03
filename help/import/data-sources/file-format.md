---
title: Data source file format
description: Correctly generate a file for use in data sources.
exl-id: 6632b970-e931-4272-a69b-c1130ad6475f
feature: Data Sources
---
# Data source file format

Data source files have the following properties:

* The file is in `.txt` format.
* Commented lines start with '`#`', and are optional.
* The first non-commented line contains the file's headers.
* The first value of every row is the date, which uses the format `MM/DD/YYYY` or `MM/DD/YYYY/HH/mm/SS`.
* Values on every row, including headers, are tab-delimited.
* Every row must have at least one dimension and one metric.

## Comments

Any row that starts with '`#`' is a comment. When downloading a data source template file, the first two lines are comments.

* The first comment indicates the type of template that you configured for the data source, the backend user ID that created the data source, and the data source ID.
* The second comment provides friendly names for each of the headers included in the template file.

All comment rows are ignored by Adobe when the file is processed, so you can remove the template comments or add your own throughout the file. Only full rows can be commented; you cannot comment out individual fields or partial rows.

## Headers

When uploading data source files, column headers are required. These column headers are not case-sensitive, but required spaces are necessary (For example, `eVar1` is an invalid header, while `EVAR 1` is valid). Column headers apply to all report suites. Use the following tables to make sure that each header in your data source file is set correctly.

>[!TIP]
>
>You can make a data sources file from scratch if you include the correct headers in your data source file. There is no limit to the number of headers that you can include within a single file; however, each row can only have a maximum of 4096 bytes.

| Dimension | Data source header |
| --- | --- |
| [Category](/help/components/dimensions/category.md) | `Category` |
| [eVar1 - eVar250](/help/components/dimensions/evar.md) | `Evar 1` - `Evar 250` |
| [Marketing Channel](/help/components/dimensions/marketing-channel.md) | `Marketing Channel` |
| [Marketing Channel Detail](/help/components/dimensions/marketing-detail.md) | `Marketing Channel Detail` |
| [Product](/help/components/dimensions/product.md) | `Product` |
| [Tracking Code](/help/components/dimensions/tracking-code.md) | `Tracking Code` |
| [Transaction ID](/help/implement/vars/page-vars/transactionid.md) | `transactionID` |
| [Zip code](/help/components/dimensions/zip-code.md) | `Zip` |

{style="table-layout:auto"}

Dimensions and metrics go into the same header row.

| Metric | Data source header |
| --- | --- |
| [Cart Additions](/help/components/metrics/cart-additions.md) | `Cart Adds` |
| [Cart Removals](/help/components/metrics/cart-removals.md) | `Cart Removes` |
| [Cart Views](/help/components/metrics/cart-views.md) | `Cart Views` |
| [Carts](/help/components/metrics/carts.md) | `Cart Opens` |
| [Checkouts](/help/components/metrics/checkouts.md) | `Checkouts` |
| [Custom Events](/help/components/metrics/custom-events.md) | `Event 1` - `Event 1000` |
| [Orders](/help/components/metrics/orders.md) | `Orders` |
| [Revenue](/help/components/metrics/revenue.md) | `Price` |
| [Units](/help/components/metrics/units.md) | `Quantity` |

{style="table-layout:auto"}

Adobe does not support data sources for any other dimensions or metrics. If variables beyond what are listed in the above tables are required, consider using the [Bulk data insertion API](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/bulk-data-insertion/) instead.

## Date

The first value in every row **must** be the date. Date format must be in one of the following formats:

* **`MM/DD/YY/HH/mm/SS`**
* **`MM/DD/YY`**

Omitting the hours/minutes/seconds automatically sets the timestamp to 12 PM for that day.

A single data source file supports up to 90 unique days. If you want to include more than 90 unique days in an upload, split your data into multiple files.

## Dimension and metric data

Subsequent values after the date in each row contains the data that you want to upload. Every row corresponds with that respective timestamp. Make sure that the same number of tabs exist on every row. Columns can be in any order; make sure that the data in each row aligns with the headers at the top. The maximum amount of data a single row can have is 4096 bytes.

Dimension data cannot contain semicolons (`;`). Rows that contain semicolons are skipped.

## Next steps

[File upload](file-upload.md): Learn the process to upload a data sources file for ingestion by Adobe.
