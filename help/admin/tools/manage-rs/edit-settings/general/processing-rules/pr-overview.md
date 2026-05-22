---
description: Processing rules simplify data collection and manage content as it is sent to reporting.
subtopic: Processing rules
title: Processing rules overview
feature: Processing Rules
role: Admin
exl-id: 0244aba2-4345-463a-8528-d4dcd2f872ff
TQID: 'https://experienceleague.adobe.com/fiWUPrFezgDFX-mx-ogHH1wXYgtUF9vAgLjay9z6vsU'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
  - id: ff9b434a-2221-4df7-81d1-5bcbf5f80bce
    internal-label: Admin Tools
subfeature_v2:
  - id: fbaf7f9a-8341-44f6-aa57-6c8d50741804
    internal-label: Processing rules
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: b4dd41a7-ccf8-4e9d-918e-acaab534a307
    internal-label: Data quality
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: d3cdead0-685a-4489-9250-4bb709942f66
    internal-label: Data collection
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
    internal-label: Administration
---
# Processing rules overview

Processing rules allow you to modify how your data is collected before it is written to a report suite.

**[!UICONTROL Admin]** > **[!UICONTROL Report Suites]** > Select report suite > **[!UICONTROL Edit Settings]** > **[!UICONTROL General]** > **[!UICONTROL Processing rules]**

>[!WARNING]
>
>Processing rules directly affect data collection, and can cause data loss if used incorrectly. Always test processing rules in a development report suite before enabling them in a production report suite to mitigate data quality issues.

The two primary use cases for processing rules include:

* **Use the context data variable implementation workflow**: Instead of directly setting variables in your implementation, you can use [Context data variables](/help/implement/vars/page-vars/contextdata.md) to set key/value pairs. For example, instead of setting:
  
  ```js
  s.eVar1 = "Robert Munch";
  s.eVar2 = "Books";
  s.eVar3 = "Youth";
  ```

  You can instead set:

  ```js
  s.contextData['author'] = "Robert Munch";
  s.contextData['section'] = "Books";
  s.contextData['genre'] = "Youth";
  ```
  
  You can then map the context data variables to the desired dimensions and metrics in the Analytics UI.

  When communicating with developers in your organization to implement Analytics on a property, using context data variables simplifies the communication process. Developers can simply implement each key/value pair once, then you as an Analytics admin can ensure that the data makes it to the correct implementation variable.

* **Modify data as it is collected**: This use case has a wide range of applications, such as temporary fixes to data quality or to help fill in implementation gaps. See [Processing rules use cases](pr-use-cases.md) for more information and specific examples.

## Permissions

Product admins have access to processing rules by default. You can grant access to processing rules to non-admins by including them in a product profile that includes the **[!UICONTROL Processing rules]** permission item. See [Product profile permissions for Report Suite Tools](/help/admin/admin-console/permissions/report-suite-tools.md) for more information.

## Considerations when creating or editing processing rules

When creating or editing processing rules, take the following into consideration:

* **Possible empty values**: When you create a rule, consider cases when the overwriting value is empty. For example, if you have a rule that overwrites eVar1 with eVar2 and eVar2 is empty, both variables are blanked out. Adobe recommends adding a condition that checks for a variable value before using it to overwrite another value.
* **Apply immediately on save**: Processing rules apply to collected data the moment that you save them. They do not apply retroactively to data that is already collected.
* **Processing order within rules**: If you have multiple processing rules, the order that they run matters. Make sure that if you use a given variable in multiple rules that they are executed in the correct order. If you overwrite eVar3 in rule 1, that original eVar3 value is not available in any subsequent rules.
* **Processing order within the data collection pipeline**: See [Processing order for data in Adobe Analytics](/help/technotes/processing-order.md) to understand where processing rules apply in the overall data collection pipeline.
* **Encoding**: Stick to UTF-8 encoding in almost all cases.
* **Case sensitivity**: String comparisons in processing rules are not case-sensitive. The string values that you use to overwrite values use the same rules as directly populating the variable.
* **Single report suite**: When you edit processing rules, they apply to only one report suite. Selecting multiple report suites in the Report suite manager forces you to select a single report suite. Once you have created or edited the desired processing rules, you can [copy those rules to other report suites](pr-copy.md).
* **No data exclusion**: Excluding data is not an intended feature of processing rules. Consider using [`abort`](/help/implement/vars/config-vars/abort.md) at the data collection level or use [VISTA rules](/help/technotes/vista.md) after data is collected.
* **Available variables**: Not all dimensions and metrics are available in processing rules. See [Dimensions and metrics available to processing rules](pr-variables.md) for the full list of what is supported.
* **Number of rules allowed**: Each report suite can contain up to 150 rules. Each rule can contain up to 30 conditions.

>[!MORELIKETHIS]
>
>![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Map context data variables into props and eVars with processing rules](https://experienceleague.adobe.com/en/docs/analytics-learn/tutorials/implementation/implementation-basics/map-contextdata-variables-into-props-and-evars-with-processing-rules){target="_blank"}
