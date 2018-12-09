---
description: null
seo-description: null
seo-title: Labeling Example
title: Labeling Example
uuid: a9a5b937-dbde-4f0f-a171-005ef4c79df9
index: y
internal: n
snippet: y
---

# Labeling Example

* [Sample Hit Data](../../admin/c-data-governance/gdpr-labeling-example.md#section_94DE6BC0026F46D7AD7061C5625C8D52) 
* [Sample Access Request](../../admin/c-data-governance/gdpr-labeling-example.md#section_BDA817FD2415420DAAC835825484BA9D) 
* [Sample Delete Request](../../admin/c-data-governance/gdpr-labeling-example.md#section_6C75F70F5D574BE7AA540981E8B7EA26)

## Sample Hit Data {#section_94DE6BC0026F46D7AD7061C5625C8D52}

Suppose you have the following hit data:

* The first row contains the labels for each variable. 
* The second row is the name of the variable. If it has an ID label, it contains the assigned namespace in parentheses. 
* Hit data starts in the third row.

<!-- Meike, converted html tables for fix elusive validation error. Bob -->

| Labels | I2<br>ID-PERSON<br>DEL-PERSON<br>ACC-PERSON  | I2<br>ID-DEVICE<br>DEL-DEVICE<br>ACC-ALL  | I2<br>DEL-PERSON<br>ACC-PERSON | I2<br>DEL-DEVICE<br>DEL-PERSON<br>ACC-ALL  | I2<br>ID-DEVICE<br>DEL-DEVICE<br>ACC-ALL  |
|:---:|:---:|:---:|:---:|:---:|:---:|
|Variable Name<br>(Namespace)|MyProp1<br>(user)|Visitor ID<br>(AAID)|MyEvar1|MyEvar2|MyEvar3<br>(xyz)|
|Hit Data|Mary|77|A|M|X|
|Mary|88|B|N|Y|
|Mary|99|C|O|Z|
|John|77|D|P|W|
|John|88|E|N|U|
|John|44|F|Q|V|
|John|55|G|R|X|
|Alice|66|A|N|Z|


## Sample Access Request {#section_BDA817FD2415420DAAC835825484BA9D}

If I submit an access request, the summary file will contain the values indicated in the table below. A request may return only a device file, only a person file or one of each. Two summary files are only returned if a person ID is used and expandIds is true. 

| API Values | Returned File Type | Data in Summary Access File |
|--- |--- |--- |
|Namespace/ ID|expandIDs||MyProp1|Visitor ID|MyEvar1|MyEvar2|MyEvar3|
|AAID=77|false|device|Variable not present|77|Variable not present|M, P|X, W|
|AAID=77|true|device|77|M, P|X, W|
|user=Mary|false|person|Mary|77, 88, 99|A, B, C|M, N, O|X, Y, Z|
|user=Mary|true|person|Mary|77, 88, 99|A, B, C|M, N, O|X, Y, Z|
|device|not present|77, 88|not present|N, P|U, W|
|user=Mary AAID=66|true|person|Mary|77, 88, 99|A, B, C|M, N, O|X, Y, Z|
|device|not present|66, 77, 88|not present|N, P|U, W, Z|
|xyz=X|false|device|not present|55, 77|not present|M, R|X|
|xyz=X|true|device|not present|55, 77|not present|M, P, R|W, X|

Notice that the setting for expandIDs does not make any difference to the output when a cookie ID is used.

## Sample Delete Request {#section_6C75F70F5D574BE7AA540981E8B7EA26}

With a delete request using the API values in the first row of the table, the hit table will be updated to look something like this: 

|AAID=77 expandIDs value does not matter  |
|--- |
|MyProp1|AAID|MyEvar1|MyEvar2|MyEvar3|
|Mary|42|A|GDPR-7398|GDPR-9152|
|Mary|88|B|N|Y|
|Mary|99|C|O|Z|
|John|42|D|GDPR-1866|GDPR-8216|
|John|88|E|N|U|
|John|44|F|Q|V|
|John|55|G|R|X|
|Alice|66|A|N|W|

>[!NOTE]
>
>Only cells on rows containing AAID = 77 and a DEL-DEVICE label are impacted.

|user=Mary expandIDs=false  |
|--- |
|MyProp1|AAID|MyEvar1|MyEvar2|MyEvar3|
|GDPR-0523|77|GDPR-1866|GDPR-3681|X|
|GDPR-0523|88|GDPR-2178|GDPR-1975|Y|
|GDPR-0523|99|GDPR-9045|GDPR-2864|Z|
|John|77|D|P|W|
|John|88|E|N|U|
|John|44|F|Q|V|
|John|55|G|R|X|
|Alice|66|A|N|W|

>[!NOTE]
>
>Only cells on rows containing user=Mary and a DEL-PERSON label are impacted. Also, in practice the variable containing A_ID would probably be a prop or eVar and its replacement value would be a string starting with “GDPR-“, followed by a random number (GUID), rather than replacing the numeric value with a different, random numeric value.

|user=Mary expandIDs=true  |
|--- |
|MyProp1|AAID|MyEvar1|MyEvar2|MyEvar3|
|GDPR-5782|09|GDPR-0859|GDPR-8183|GDPR-9152|
|GDPR-5782|16|GDPR-6104|GDPR-2911|GDPR-6821|
|GDPR-5782|83|GDPR-2714|GDPR-0219|GDPR-4395|
|John|09|D|GDPR-8454|GDPR-8216|
|John|16|E|GDPR-2911|GDPR-2930|
|John|44|F|Q|V|
|John|55|G|R|X|
|Alice|66|A|N|W|

Note the following:

* Cells on rows containing user=Mary and a DEL-DEVICE or DEL-PERSON label are impacted, as well as cells with a DEL-DEVICE label on rows containing any Visitor ID that occurred on a row containing user=Mary. 
* MyEvar2 in the fourth and fifth rows is updated because these rows contain the same Visitor ID values as those on the first and second rows, so ID expansion includes them for device-level deletes. 
* The values of MyEvar2 in rows two and five match both before and after the delete, but after the delete no longer matches the value N that occurs in the last row, because that row was not updated as part of the delete request. 
* MyEvar3 behaves very differently than it did without ID expansion, because without ID expansion, no ID-DEVICES matched. Now AAID matches on the first five rows. 
