---
description: To bulk import bot rules, you can upload a CSV file that defines the rules.
seo-description: To bulk import bot rules, you can upload a CSV file that defines the rules.
seo-title: Upload bot rules
solution: Analytics
subtopic: Bot rules
title: Upload bot rules
topic: Admin tools
uuid: bd70c199-5817-437e-980d-6d8f95d82f2c
index: y
internal: n
snippet: y
---

# Upload bot rules

To bulk import bot rules, you can upload a CSV file that defines the rules.

Create a CSV file with the following columns in the order presented: 

<table id="table_770891EF9E4A49F695977BB6446736B5"> 
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> Bot Name</span> </p> </td> 
   <td colname="col2"> <p> <span class="codeph"> IP Start </span> </p> </td> 
   <td colname="col3"> <p> <span class="codeph"> IP End </span> </p> </td> 
   <td colname="col4"> <p> <span class="codeph"> Agent Match Rule (contains or starts with)</span> </p> </td> 
   <td colname="col5"> <p> <span class="codeph"> Agent Include (100 char limit)</span> </p> </td> 
   <td colname="col6"> <p> <span class="codeph"> Agent Exclude (255 char limit)</span> </p> </td> 
  </tr> 
 </tbody> 
</table>

You can define three types of bot rules:

* User agent contains or starts with 
* Single IP address or wildcard match 
* IP range match

Each row in the import file can contain only one of the following bot definitions:

* **User agent contains or starts with**: Provide a single user agent string to match in the Agent Include column. Specify the type of match you want performed by placing *contains* or *starts with* in the Agent Match Rule field. An optional value can be included in the Agent Exclude column that defines one or more pipe-delimited ( `|` ) strings that the Agent does not contain. String matches are case-insensitive. Both the IP Start and IP End columns must be empty. 

* **Single IP address or wildcard match**: To match a single IP address ( `10.10.10.1`) or wildcard IP address ( `10.10.*.*`), place the same value in both the IP Start and IP End columns. Match Rule, Agent Include, and Agent Exclude must be empty. 

* **IP range match**: Define a range of IP addresses using the IP Start and IP End columns. Wildcards can be used to match IP ranges, for example `10.10.10.*` to `10.10.20.*`. Match Rule, Agent Include, and Agent Exclude must be empty.

**Multiple Rules Combined with OR**

To match a bot using a combination of rules joined with an OR (for example, user agent or IP address), provide an identical name for all rules that you want to combine in the bot name field. AND matches are not supported.

**Overwrite All Rules with an Upload File**

Select the **[!UICONTROL Overwrite existing rules]** checkbox to delete all existing rules and replace them with the rules defined in the upload file.

**Exporting Rules**

The **[!UICONTROL Export Uploaded Bot File]** button exports all rules defined in the UI in a CSV format. 
