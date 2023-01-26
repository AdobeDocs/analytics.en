---
description: Each ID that you want to be able to search for is assigned a namespace, which is a custom string that identifies that ID in any variable where it is used across all your report suites.
title: Namespaces
feature: Data Governance
exl-id: 421572c2-2789-48bc-b530-d48216799724
---
# Namespaces

Each ID that you want to be able to search for is assigned a namespace, which is a custom string that identifies that ID in any variable where it is used across all your report suites.

The namespace string is used to identify the field(s) that you want searched when providing an ID as part of a Data Privacy request. When a Data Privacy request is submitted, the request will include a JSON section specifying the data subject IDs to use for the request. Multiple IDs can be included as part of a single request for a data subject. The JSON includes:

* A "namespace" field containing the namespace string.
* A "type" field that for most Adobe Analytics requests contains the value "analytics".
* A "value" field containing the ID that Analytics should search for in the associated namespace variables from each of your report suites.

Refer to the [Experience Cloud Data Privacy API documentation](https://experienceleague.adobe.com/docs/experience-platform/privacy/api/overview.html) for more details.

## Cookie ID

Legacy Analytics Tracking Cookie, also known as the Adobe Analytics ID (AAID):

```
{
   namespace: "AAID",
   type: "standard",
   value: "2CCEEAE88503384F-1188000089CA"
}
```

The value must be specified as two hexadecimal numbers separate by a dash. All hexadecimal digits that are alphabetic characters must be specified using upper case. The hexadecimal values should not have any leading zeros (note the difference from the same value specified in the deprecated form, where the leading zeros are required).

It is also acceptable to use `"namespaceId": 10` instead of or in addition to `"namespace": "AAID"` and you may see some other Adobe products use that form.

## Legacy Analytics Tracking Cookie: Deprecated form

```
{
   "namespace": "visitorId",
   "type": "analytics",
   "value": "2cceeae88503384f-00001188000089ca"
}
```

Deprecated form:

The value should be specified as two 16-digit hexadecimal numbers or as two 19-digit decimal numbers. The numbers should be separated by a dash, underscore or colon. Leading zeros should be added if either number doesn't have enough digits.

## Identity Service Cookie

```
{
    namespace: "ECID",
    type: "standard",
    value: "00497781304058976192356650736267671594"
}
```

The value must be specified as a 38-digit decimal number. If you are pulling this number from the two mcvisid\_high/low or post\_msvisid\_high/low columns from a data feed or Data Warehouse report, you must zero pad each of the two numbers to 19 digits and then concatenate them with the high value first.

It is also acceptable to use: `"namespaceId": 4` instead of or in addition to `"namespace": "ECID"` and you may see some other Adobe products use that form.

>[!NOTE]
>
>The Experience Cloud ID (ECID) was previously known as the Marketing Cloud ID (MCID), and is still referred to by that name in some existing documentation.
>
>These IDs are the only IDs supported by Analytics that use a "type" value other than "analytics".

If the format of the value portion of any of these cookie IDs does not follow the format described for that ID, then the Data Privacy request will fail, with an error of "Value not formatted correctly."

You will most commonly collect these cookie IDs using the new [privacy JavaScript](https://developer.adobe.com/experience-platform-apis/references/privacy-service/), which will automatically provide all of the relevant key/value pairs for these JSON IDs.

This JavaScript code populates the JSON with other key/value pairs besides those listed above (namespace, type, value), but the fields listed above are the most important for Analytics Data Privacy processing and the only ones you need to provide if you collect the IDs in some other way.

## Custom Visitor ID

```
{
     namespace: "customVisitorID",
     type: "analytics",
     value: "<ID>"
}
```

The namespace is also predefined for the custom visitor ID.

## IDs in Custom Variables

```
{
    namespace: "Email Address",
    type: "analytics", 
    value: "john@xyz.com" }, 
{
    namespace: "CRM ID", 
    type: "analytics", 
    value: "123456-ABCD" 
}
```

For IDs in custom traffic or conversion variables (props or eVars), label the variable with an ID-DEVICE or ID-PERSON label, then assign your own namespace name to that type of ID. See [Provide a Namespace when Labeling a Variable as ID-DEVICE or ID-PERSON.](gdpr-labels.md)

You can also see namespaces that you have previously defined for other variables or report suites and reuse one of those, so that the same namespace can easily be used for all your report suites that store that type of ID. It is also possible to assign the same namespace to multiple variables within a report suite. For example, some customers store a CRM ID in a traffic variable and a conversion variable (depending on the page, it is sometimes in one or the other or both), and they could assign the namespace "CRM ID" to both variables.

>[!TIP]
>
>Avoid using the friendly name of a variable (the name displayed in the reporting UI) or the variable's number (such as eVar12) when specifying the namespace to the Data Privacy API, unless it is the namespace specified when applying the ID-DEVICE or ID-PERSON label. Using a namespace rather than a friendly name allows the same user identity block to specify the correct variable for multiple report suites. For example, if the ID is in different eVars in some of the report suites, or if the friendly names don't match (such as when the friendly name has been localized for a specific report suite).

>[!CAUTION]
>
>The namespaces "visitorId" and "customVisitorId" are reserved for identifying the Analytics legacy tracking cookie and the Analytics customer visitor ID. Do not use these namespaces for custom traffic or conversion variables.

For more information, see [Provide a Namespace when Labeling a Variable as ID-DEVICE or ID-PERSON.](/help/admin/c-data-governance/data-labeling/gdpr-labels.md)
