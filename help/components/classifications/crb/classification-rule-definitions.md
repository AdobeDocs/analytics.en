---
description: Definitions of interface elements on the pages in the Classification Rule Builder.
subtopic: Classifications
title: Classification rules - definitions
feature: Admin Tools
uuid: 77af8669-6e11-435c-9cc3-b03eb627c855
exl-id: 514501d1-7e1b-45da-b8fe-c68331e59dab
---
# Classification rules - definitions

Definitions of interface elements on the pages in the Classification Rule Builder.

## Rules Page {#section_4A5BF384EEEE4994B6DC888339833529}

This page displays the rules in a rule set.

![](assets/classification_rules_page.png)

**Definitions** 

<table id="table_2B3A8BB7BDE14836ACA6A1D444B011CD"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Element </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Select Report Suites and Variables </p> </td> 
   <td colname="col2"> <p><b>Report Suite</b> </p> <p>The report suites to which the rule set applies. </p> <p><b>Variable</b> </p> <p>You can apply only one variable when creating a classification rule set. If you want to create multiple rule sets for one variable, you must apply each rule set to multiple report suites. </p> <p>Note: You can use only the variables you have access to in your report suites. Variables will display in the <span class="wintitle"> New Rule Set</span> panel only after they have at least one classification defined for that variable. </p> <p> You can create classifications on a variable in <span class="uicontrol"> Admin</span> &gt; <span class="uicontrol"> Report Suites</span> &gt; <span class="uicontrol"> Traffic</span> &gt; <span class="uicontrol"> Traffic Classifications</span> (or <span class="uicontrol"> Conversion</span> &gt; <span class="uicontrol"> Conversion Classifications</span>). Then select the variable, then click <span class="uicontrol"> Add Classification</span>. </p> <p>See <a href="https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/traffic-variables/traffic-classifications.html"  > Traffic Classifications</a> and <a href="https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/conversion-variables/conversion-classifications.html"  > Conversion Classifications</a> in Admin Help. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Activate</span> </p> </td> 
   <td colname="col2"> <p>Validates and activates a rule. Active rules process daily, examining classification data going back typically one month. The rules automatically check for new values and upload the classifications. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Deactivate</span> </p> </td> 
   <td colname="col2"> <p>Deactivates the rules so that you can edit and test them. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Configure Report Suites and Variables </p> </td> 
   <td colname="col2"> <p>Displays the <span class="wintitle"> Available Report Suites</span> page, where you can select one or more available report suites to use for all your rule sets. (This page also displays when you first run the <span class="wintitle"> Classification Rule Builder</span>.) </p> <p>This feature is intended to help reduce report suite load time, in the event that you have hundreds of available report suites. </p> <p>The report suites you select here are made available at the rule level, when you click <span class="uicontrol"> Add Suites</span> when creating a rule. </p> <p>Note: A report suite becomes available <span class="term"> only</span> when the report suites have at least one classification defined for the variable in <span class="wintitle"> Admin Tools</span>. <p>(See <span class="term"> Variable</span> in <a href="/help/components/classifications/crb/classification-rule-set.md"  > Classification Rule Sets</a> for an explanation about this prerequisite.) </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Rules overwrite any existing values </p> </td> 
   <td colname="col2"> <p> (Default setting) Always overwrite existing classification keys, including classifications uploaded via the importer (SAINT). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Rules overwrite only unset values </p> </td> 
   <td colname="col2"> <p>Only fill in blank (unset) cells. Existing classifications will not be changed. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Lookback window </p> </td> 
   <td colname="col2"> <p>When you activate and validate rules, you can specify whether the rules should overwrite existing classifications for affected keys. (Only classified keys that have been previously passed into <span class="keyword"> Adobe Analytics</span> within the time period you specify are affected.) </p> <p>If you to not specify a <span class="term"> lookback window</span>, the rules look back roughly one month (depending on current day of the month.) Existing classifications are never overwritten unless you enable this option. </p> <p><b>Dev Center</b>: Partners can create classification rules in the <span class="wintitle"> Dev Center</span>. These rules are deployed when the customer activates an integration. In the <span class="wintitle"> Dev Center</span>, the <span class="uicontrol"> Overwrite Since</span> option lets the partner specify whether the customer can determine the overwrite value when activating or editing an integration. </p> <p>See <a href="/help/components/classifications/crb/classification-quickstart-rules.md"  > How Rules Are Processed</a> for more information about rule processing. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <a href="/help/components/classifications/crb/classification-quickstart-rules.md"  > Add Rule </a> </td> 
   <td colname="col2"> <p>Lets you add rules to the rule set. </p> <p>Note:  If a value is matched twice or more in a set of rules, the system uses the last rule to classify the value. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Draft</span> </td> 
   <td colname="col2"> Lets you specify that a rule is in draft mode. Draft status lets you test the rule before running it. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Duplicate</span> </td> 
   <td colname="col2"> Duplicates (copies) a rule set, so that you can apply the rule set to another variable, or to the same variable in a different report suite. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <a href="/help/components/classifications/crb/classification-quickstart-rules.md"  > Test Rule Set </a> </p> </td> 
   <td colname="col2"> <p>Lets you test the validity of a rule set. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Matching Condition</span> </td> 
   <td colname="col2"> Specifies the conditions you want that for the rule. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Classification Action</span> </td> 
   <td colname="col2"> <p>Specifies the action to take when the Matching Condition occurs. </p> <p>For example, you set a Campaign Name to $2, which identifies position 2 in a tracking code as the Campaign Name. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> #</span> </td> 
   <td colname="col2"> <p>The rule number. </p> <p>See <a href="/help/components/classifications/crb/classification-quickstart-rules.md"  > How Rules Are Processed</a> for more information. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Select Rule Type</span> </td> 
   <td colname="col2"> <p>Each rule set applies to a specific variable. Valid selections are: </p> 
    <ul id="ul_6A8E06BB4AF2402B99C215823CB3D59D"> 
     <li id="li_5C702D4F460841D38A59621A5161A3BC">Starts With </li> 
     <li id="li_8052A741D9F34A2FBC136C181600193E">Ends With </li> 
     <li id="li_D0FA6EA4F09644FFBC9E6BC568BE80AC">Contains </li> 
     <li id="li_48675FE5253942ED887C6A72D1DCEF54"> <a href="/help/components/classifications/crb/classification-quickstart-rules.md"  > Regular Expression </a> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Enter Match Criteria</span> </td> 
   <td colname="col2"> The text pattern you are looking for in a key. These criteria can be search terms, characters, or regular expression. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Set Classification</span> </td> 
   <td colname="col2"> The classification column you want to set if the match criteria are met. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> To</span> </td> 
   <td colname="col2"> The value you want to specify for the selected classification column if the match criteria is met. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Filter </td> 
   <td colname="col2"> Lets you search for rules. </td> 
  </tr> 
 </tbody> 
</table>

## Regular Expression Page {#section_C932A5469E774841B2229965A154163C}

You can edit regular expressions on the [!UICONTROL Regular Expression] page.

![](assets/regex_tracking_code.png)

**Definitions** 

|  Element  | Description  |
|---|---|
|  Sample Key  | The test string to use. For example, you can create a classification from specific characters in a tracking code. You can match particular characters, words, or patterns of characters.  |
|  Match Groups  | Shows how the regular expression corresponds to the campaign ID characters, so that you can classify a position in the campaign ID.  |
|  Match Result  | Displays the parts of a string that successfully match the regular expression.  |

See [Regular Expressions in Classification Rules](/help/components/classifications/crb/classification-quickstart-rules.md).

## Testing Page {#section_EC926F97901C4E65901413F9683AA70A}

This page lets you test rules in a set.

**Definitions** 

|  Element  | Description  |
|---|---|
|  Run Test  | When you test the rule set, use keys from the report to see how they will be impacted by the rule set.  |
|  Filter  |Filters the values in the [!UICONTROL Results] panel.  |
