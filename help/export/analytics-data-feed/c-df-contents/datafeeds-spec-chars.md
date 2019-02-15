---
description: Information about special characters used in the data feed.
keywords: Data Feed;job;special characters;hit_data;multi-valued variables;events_list;products_list;mvvars
seo-description: Information about special characters used in the data feed.
seo-title: Special characters
solution: Analytics
subtopic: data feeds
title: Special characters
topic: Reports and analytics
uuid: 5efe019b-39e6-4226-a936-88202a02f5e6
---

# Special characters

Information about special characters used in the data feed.

* [Special characters in the hit_data file](../../../export/analytics-data-feed/c-df-contents/datafeeds-spec-chars.md#section_9759C7A6AE684EB5B4A154FB6A26B39E) 
* [Special characters in multi-valued variables (events_list, products_list, mvvars)](../../../export/analytics-data-feed/c-df-contents/datafeeds-spec-chars.md#section_056F8D540FFC4F24A001DC74331C2AAC) 
* [Sample workflow](../../../export/analytics-data-feed/c-df-contents/datafeeds-spec-chars.md#section_97F8C2925A35433DA2E7E8BE60037E37)

## Special characters in the hit_data file {#section_9759C7A6AE684EB5B4A154FB6A26B39E}

The following characters have a special meaning in the hit_data file: 

| Character | Meaning | Description |
|--- |--- |--- |
|\t  (tab character)|End of column|Marks the end of a data field.|
|\n  (newline character)|End of row|Marks the end of a data row.|
|\  (backslash character)|Escape character|Escapes tab, newline, and backslash when the character was part of the value sent during data collection.|

When any of the special characters are preceded by a backslash, they represent a literal character. 

| Character | Meaning | Description |
|--- |--- |--- |
|\\t|Tab|Literal tab character. This character was part of the value sent in during data collection.|
|\\n|Newline|Literal newline. This character was part of the value sent in during data collection.|
|\\|Backslash|Literal backslash character. This character was part of the value sent in during data collection.|

## Special characters in multi-valued variables (events_list, products_list, mvvars) {#section_056F8D540FFC4F24A001DC74331C2AAC}

The following characters have a special meaning in multi-valued variables: 

<table id="table_FDA13DE05A784ED4972C2955BD2642C7"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Character </th> 
   <th colname="col02" class="entry"> Meaning </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <span class="codeph"> , </span> (comma character) </td> 
   <td colname="col02"> End of value </td> 
   <td colname="col2"> <p>Separates product strings, event IDs, or other values in multi-valued variables. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="codeph"> ; </span> (semicolon character) </td> 
   <td colname="col02"> End of sub-value within an individual product value </td> 
   <td colname="col2"> <p>Separates values associated with an individual product in the <span class="codeph"> product_list </span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="codeph"> = </span> (equals character) </td> 
   <td colname="col02"> Value assignment </td> 
   <td colname="col2"> <p>Assigns a value to an event in the <span class="codeph"> event_list </span>. </p> </td> 
  </tr> 
 </tbody> 
</table>

When any of the special characters are preceded by a caret, they represent a literal character.

| Character | Meaning | Description |
|--- |--- |--- |
|^,|Comma|Literal comma character. This character was part of the value sent in during data collection.|
|^;|Semicolon|Literal semicolon character. This character was part of the value sent in during data collection.|
|^=|Equals|Literal equals character. This character was part of the value sent in during data collection.|
|^^|Caret|Literal caret character. This character was part of the value sent in during data collection.|

## Sample workflow {#section_97F8C2925A35433DA2E7E8BE60037E37}

If some of the columns in your data feed contain user-submitted data, you should check for special characters before separating the data by column or row using `split` or `readLine`, or similar.

Consider the following data: 

|  Browser Width  | Browser Height  | eVar1  | prop1  |
|---|---|---|---|
|  1680  | 1050  | search\nstring  | en  |
|  800  | 600  | search\tstring  | en  |

During export, the newline and tab characters in the eVar1 values are escaped. The data feed for these rows appears as follows:

```
1680\t1050\tsearch\\nstring\ten\n 
800\t600\tsearch\\tstring\ten\n
```

Calling `readLine()` on the first row returns the following partial string:

```
800\t600\tsearch\
```

Calling `split("\t")` on the second row returns the following string array:

```
800 
600 
search\ 
string 
en
```

To avoid this, use a solution similar to the following:

1. Starting at the beginning of the file, read until you locate a tab, newline, backslash or caret character. 
1. Perform an action based on the special character encountered:

    * Tab - insert the string up that point into a data store cell and continue. 
    * Newline - complete the data store row. 
    * Backslash - read the next character, insert the appropriate string literal, and continue. 
    * Caret - read the next character, insert the appropriate string literal, and continue.

