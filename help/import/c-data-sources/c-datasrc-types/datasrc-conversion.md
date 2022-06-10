---
description: Data Sources supports the following conversion data dimensions and metrics for data types that are processed as conversion.
subtopic: Data sources
title: Conversion
topic-fix: Developer and implementation
feature: Data Sources
exl-id: 00450ad4-7148-4cf1-bdba-5d1732dd0fd3
---
# Conversion

Data Sources supports the following conversion data dimensions and metrics for data types that are processed as conversion.

## Conversion Dimensions and Metrics {#section_FA1731B232B246DABEDF5A5D84159084}

If you specify a View event, you must also specify the corresponding data dimension (eVar). For example, if you include eVar2 views, then you must list eVar2 with a value. The number of custom events and eVar views supported by a report suite is contract-dependent, and varies between companies.

<p class="head"> <b>Conversion Dimensions</b> </p>

| Column Name  | Description  |
|--- |--- |
|Tracking Code|Tracking code name.|
|Date|Use the following date format:  MM/DD/YYYY/HH/mm/SS (for example,  01/01/2015/06/00/00)|
|Category|Category name.  If you specify a category, then you must also select a product.|
|Channel|Channel name.|
|eVarn|eVarn name. Valid values for n are whole number 1 - 250.|
|Product|Product name.|
|State|State name.|
|Zip|Zip name.|

<p class="head"> <b>Conversion Metrics</b> </p>

| Column Name  | Description  |
|--- |--- |
|Clickthroughs|Number of tracking code views.|
|Cart Adds|Number of cart additions.|
|Cart Opens|Number of cart opens.|
|Cart Removes|Number of cart removals.|
|Cart Views|Number of cart views.|
|Checkouts|Number of checkouts.|
|Event n|Number of times event n occurred. Valid values for n are whole number 1 - 100.  If you specify a View event, you must also specify the corresponding data dimension (eVar). For example, if you include eVar2 views, then you must list eVar2 with a value.|
|eVarn Views|Number of times eVar n was viewed. Valid values for n are whole number 1 - 250.|
|Price|Product price.|
|Orders|Number of orders placed.|
|Product Views|Number of product views.|
|Quantity|Number of units sold.|
