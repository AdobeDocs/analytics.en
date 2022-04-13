---
description: Information about special characters used in the data feed.
keywords: Data Feed;job;special characters;hit_data;multi-valued variables;events_list;products_list;mvvars
subtopic: data feeds
title: Special characters in data feeds
feature: Data Feeds
exl-id: b816ebc5-0b23-4420-aa8c-b88953d031e6
---
# Special characters in data feeds

Adobe uses escape logic to make sure that values sent to data collection servers do not corrupt or negatively data feed files. The following characters are reserved by Adobe for the following purposes in `hit_data.tsv`.

## Special characters in any column

| Character | Description |
|--- |--- |
| `\t` | Represents a tab. Marks the end of a column or data field. |
| `\n` | Represents a newline. Marks the end of a row or hit. |
| `\` | Backslash. Escapes characters when sent as part of data collection. |

When these reserved values are preceded by a backslash, they were sent as part of data collection.

| Character | Description |
|--- |--- |
| `\\t` | The value '`\t`' was sent during data collection, escaped by Adobe. |
| `\\n` | The value '`\n`' was sent during data collection, escaped by Adobe. |
| `\\` | The value '`\`' was sent during data collection, escaped by Adobe. |

For example, a visitor to your site uses internal search and searches for "search\nstring". You populate eVar1 with "search\nstring", and send that value to Adobe. Adobe receives this hit, and escapes the newline included in the string. The actual value placed in raw data is "search\\nstring".

## Special characters in multi-valued variables (events_list, products_list, mvvars)

The following characters have a special meaning in columns that can contain multiple values.

| Character | Description |
|--- |--- |
| `,` | Comma. Represents the end of an individual value. Separates product strings, event ID's, or other values. |
| `;` | Semi-colon. Represents the end of an individual value in `product_list`. Separates fields within a single product string. |
| `=` | Equals sign. Assigns a value to an event in `product_list`. |
| `^` | Caret. Escapes characters when sent as part of data collection. |

When these reserved values are preceded by a caret, they were sent as part of data collection.

| Character | Description |
|--- |--- |
| `^,` | The value '`,`' was sent during data collection, escaped by Adobe. |
| `^;` | The value '`;`' was sent during data collection, escaped by Adobe. |
| `^=` | The value '`=`' was sent during data collection, escaped by Adobe. |
| `^^` | The value '`^`' was sent during data collection, escaped by Adobe. |
