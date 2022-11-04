---
description: Processing rules let you make changes to data based on defined conditions. When attributes or values match defined conditions, values can be set and deleted, and events can be set.
subtopic: Processing rules
title: How processing rules work
feature: Processing Rules
exl-id: 9d2d9f2d-1e16-486f-9191-2c43776374da
---
# How processing rules work

Processing rules let you make changes to data based on defined conditions. When attributes or values match defined conditions, values can be set and deleted, and events can be set.

Processing rules are applied to data as it is collected, and rules are applied to all data that comes through the AppMeasurement libraries and through the Data Insertion API. Processing rules also apply to the full and log data sources. These sources contain data that represents a *`hit`* or an action that a user takes. Processing rules do not apply to other data sources.

## Important Concepts {#section_EB138775E7C64C74B0D1D3213F7A823C}

The following table contains key concepts you need to understand when using processing rules: 

<table id="table_287C606AE26E47AA8F737411990ACEB2"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Concept </p> </th> 
   <th colname="col2" class="entry"> <p>Details </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Rules apply to a single report suite. </p> </td> 
   <td colname="col2"> <p> <a href="/help/admin/admin/c-processing-rules/c-processing-rules-configuration/t-processing-rules-copy-to-rs.md"> Copy processing rules to another report suite </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Processing rules are applied in the order listed. </p> </td> 
   <td colname="col2"> <p>If an action changes a value, subsequent conditions use the new value. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Processing rules are applied immediately to the report suite after they are saved. </p> </td> 
   <td colname="col2"> <p>Changes from processing rules should be visible in your report suite within minutes of saving. When testing processing rules, we recommend configuring <a href="/help/admin/admin/realtime/t-realtime-admin.md"> real-time reports</a> in your test report suite so you can quickly see the results of a processing rule. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Processing rules are the only way to access to context data variables. </p> </td> 
   <td colname="col2"> <p> <a href="/help/admin/admin/c-processing-rules/processing-rules-examples/processing-rules-copy-context-data.md"> Copy a Context Data Variable to an eVar </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Processing rules are applied before VISTA rules and Marketing Channel rules. </p> </td> 
   <td colname="col2"> <p> <a href="/help/technotes/processing-order.md"> Processing Order </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Hits cannot be excluded. </p> </td> 
   <td colname="col2"> <p>You can use VISTA rules to exclude hits. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>The product string, referrer, and user agent cannot be changed. </p> </td> 
   <td colname="col2"> <p>Referrer and user agent are read-only. The product string is not available. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Mobile device attributes and classifications are not available. </p> </td> 
   <td colname="col2"> <p>The mobile device lookup occurs before processing rules, but attributes are not available in processing rules. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Query string parameters cannot be read beyond the first 255 characters of a URL if you are running JavaScript AppMeasurement H.25.2 or earlier. JavaScript AppMeasurement H.25.3 and later provide the full URL including all query string parameters to processing rules. </p> </td> 
   <td colname="col2"> <p>Upgrade to H.25.3 or later, or read query string parameters from long URLs client-side and store values in Context Data variables. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Query string values must be encoded in Unicode or UTF-8 to be read by processing rules. </p> </td> 
   <td colname="col2"> <p>This might affect multibyte characters that are passed using query strings. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>You are limited to 150 rules with 30 conditions each for each report suite. </p> </td> 
   <td colname="col2"> <p>Processing rule limits are per report suite, not per company. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Processing rules must be set up to retrieve context data variables before data is sent. </p> </td> 
   <td colname="col2"> <p>Processing rules are applied as server calls are sent. Values stored in context data variables are discarded if they are not copied using processing rules. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Value comparisons in the UI are case insensitive. </p> </td> 
   <td colname="col2"> <p> <a href="/help/admin/admin/c-processing-rules/processing-rules-examples/clean-up-values-in-a-report.md"> Cleaning up Values in a Report </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Context data variable names can contain only alphanumeric characters, underscores and dots. Any additional characters are stripped out. </p> </td> 
   <td colname="col2"> <p>For example, The context data variable <code> login_page-home</code> automatically becomes <code> login_pagehome</code>. All data sent to the <code> login_page-home</code> variable is allocated under <code> login_pagehome</code>. </p> <p>Context data variables that contain unsupported characters cannot be added in the Processing Rules interface. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Caret (^) is a special character in the processing rules system. </p> </td> 
   <td colname="col2"> <p>To match a single caret character, use two caret characters (^^). </p> </td> 
  </tr> 
 </tbody> 
</table>

## Processing Rule Conditions {#section_387390EEE9BA4DA98698522A84326DB4}

Conditions check page variables for a matching value or if a value is present. Multiple conditions can be added and you can select if all conditions must be matched.

You can create a rule with no conditions to always execute defined actions.

Variables are not automatically checked for values before actions occur. For example, Prop1 contains a value of "something", and eVar1 is empty. If you set Prop1 to equal eVar1 both values will be empty. If you need to avoid this add a condition to check for the presence of a value.

## Processing Rule Actions {#section_E2285C9D008442C7BF136E52A9A4CC06}

Actions set page variables, delete page variables, or trigger events. Actions can also concatenate values to display in a report.

For example, you might want to display `category:product` by concatenating two variables.
