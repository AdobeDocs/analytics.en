---
description: Rather than maintaining and uploading classifications each time your tracking codes change, you can create automatic, rule-based classifications and apply them across multiple report suites. Rules are processed at frequent intervals, depending on your volume of classification related traffic.
seo-description: Rather than maintaining and uploading classifications each time your tracking codes change, you can create automatic, rule-based classifications and apply them across multiple report suites. Rules are processed at frequent intervals, depending on your volume of classification related traffic.
seo-title: Classification Rule Builder workflow
solution: Analytics
subtopic: Classifications
title: Classification Rule Builder workflow
topic: Admin tools
uuid: a0648422-f11b-4e31-812e-5743db411b83
index: y
internal: n
snippet: y
---

# Classification Rule Builder workflow

Rather than maintaining and uploading classifications each time your tracking codes change, you can create automatic, rule-based classifications and apply them across multiple report suites. Rules are processed at frequent intervals, depending on your volume of classification related traffic.

## Getting Started with Classification Rules {#section_3FF666EF9D5B4E37A23B3FB400CDA2E6}

**[!UICONTROL Admin]** > **[!UICONTROL Classification Rule Builder]**

Here are the high-level steps you take to implement classification rules: 

<table id="table_DF3A0DFCA34C4A40BD7930E07FB28C00"> 
 <thead> 
  <tr> 
   <th colname="col01" class="entry"> Step </th> 
   <th colname="col02" class="entry"> Where Performed </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col01"> <p style="text-align: center;"><img href="assets/step1_icon.png" id="image_2B9410A896C64591A852DD0FFE5CB1BA" /> </p> <p>(Prerequisite) <a href="https://marketing.adobe.com/resources/help/en_US/reference/?f=c_classifications" format="https" scope="external"> Set up your classification schema</a>. </p> </td> 
   <td colname="col02"> <span class="uicontrol"> Admin</span> &gt; <span class="uicontrol"> Report Suites</span> &gt; <span class="uicontrol"> Edit Settings</span> &gt; <span class="term"> &lt;Traffic Classifications or Conversion Classifications&gt;</span> </td> 
   <td colname="col2"> <p>Choose a variable and define the classifications to use for that variable. </p> <p>Variables must have at least one classification column created before they are available for use in rules. </p> <p> Once classifications are enabled, you can use the importer and the rule builder to classify specific values. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p style="text-align: center;"><img href="assets/step2_icon.png" id="image_D19C29A109C844E598E7343E89E92B88" /> </p> <p> <a href="../../../components/c-classifications2/crb/classification-rule-set.md#task_86F216DFD2534FA181E64ABDF306782B" format="dita" scope="local"> Create a rule set. </a> </p> </td> 
   <td colname="col02"> <p><span class="uicontrol"> Admin</span> &gt; <span class="uicontrol"> Classification Rule Builder</span> &gt; <span class="uicontrol"> Add Rule Set</span> </p> </td> 
   <td colname="col2"> <p>A rule set is a group of classification rules for a specific variable. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p style="text-align: center;"><img href="assets/step3_icon.png" id="image_EDD01A95F5D7427A9AA97EA713735083" /> </p> <p>Configure report suites and variables. </p> </td> 
   <td colname="col02"> <p><span class="uicontrol"> Classification Rule Builder</span> &gt; <span class="term"> &lt;your rule set&gt;</span> </p> </td> 
   <td colname="col2"> <p>Apply the rule set to report suites and variables. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p style="text-align: center;"><img href="assets/step4_icon.png" id="image_6F19EBE7EDAF458A86E529247D9ECCB1" /> </p> <p> <a href="../../../components/c-classifications2/crb/classification-quickstart-rules.md#concept_CF2F64BD96454FBFAA84638FC7DEA263" format="dita" scope="local"> Add classification rules to the set</a>. </p> </td> 
   <td colname="col02"> <p><span class="uicontrol"> Classification Rule Builder</span> &gt; <span class="term"> &lt;your rule set&gt;</span> </p> </td> 
   <td colname="col2"> <p>Match a condition to a classification, and then specifying the action to take for the rule. </p> <p>Be familiar with the information in <a href="../../../components/c-classifications2/crb/classification-quickstart-rules.md#concept_A67A23F523844D37898583C632DB9D25" format="dita" scope="local"> How Rules Are Processed</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p style="text-align: center;"><img href="assets/step5_icon.png" id="image_061EB089A8EF4165B6A81CC645F2B43A" /> </p> <p><a href="../../../components/c-classifications2/crb/classification-quickstart-rules.md#task_618A1E7CC8664E728F312250E8367158" format="dita" scope="local"> Test a Classification Rule Set</a> </p> </td> 
   <td colname="col02"> <p> <span class="wintitle"> Testing</span> Page </p> </td> 
   <td colname="col2"> <p>You will want to test rules for validation by editing them in Draft mode. In Draft mode, rules cannot run. </p> <p> This step is important when using<a href="../../../components/c-classifications2/crb/classification-quickstart-rules.md#concept_8A63F9BCF9484963962E14E6286D312D" format="dita" scope="local"> regular expressions</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p style="text-align: center;"><img href="assets/step6_icon.png" id="image_0F2AD6AE741D4B63A9B69CD1EBCCB8B1" /> </p> <p> <a href="../../../components/c-classifications2/crb/classification-rule-definitions.md#section_4A5BF384EEEE4994B6DC888339833529" format="dita" scope="local"> Activate valid rules</a>. </p> </td> 
   <td colname="col02"> <span class="wintitle"> Rules</span> Page </td> 
   <td colname="col2"> <p>Once rules are valid, activate the rule set. </p> <p>You can overwrite existing keys, if necessary. See <a href="../../../components/c-classifications2/crb/classification-quickstart-rules.md#concept_A67A23F523844D37898583C632DB9D25" format="dita" scope="local"> How Rules Are Processed</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p style="text-align: center;"><img href="assets/step7_icon.png" id="image_89BFBE52C55044D08F27F9C0B6040F3F" /> </p> <p>(Optional) <a href="../../../components/c-classifications2/crb/classification-rule-definitions.md#section_4A5BF384EEEE4994B6DC888339833529" format="dita" scope="local"> Delete unwanted rules</a>. </p> </td> 
   <td colname="col02"> <p> <span class="wintitle"> Rules</span> Page </p> </td> 
   <td colname="col2"> <p>Delete unwanted rules from a set. </p> <p>Note:  Deleting rules does not delete classified data uploaded. </p> <p>See <a href="../../../components/c-classifications2/c-classifications-importer/t-delete-classification-data.md#task_105C3761180A4D21B8395730C39B5F89" format="dita" scope="local"> Delete classification data</a> if you need to delete classified data. </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>Groups with permissions to use the classification import tool can use classification rules. See [How Rules Are Processed](../../../components/c-classifications2/crb/classification-quickstart-rules.md#concept_A67A23F523844D37898583C632DB9D25) for important processing information.

**Additional Resources**

**Blog**: For additional information about this feature, see the Digital Marketing Blog - [Rule-based Classifications](http://blogs.adobe.com/digitalmarketing/analytics/rule-based-classifications-part-1-making-classifications-easier/?utm_source=feedburner&utm_medium=feed&utm_campaign=Feed%3A+AdobeDigitalMarketing+%28Adobe+Digital+Marketing+Blog%29).

**Video**: Visit [YouTube](https://www.youtube.com/watch?v=6laI5SBXY-I) to view the [!UICONTROL Classifications Overview] video. 
