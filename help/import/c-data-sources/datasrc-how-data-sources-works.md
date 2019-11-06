---
description: Information about how Adobe provides access to Data Sources.
seo-description: Information about how Adobe provides access to Data Sources.
seo-title: How Data Sources works
solution: Analytics
subtopic: Data sources
title: How Data Sources works
topic: Developer and implementation
uuid: ee9e6e74-9b00-4733-9a4b-d9f2b954cc7c
---

# How Data Sources works

Information about how Adobe provides access to Data Sources.

> [!NOTE] Once submitted via the Data Sources, imported data is indistinguishable from reporting data gathered using other methods (JavaScript beacon, ActionSource, Data Insertion API, etc.). You cannot remove the data once it is imported.

![](assets/data_sources_overview.png)

Two methods are available to submit data:

* [FTP](/help/import/c-data-sources/datasrc-how-data-sources-works.md#section_0E70022648F94061AF5B4AD6C7145243) 
* [API](/help/import/c-data-sources/datasrc-how-data-sources-works.md#section_65DACC9CE00C437BBFDD02D19C25A4BD)

## FTP {#section_0E70022648F94061AF5B4AD6C7145243}

You can create and manage FTP-based data sources through marketing reports, which uses FTP file transfer to import data files into Data Sources. After creating a data source, Adobe provides you with an FTP location that you can use to upload Data Source files. Once uploaded, Data Sources automatically locates and processes them. Once processed, the data is available for marketing reports.

## API {#section_65DACC9CE00C437BBFDD02D19C25A4BD}

Adobe offers a Data Sources API that lets you programmatically link your applications into Data Sources. This eliminates the need for an intermediary FTP server, and transfers data via HTTP, SOAP, and REST.

See [Data Sources API Documentation](https://marketing.adobe.com/developer/documentation/data-sources/c-data-sources-api).
