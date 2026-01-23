---
description: Understand the various file formats that classification sets do support
title: Classification Set File Formats
feature: Classifications
exl-id: f3d429be-99d5-449e-952e-56043b109411
---
# Classification set file formats

Classification sets support multiple file formats for uploading classification data. Each format has specific requirements for successful data uploads.

Once your file is properly formatted according to these specifications, you can upload the data through the Classification sets interface or API. For detailed upload instructions: 

* **Browser upload**: See [Upload](manage/schema.md#upload) in the [Schema](manage/schema.md) interface for a classification set.
* **API upload**: See the [Analytics Classifications API](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/classifications/)

Classification sets support the following file formats:

* **JSON**: JavaScript Object Notation files with structured data
* **CSV**: Comma-separated values files
* **TSV or TAB**: Tab-separated values files

## General file requirements

All file formats must adhere to the following requirements:

* **File encoding**: Use UTF-8 without byte-order marks. Latin1 encoding is also supported.
* **Character limits**: Individual classification values have a maximum limit of 255 bytes.
* **Key requirements**: Key values cannot be empty or contain only whitespace. If duplicate keys are present, the last occurrence is used.

+++ JSON format details

The JSON file format follows conventions for JSON Lines (JSONL). The file must contain one JSON object per line, where each object represents a single classification record. 

>[!NOTE]
>
>Despite following the conventions for JSON Lines, use the `.json` file extension for all uploads. Using the `.jsonl` extension can result in errors.

### JSON structure

Each JSON object must contain:

* `key` (required): The unique identifier for the classification record
* `data` (required for updates): An object containing classification column names and their values
* `action` (optional): The action to perform. Supported values include:
  * `update` (the default action, when no action is specified)
  * `delete-field`
  * `delete-key`
* `enc` (optional): Data encoding specification. Supported values include:
  * `utf8` or `UTF8` (default)
  * `latin1` or `LATIN1`

All JSON field names (`key`, `data`, `action`, `enc`) are case-sensitive and must be lowercase.

### JSON validation rules

* The `key` field is required and cannot be null or empty.
* For `update` actions, the `data` field is required and cannot be empty.
* For `delete-field` actions, the `data` field must contain the fields to delete.
* For `delete-key` actions, the `data` field must not be present.
* Supported encoding values are case-insensitive and include standard charset names.

### JSON examples

Some examples of JSON records in a JSON file.

#### Basic update record

```json
{"key": "product123", "data": {"Product Name": "Basketball Shoes", "Brand": "Brand A", "Category": "Sports"}}
```

#### Update with encoding specified

```json
{"key": "product456", "enc": "utf8", "data": {"Product Name": "Running Shoes", "Brand": "Brand B"}}
```

#### Delete specific fields

```json
{"key": "product789", "action": "delete-field", "data": {"Brand": null, "Category": null}}
```

#### Delete an entire key

```json
{"key": "product999", "action": "delete-key"}
```


+++

+++ CSV format details

CSV (Comma-Separated Values) files use commas to separate classification data fields.

### CSV structure

* **Header row**: The first row must contain column headers and the first column must be the key column. Subsequent columns should match names in yours classification set schema
* **Data rows**: Each subsequent row contains classification data
* **Delimiters**: Fields are separated by commas
* **Quoting**: Fields containing commas, quotes, or newlines should be enclosed in double quotes

### CSV formatting rules

* Fields that contain commas must be enclosed in double quotes.
* Fields that contain double quotes must escape quotes by doubling them (`""`).
* Empty fields represent null values for that classification.
* Leading and trailing spaces around fields are automatically trimmed.
* Special characters (tabs, newlines) within quoted fields are preserved.

### CSV delete operations

* Use `~deletekey~` in any field to delete the entire key and all its classification data
* Use `~empty~` in specific fields to delete only those classification values (leaves other fields intact)
* When using `~empty~`, you can mix deletions with updates in the same file

### CSV examples

Some examples of CSV records in a CSV file.

#### Basic classification data

```csv
Key,Product Name,Brand,Category,Price
product123,"Basketball Shoes",Brand A,Sports,89.99
product456,"Running Shoes",Brand B,Sports,79.99
product789,"Winter Jacket",Brand C,Clothing,149.99
```

#### Delete an entire key

```csv
Key,Product Name,Brand,Category,Price
product999,~deletekey~,,,
```

#### Delete specific fields (mixed with updates)

```csv
Key,Product Name,Brand,Category,Price
product123,"Updated Product Name",Brand A,Sports,89.99
product456,,~empty~,~empty~,79.99
```

+++

+++ TSV and TAB format details

TSV (Tab-Separated Values) and TAB files use tab characters to separate classification data fields.

### TSV and TAB structure

* **Header row**: The first row must contain column headers and the first column must be the key column. Subsequent columns should match names in yours classification set schema.
* **Data rows**: Each subsequent row contains classification data.
* **Delimiters**: Fields are separated by tab characters (`\t`).
* **Quoting**: Generally no quoting is needed, but some implementations support quoted fields.

### TSV and TAB formatting rules

* Fields are separated by single tab characters.
* Empty fields (consecutive tabs) represent null values.
* No special quoting is typically required.
* Leading and trailing spaces are preserved.
* Newline characters within fields should be avoided.

### TSV and TAB delete operations

* Use `~deletekey~` in any field to delete the entire key and all its classification data.
* Use `~empty~` in specific fields to delete only those classification values (leaves other fields intact).
* When using `~empty~`, you can mix deletions with updates in the same file.

### TSV and TAB examples

Some examples of TSV or TAB delimited records in a TSV or TAB file.

#### Basic classification data

```tsv
Key    Product Name    Brand    Category    Price
product123    Basketball Shoes    Brand A    Sports    89.99
product456    Running Shoes    Brand B    Sports    79.99
product789    Winter Jacket    Brand C    Clothing    149.99
```

#### Delete an entire key

```tsv
Key    Product Name    Brand    Category    Price
product999    ~deletekey~            
```

#### Delete specific fields (mixed with updates)

```tsv
Key    Product Name    Brand    Category    Price
product123    Updated Product Name    Brand A    Sports    89.99
product456        ~empty~    ~empty~    79.99
```

+++

## Error handling

Common issues and solutions when uploading files:

### General file format errors

* **Invalid file format**: Verify that your file extension matches the content format (`.json`, `.csv`, `.tsv`, or `.tab`).
* **Unknown header**: Column names must match your classification set schema (applies to all formats).

### JSON specific errors

* **Key is a required field**: All JSON records must have a non-empty `"key"` field (lowercase, case-sensitive).
* **Data is a required field when using action=update**: JSON update actions must include a `"data"` field.
* **Data is a required field when using action=delete-field**: JSON delete-field actions must specify which fields to delete in the `"data"` field.
* **Data must not be present when using action=delete-key**: JSON delete-key actions cannot include a `"data"` field.
* **Unsupported encoding**: Use only supported encoding values in the `"enc"` field (`utf8`, `UTF8`, `latin1`, `LATIN1`).
* **Invalid JSON syntax**: Ensure that the JSON file is formatted correctly following JSONL conventions. Also check for general JSON formatting, missing quotes, commas, brackets, etc.


### CSV and TSV specific errors

* **The first column is required to be the key**: Ensure your CSV or TSV file has a proper header row with the key column first.
* **A minimum of two header items are required**: CSV or TSV files must have at least a `Key` column and one classification column.
* **The first header column must be called 'Key'**: The first column header must be exactly `Key` (capital `K`, case-sensitive).
* **Blank headers are not allowed**: All CSV/TSV column headers must have names.
* **The number of columns did not match the headers**: Each CSV or TSV data row must have the same number of fields as the header row.
* **"Malformed document**: Check CSV quoting, proper tab separation in TSV files, and more.


### Size limit errors

* **Key exceeds maximum size**: Individual keys cannot exceed 255 bytes.
* **Column value exceeds maximum size**: Individual classification values cannot exceed 255 bytes.

## Best practices

* **File size**: 50MB is the maximum file size for browser and API uploads.
* **Batch processing**: For large datasets, consider splitting into smaller files.
* **Data validation**: Test with a small sample file before uploading large datasets.
* **Backup**: Keep copies of your source data files.
* **Incremental updates**: Us the JSON format for precise control over individual record updates and deletions.
