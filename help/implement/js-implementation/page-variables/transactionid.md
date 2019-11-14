---
description: Page variables directly populate a report, such as pageName, List Props, List Variables, and so on.
keywords: Analytics Implementation
solution: Analytics
subtopic: Variables
title: Page variables
topic:
uuid:
---

# transactionID

[!UICONTROL Integration Data Sources] use a [!UICONTROL transaction ID] to tie offline data to an online transaction (like a lead or purchase generated online).

<!-- 

transactionID.xml

 -->

Each unique *`transactionID`* sent to Adobe is recorded in preparation for a [!UICONTROL Data Sources] upload of offline information about that transaction. See [Data Sources](https://marketing.adobe.com/resources/help/en_US/sc/datasources/).

|  Max Size  | Debugger Parameter  | Reports Populated  | Default Value  |
|---|---|---|---|
|  100 bytes  | xact  | n/a  | ""  |

**Enable Transaction ID Storage** {#section_3EA2C9DC9D4C4F0FBE4AB67981BCB52E}

Before *`transactionID`* values are recorded, [!UICONTROL Transaction ID Storage] must be enabled for the report suite selected in the Report Suite Manager. This setting is located at 

```
Analytics > Admin > Report Suites > Edit Settings > General > General Account Settings.
```

To see whether *`transactionID Storage`* is enabled for a report suite, go to

```
Analytics > Admin > Data Sources > Manage
```

**Syntax and Possible Values** {#section_0C18329203DC45E989DBAE70C0FB4801}

```js
s.transactionID="unique_id"
```

The *`transactionID`* should contain only alphanumeric characters. If multiple [!UICONTROL transactionIDs] should be recorded in a single hit, you can use a comma to delimit multiple values.

**Examples** {#section_A4C1F0E54CB54AD7B86A22147E9B5FEF}

```js
s.transactionID="11123456"
```

```js
s.transactionID="lead_12345xyz"
```

```js
s.transactionID=s.purchaseID
```

**Pitfalls, Questions, and Tips** {#section_4299BAD5D0154DBC88A9EF0E2C252BB4}

* If *`transactionID`* recording is not enabled, *`transactionID`* values will be discarded and unavailable for use with [!UICONTROL Integration Data Sources]. Make sure to set a conversion variable or event (an eVar or the events variable) on the page where *`transactionID`* is set. Otherwise, no data is recorded for the *`transactionID`*.

* If you are recording [!UICONTROL transactionIDs] for multiple systems, such as purchases and leads, make sure the value in *`transactionID`* is always unique. This can be accomplished by adding a prefix to the ID, such as lead_1234 and purchase_1234. [!UICONTROL Integration Data Sources] do not function as expected ( [!UICONTROL Data Source] data will tie to the wrong data) if a unique *`transactionID`* is seen twice.

* By default, *`transactionID`* values are remembered for 90 days. If your offline interaction process is longer than 90 days, contact Customer Care to have the limit extended.

> [!NOTE] The *`transactionID`* variable can contain any character other than a comma. It should be in the same location where the character limit (100 bytes) is specified. If multi-byte characters are used, multi-byte character support must be enabled in order to avoid problems with unexpected characters in the *`transactionID`*.
