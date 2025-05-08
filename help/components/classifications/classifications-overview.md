---
title: Classifications overview
description: Customize the grouping of dimension items.
feature: Classifications
exl-id: 0d2c77ea-610f-48e0-b6a2-6e91794783b1
---
# Classifications overview

A classification is a way of categorizing Analytics variable data, then displaying the data in different ways when you generate reports. You establish a relationship between a variable value and metadata related to that value. Classifications can be used on most custom dimensions, such as [Tracking code](/help/components/dimensions/tracking-code.md), [props](/help/components/dimensions/prop.md), and [eVars](/help/components/dimensions/evar.md).

**Classification sets** are the primary way to classify data. **Classification rules** and the **Classification importer** are legacy methods to classify data. All classification data ultimately operates the same in reporting; you can combine any of these methods to best fit your organization's workflow.

* **Classification sets**: Create and manage classifications and their rules in a single, simplified interface.
* **Classification rules** (legacy): Create rules that assign a given dimension item to a classification dimension item. This method to classify data is best when a dimension frequently encounters new unique values or where manual classifications would be frequent and burdensome.
* **Classification importer** (legacy): Export a template spreadsheet with dimension items in each row. Columns represent each classification for a dimension. This method to classify data is best when all dimension items are known and does not require frequent updating.

A single dimension can have multiple classification dimensions. For example, you can classify [!UICONTROL Product IDs] with additional product attributes, such as product name, color, size, description, and SKU. Each of these attributes would be a separate classification dimension belonging to the same parent dimension. Augmenting your reports with these attributes provides deeper and more complex reporting opportunities. Once a dimension contains classification data, the classification dimension is available in reporting that contains only classification dimension items. Any parent dimension item that does not contain a classification value is grouped under [Unspecified](/help/technotes/unspecified.md)
