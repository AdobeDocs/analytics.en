---
description: Rather than maintaining and uploading classifications each time your tracking codes change, you can create automatic, rule-based classifications and apply them across multiple report suites. Rules are processed at frequent intervals, depending on your volume of classification related traffic.
subtopic: Classifications
title: Classification Rule Builder workflow
feature: Admin Tools
uuid: edb1f07e-fa86-4055-8f4b-cce2d370edbb
exl-id: cdb20dcc-0635-4d5e-9c54-f102d17a0a3d
---
# Classification Rule Builder workflow

Rather than maintaining and uploading classifications each time your tracking codes change, you can create automatic, rule-based classifications and apply them across multiple report suites. Rules are processed at frequent intervals, depending on your volume of classification related traffic.

## Important Notice before you get started

Keep this in mind before you start using classification rules: 

* Sub-classifications are not supported with Classification Rule Builder (CRB). 
* Our current classification system can only export up to 10 million rows at a time.
* When CRB requests an export, it pulls both classified AND unclassified values, with unclassified values coming through at the end of the export. This means that, over time, you could fill up 10 million classified values - without ever getting to the unclassified values.
* Because the architecture is set up in a way that CRB could be pulling from "n" number of servers, this can lead to inconsistencies as to which servers get picked up and in what order. For that reason, it is very difficult to get to unclassified values.

This is the **workaround** for those who have more than 10 million classified values for a dimension: You will need to export unclassified values via FTP, in 10-million batches, and manually classify them.

## Getting Started with Classification Rules {#section_3FF666EF9D5B4E37A23B3FB400CDA2E6}

**[!UICONTROL Admin]** > **[!UICONTROL Classification Rule Builder]**

Here are the high-level steps you take to implement classification rules: 

| Step | Where Performed | Description |
|--- |--- |--- |
| Step 1 (Prerequisite): [Set up your classification schema](https://experienceleague.adobe.com/docs/ analytics/components/classifications/c-classifications.html).|[!UICONTROL Admin] > [!UICONTROL Report Suites] > [!UICONTROL Edit Settings] > &lt;Traffic Classifications or Conversion Classifications&gt; |Choose a variable and define the classifications to use for that variable. <br>Variables must have at least one classification column created before they are available for use in rules.<br>Once classifications are enabled, you can use the importer and the rule builder to classify specific values.|
| Step 2: [Create a rule set](/help/components/classifications/crb/classification-rule-set.md).|[!UICONTROL Admin] >  [!UICONTROL Classification Rule Builder] > [!UICONTROL Add Rule Set]|A rule set is a group of classification rules for a specific variable.|
| Step 3: Configure report suites and variables.|[!UICONTROL Classification Rule Builder] >  &lt;your rule set&gt;|Apply the rule set to report suites and variables.|
| Step 4: [Add classification rules to the set](/help/components/classifications/crb/classification-quickstart-rules.md).|[!UICONTROL Classification Rule Builder] >  &lt;your rule set&gt;|Match a condition to a classification, and then specifying the action to take for the rule.  Be familiar with the information in  [How Rules Are Processed](/help/components/classifications/crb/classification-quickstart-rules.md).|
| Step 5: [Test a Classification Rule Set](/help/components/classifications/crb/classification-quickstart-rules.md)|[!DNL Testing Page]|You will want to test rules for validation by editing them in Draft mode. In Draft mode, rules cannot run.<br>This step is important when using [regular expressions](/help/components/classifications/crb/classification-quickstart-rules.md).|
| Step 6: [Activate valid rules](/help/components/classifications/crb/classification-rule-definitions.md).|[!DNL Rules Page]|Once rules are valid, activate the rule set.  You can overwrite existing keys, if necessary. See [How Rules Are Processed](/help/components/classifications/crb/classification-quickstart-rules.md).|
| Step 7 (Optional): [Delete unwanted rules](/help/components/classifications/crb/classification-rule-definitions.md).|[!DNL Rules Page]|Delete unwanted rules from a set.<br>Note:  Deleting rules does not delete classified data uploaded.  See  [Delete classification data](/help/components/classifications/importer/t-delete-classification-data.md) if you need to delete classified data.|

>[!NOTE]
>
>Groups with permissions to use the classification import tool can use classification rules. See [How Rules Are Processed](/help/components/classifications/crb/classification-quickstart-rules.md) for important processing information.

**Additional Resources**

**Blog**: For additional information about this feature, see the Digital Marketing Blog: [Rule-based Classifications](https://theblog.adobe.com/rule-based-classifications-part-1-making-classifications-easier/).

**Video**: View the [Classifications Overview](https://experienceleague.adobe.com/docs/ analytics-learn/tutorials/components/classifications/overview-of-classifications.html) video.
