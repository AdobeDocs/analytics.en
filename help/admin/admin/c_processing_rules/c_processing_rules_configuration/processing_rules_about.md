---
description: Processing rules let you make changes to data based on defined conditions. When attributes or values match defined conditions, values can be set and deleted, and events can be set.
seo-description: Processing rules let you make changes to data based on defined conditions. When attributes or values match defined conditions, values can be set and deleted, and events can be set.
seo-title: How processing rules work
solution: Analytics
subtopic: Processing rules
title: How processing rules work
topic: Admin tools
uuid: c3284962-960d-4f0f-8911-da5cb46aadfc
index: y
internal: n
snippet: y
---

# How processing rules work

Processing rules let you make changes to data based on defined conditions. When attributes or values match defined conditions, values can be set and deleted, and events can be set.

Processing rules are applied to data as it is collected, and rules are applied to all data that comes through the AppMeasurement libraries and through the Data Insertion API. Processing rules also apply to the full and log data sources. These sources contain data that represents a *`hit`* or an action that a user takes. Processing rules do not apply to other data sources.

* [Important Concepts](../../../admin/c_processing_rules/c_processing_rules_configuration/processing_rules_about.md#section_EB138775E7C64C74B0D1D3213F7A823C) 
* [Processing Rule Conditions](../../../admin/c_processing_rules/c_processing_rules_configuration/processing_rules_about.md#section_387390EEE9BA4DA98698522A84326DB4) 
* [Processing Rule Actions](../../../admin/c_processing_rules/c_processing_rules_configuration/processing_rules_about.md#section_E2285C9D008442C7BF136E52A9A4CC06)

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
   <td colname="col2"> <p> <a href="../../../admin/c_processing_rules/c_processing_rules_configuration/t_processing_rules_copy_to_rs.md#task_6E4B82FCA687409B88F17EAFC353755D" type="task" format="dita" scope="local"> Copy processing rules to another report suite </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Processing rules are applied in the order listed. </p> </td> 
   <td colname="col2"> <p>If an action changes a value, subsequent conditions use the new value. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Processing rules are applied immediately to the report suite after they are saved. </p> </td> 
   <td colname="col2"> <p>Changes from processing rules should be visible in your report suite within minutes of saving. When testing processing rules, we recommend configuring <a href="realtime.md#concept_6E8756BDDAE843F88B6563C09C48B0B6" format="dita" scope="local"> Real-Time Reports</a> in your test report suite so you can quickly see the results of a processing rule. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Processing rules are the only way to access to context data variables. </p> </td> 
   <td colname="col2"> <p> <a href="../../../admin/c_processing_rules/processing_rules_examples/processing_rules_copy_context_data.md#concept_43AA4980A2D847D6A3BEC50BCC0780E7" format="dita" scope="local"> Copy a Context Data Variable to an eVar </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Processing rules are applied before VISTA rules and Marketing Channel rules. </p> </td> 
   <td colname="col2"> <p> <a href="../../../admin/c_processing_rules/c_processing_rules_configuration/processing_rule_order.md#concept_8A6BBEA7F50C40C8A8D8755D4F579B1E" type="concept" format="dita" scope="local"> Processing Order </a> </p> </td> 
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
   <td colname="col1"> <p>Query string parameters cannot be read beyond the first 255 characters of a URL if you are running JavaScript AppMeasurement H.25.2 or earlier. JavaScript AppMeasurement H.25.3 (released January 2013) and later provide the full URL including all query string parameters to processing rules. </p> </td> 
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
   <td colname="col2"> <p> <a href="../../../admin/c_processing_rules/processing_rules_examples/clean_up_values_in_a_report.md#concept_958E924BCCBB4BBA91CE91C977FE5151" type="concept" format="dita" scope="local"> Cleaning up Values in a Report </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Context data variable names can contain only alphanumeric characters, underscores and dots. Any additional characters are stripped out. </p> </td> 
   <td colname="col2"> <p>For example, The context data variable <span class="codeph"> login_page-home</span> automatically becomes <span class="codeph"> login_pagehome</span>. All data sent to the <span class="codeph"> login_page-home</span> variable is allocated under <span class="codeph"> login_pagehome</span>. </p> <p>Context data variables that contain unsupported characters cannot be added in the Processing Rules interface. </p> </td> 
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
