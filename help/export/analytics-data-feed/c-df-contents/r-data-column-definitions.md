---
description: Use this section to select which data columns to include in the feed and how the feed data should be processed and packaged before delivery.
keywords: Data Feed;data;column;definitions;select column templates;clickstream;available columns;included columns;compression format;packaging type;include data manifest;remove escaped characters;download csv
seo-description: Use this section to select which data columns to include in the feed and how the feed data should be processed and packaged before delivery.
seo-title: Data column definitions
solution: Analytics
title: Data column definitions
uuid: 43370933-5dd9-48f0-a1be-3d10d38a0edb
index: y
internal: n
snippet: y
---

# Data column definitions

Use this section to select which data columns to include in the feed and how the feed data should be processed and packaged before delivery.

* [Data Column Options](../../../export/analytics-data-feed/c-df-contents/r-data-column-definitions.md#section_AD12773C162240B1AE454FA1F000F445) 
* [Specify Columns](../../../export/analytics-data-feed/c-df-contents/r-data-column-definitions.md#section_42BB8910657D4F959375451F2EAD4A58) 
* [Download CSV](../../../export/analytics-data-feed/c-df-contents/r-data-column-definitions.md#section_10F5B6A05D15469394FAEA68BF14BA0D)

## Data Column Options {#section_AD12773C162240B1AE454FA1F000F445}

The Data Column Definition section includes the following options:

| Option | Description |
|--- |--- |
|Remove Escaped Characters|Select whether to remove escaped characters from the feed content.|
|Include Data Manifest|Select whether to include a data manifest at the beginning of each delivered feed.|
|Compression Format|Select the compression format for the generated feed.|
|Packaging Type|Specify how the feed is sent.|

## Specify Columns {#section_42BB8910657D4F959375451F2EAD4A58}

Select the desired columns from the Available list, then click **[!UICONTROL Add]** to include the selected columns.

The Data Column Definitions section contains the following elements:

| Field | Description |
|--- |--- |
|Select Column Templates|Choose from the list of predefined Data Columns definitions.  After you select a column definition template, the "Included Columns" list contains columns from the selected template.|
|Available Columns List|Choose from the list of all possible Dimension and Metrics IDs that can be included in a data feed.|
|Included Columns|Choose from the list of columns included in the data feed.  The Delete icon appears when hovering above an included column.  Drag and drop to move columns up and down in the Included Columns list.|

## Download CSV {#section_10F5B6A05D15469394FAEA68BF14BA0D}

The Download CSV option lets you download the current Data Column Definition.

>[!NOTE]
>
>This option is available only after at least one column is added to the Included Column list.

