---
description: Classification rules regularly look for unclassified terms. If a rule match is found, the rules add the terms to your classification data tables automatically. You can also use classification rules to overwrite existing keys.
seo-description: Classification rules regularly look for unclassified terms. If a rule match is found, the rules add the terms to your classification data tables automatically. You can also use classification rules to overwrite existing keys.
seo-title: Classification rules
solution: Analytics
subtopic: Classifications
title: Classification rules
topic: Admin tools
uuid: 48d0ee37-f0a6-492c-bc44-403d853d7a7b
index: y
internal: n
snippet: y
---

# Classification rules

Classification rules regularly look for unclassified terms. If a rule match is found, the rules add the terms to your classification data tables automatically. You can also use classification rules to overwrite existing keys.

## Classification rules {#concept_CF2F64BD96454FBFAA84638FC7DEA263}

Classification rules regularly look for unclassified terms. If a rule match is found, the rules add the terms to your classification data tables automatically. You can also use classification rules to overwrite existing keys. 

**[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Classification Rule Builder]**

The Rule Builder lets you create a *`classification rule set`*, which is a list of *`classification rules`*. A rule matches criteria you specify, then performs an action.

Classification rules are convenient for:

* **Email** and **Display ads**: Create classification rules to group individual display ad campaigns so that you can earn how the Display campaigns are performing against email campaigns. 

* **Tracking codes**: Create classification rules to categorize key values derived from strings in tracking codes, and match them to specific criteria you define. 
* **Search terms**: Use [regular expressions](../../c_classifications2/crb/classification_quickstart_rules.md#concept_8A63F9BCF9484963962E14E6286D312D) and wildcards to simplify classifying of search terms. For example if a search term contains *`baseball`*, you can set a *`Sports League`* classification to *`MLB`*.

For example, assume that a tracking code for an email campaign ID is:

`em:Summer:2013:Sale`.

You can set up three rules in a rule set that identify the parts of the string, then classify the values: 

|  #  | Select Rule Type  | Enter Match Criteria  | Set Classification  | To  |
|---|---|---|---|---|
|  1  | Starts With  | em:  | Channel  | Email  |
|  2  | Ends With  | Sale  | Type  | Sale  |
|  3  | Contains  | 2013  | Year  | 2013  |

## How Rules Are Processed {#concept_A67A23F523844D37898583C632DB9D25}

Important information about how classification rules are processed.

<!-- 

about_classification_rules.xml

 -->

* [Important Information about Rules](about_classification_rules.md#section_0BD46702FBEC4D98A4DD2EA0BD428046) 
* [When Do Rules Not Classify Keys?](about_classification_rules.md#section_4481E88CA28246B6B19EA16E2D83A3A8) 
* [About Rule Priority](../../c_classifications2/crb/classification_quickstart_rules.md#concept_93527FEB3C9B48FB96FB7DF857E5F980)

>[!NOTE]
>
>The [!UICONTROL Rule Builder] does not support Numeric 2 classifications.

## Important Information about Rules {#section_0BD46702FBEC4D98A4DD2EA0BD428046}

* Specify [group permissions](https://marketing.adobe.com/resources/help/en_US/reference/?f=groups) for classifications in [!UICONTROL Admin Tools]. 

* **Regular expressions**: Help is available under [Regular Expressions in Classification Rules](../../c_classifications2/crb/classification_quickstart_rules.md#concept_8A63F9BCF9484963962E14E6286D312D). 

* **Report suites**: You cannot choose a classification until at least one report suite is selected. You cannot apply the report suite until you have created the rule set and assigned a variable.

  When you test the rule set, use keys (the variable being classified) from the report to see how they will be impacted by the rule set. (The [key](../../c_classifications2/c_classifications_importer/c_saint_data_files.md#concept_0B77B3079B5C414F9956058688990443) is the variable being classified, or the first column in the classification upload table.) 

* **Rule priority**: If a key matches multiple rules that set the same classification (in the [!UICONTROL Set Classification] column), the last rule that matches the classification is used. See [About Rule Priority](../../c_classifications2/crb/classification_quickstart_rules.md#concept_93527FEB3C9B48FB96FB7DF857E5F980). 

* **Limits on number of rules**: No set limit exists for the number of rules you can create. However, a large number of rules may impact browser performance. 
* **Processing**: Rules are processed at frequent intervals, depending on your volume of classification related traffic.

  Active rules process every four hours, examining classification data going back typically one month. The rules automatically check for new values and upload the classifications using the importer. 

* **Overwriting existing classifications**: See [When Do Rules Not Classify Keys?](../../c_classifications2/crb/classification_quickstart_rules.md#section_4481E88CA28246B6B19EA16E2D83A3A8) If necessary, you can delete or remove existing classifications, using the importer.

## When Do Rules Not Classify Keys? {#section_4481E88CA28246B6B19EA16E2D83A3A8}

When you activate rules, you can overwrite existing classifications. In the following situations, a classification rule does not classify a [key](../../c_classifications2/c_classifications_importer/c_saint_data_files.md#concept_0B77B3079B5C414F9956058688990443)(variable) if:

* The key is already classified and you do not select [Overwrite Classifications](../../c_classifications2/crb/classification_rule_definitions.md#overwrite_classifications).

  You can overwrite classifications when [adding and activating](../../c_classifications2/crb/classification_quickstart_rules.md#task_86F216DFD2534FA181E64ABDF306782B) a rule, and when activating a data connectors integration. (For data connectors, rules are created by partners in the Dev Center and displayed in the [!UICONTROL Classification Rule Builder].) 

* A classified key has not appeared in the data after a time frame specified when overwriting a key, even after you enable [Overwrite Classifications](../../c_classifications2/crb/classification_rule_definitions.md#overwrite_classifications). 
* The key is not classified and the key is never passed into [!DNL Adobe Analytics] after the time frame beginning about one month ago. 

  >[!NOTE]
  >
  >In reports, classifications apply to any time frame specified, whenever a key exists. The date range of a report does not affect reporting.

![](assets/overwrite_keys.png)

## Regular Expressions in Classification Rules {#concept_8A63F9BCF9484963962E14E6286D312D}

Use regular expressions to match consistently formatted string values with a classification. For example, you can create a classification from specific characters in a tracking code. You can match particular characters, words, or patterns of characters.

<!-- 

regex_classification_rules.xml

 -->

* [Regular Expression - Tracking Code Example](../../c_classifications2/crb/classification_quickstart_rules.md#section_2EF7951398EB4C2F8E52CEFAB4032669) 
* [Regular Expression - Classifying a Specific Character](../../c_classifications2/crb/classification_quickstart_rules.md#section_5D300C03FA484BADACBFCA983E738ACF) 
* [Regular Expressions - Matching Tracking Codes of Varying Length](../../c_classifications2/crb/classification_quickstart_rules.md#section_E86F5BF5C2F44ABC8FFCE3EA67EE3BB2) 
* [Regular Expressions - "Does Not Contain" Example](../../c_classifications2/crb/classification_quickstart_rules.md#section_FCA88A612A4E4B099458E3EF7B60B59C) 
* [Regular Expressions - Reference Table](../../c_classifications2/crb/classification_quickstart_rules.md#section_0211DCB1760042099CCD3ED7A665D716)

>[!NOTE]
>
>As a best practice, regular expressions are best suited for tracking codes that use delimiters.

## Regular Expression - Tracking Code Example {#section_2EF7951398EB4C2F8E52CEFAB4032669}

>[!NOTE]
>
>If the tracking code is URL encoded, it will **not** be classified by the Rules Builder.

In this example, assume you want to classify the following campaign ID:

[!UICONTROL Sample Key]: `em:JuneSale:20130601`

The parts of the tracking code you want to classify are:

* `em` = email 
* `JuneSale` = campaign name 
* `20130601` = date

[!UICONTROL Regular Expression]: `^(.+)\:(.+)\:(.+)$`

How the regular expression correlates to the campaign ID:

![](assets/regex.png)

[!UICONTROL Match Groups]: Shows how the regular expression corresponds to the campaign ID characters, so that you can classify a position in the campaign ID.

![](assets/regex_tracking_code.png)

This example tells the rule that the campaign date `20140601` is at the third group `(.+)`, identified by `$3`.

** [!UICONTROL Rule Builder] **

In the [!UICONTROL Rule Builder], configure the rule as follows: 

|  #  | Select Rule Type  | Enter Match Criteria  | Set Classification  | To  |
|---|---|---|---|---|
|  1  | Regular Expression  | ^(.+)\:(.+)\:(.+)$  | Campaign Date  | $3  |

**Syntax** 

<table id="table_4FA742E72A2D404280424B2111F395A0"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Regular Expression </th> 
   <th colname="col2" class="entry"> String or Match Result </th> 
   <th colname="col3" class="entry"> Corresponding Match Groups </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> ^(.+)\:(.+)\:(.+)$</span> </p> </td> 
   <td colname="col2"> <p>em:JuneSale:20130601 </p> </td> 
   <td colname="col3"> <p>$0: em:JuneSale:20130601 </p> <p>$1: em </p> <p>$2: JuneSale </p> <p>$3: 20130601 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Building the syntax </td> 
   <td colspan="2"> <p>^ = starts the line </p> <p>() = groups characters and lets you extract matching characters in the parentheses. </p> <p>(.+) = captures one (.) character and (+) any more </p> <p>\ = start of a string. </p> <p>$ = indicates that the preceding character (or character group) is the last in the line. </p> </td> 
  </tr> 
 </tbody> 
</table>

See [Regular Expressions - Reference Table](../../c_classifications2/crb/classification_quickstart_rules.md#section_0211DCB1760042099CCD3ED7A665D716) for information about what the characters in a regular expression mean.

## Regular Expression - Classifying a Specific Character {#section_5D300C03FA484BADACBFCA983E738ACF}

One way to use a regular expression is to classify a specific character in a string of characters. For example, assume that the following tracking code contains two important characters:

[!UICONTROL Sample Key]: `4s3234`

* `4` = brand name 
* `s` = identifies a search engine, such as Google

![](assets/regex_char_position.png)

** [!UICONTROL Rule Builder] **

In the [!UICONTROL Rule Builder], configure the rule as follows: 

<table id="table_7E52B986A50E446DB431B2A2C4AA8958"> 
 <thead> 
  <tr> 
   <th colname="col01" class="entry"> # </th> 
   <th colname="col1" class="entry"> Select Rule Type </th> 
   <th colname="col2" class="entry"> Enter Match Criteria </th> 
   <th colname="col3" class="entry"> Set Classification </th> 
   <th colname="col4" class="entry"> To </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col01"> </td> 
   <td colname="col1"> Regular Expression </td> 
   <td colname="col2"> ^.(s).*$ </td> 
   <td colname="col3"> Brand and Engine </td> 
   <td colname="col4">$0 <p>(Captures the first two characters for brand name and search engine.) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> </td> 
   <td colname="col1"> Regular Expression </td> 
   <td colname="col2"> ^.(s).*$ </td> 
   <td colname="col3"> Search Engine </td> 
   <td colname="col4">$1 <p>(Captures the second character for Google.) </p> </td> 
  </tr> 
 </tbody> 
</table>

## Regular Expressions - Matching Tracking Codes of Varying Length {#section_E86F5BF5C2F44ABC8FFCE3EA67EE3BB2}

This example shows how to identify specific characters between colon delimiters when you have tracking codes of varying lengths. Adobe recommends using one regular expression for each tracking code.

Sample Keys:

* `a:b` 
* `a:b:c` 
* `a:b:c:d`

**Syntax**

![](assets/regex_b.png)

![](assets/regex_varying_length.png)

** [!UICONTROL Rule Builder] **

In the [!UICONTROL Rule Builder], configure the rule as follows: 

<table id="table_BA6AFB62483E48D998E08B4BB7E7F2E0"> 
 <thead> 
  <tr> 
   <th colname="col01" class="entry"> # </th> 
   <th colname="col1" class="entry"> Select Rule Type </th> 
   <th colname="col2" class="entry"> Enter Match Criteria </th> 
   <th colname="col3" class="entry"> Set Classification </th> 
   <th colname="col4" class="entry"> To </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col01"> </td> 
   <td colname="col1"> <p>Regular Expression </p> <p>For match string <b>a</b>:b </p> </td> 
   <td colname="col2"> <p> <span class="codeph"> ^([^\:]+)\:([^\:]+)$</span> </p> </td> 
   <td colname="col3"> a </td> 
   <td colname="col4"> $1 </td> 
  </tr> 
  <tr> 
   <td colname="col01"> </td> 
   <td colname="col1"> <p>Regular Expression </p> <p>For match string a:<b>b</b> </p> </td> 
   <td colname="col2"> <p> <span class="codeph"> ^([^\:]+)\:([^\:]+)$</span> </p> </td> 
   <td colname="col3"> b </td> 
   <td colname="col4"> $2 </td> 
  </tr> 
  <tr> 
   <td colspan="5"> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> </td> 
   <td colname="col1"> <p>Regular Expression </p> <p>For match string <b>a</b>:b:c </p> </td> 
   <td colname="col2"> <p> <span class="codeph"> ^([^\:]+)\:([^\:]+)\:([^\:]+)$</span> </p> </td> 
   <td colname="col3"> a </td> 
   <td colname="col4"> $1 </td> 
  </tr> 
  <tr> 
   <td colname="col01"> </td> 
   <td colname="col1"> <p>Regular Expression </p> <p>For match string a:<b>b</b>:c </p> </td> 
   <td colname="col2"> <p> <span class="codeph"> ^([^\:]+)\:([^\:]+)\:([^\:]+)$</span> </p> </td> 
   <td colname="col3"> b </td> 
   <td colname="col4"> $2 </td> 
  </tr> 
  <tr> 
   <td colname="col01"> </td> 
   <td colname="col1"> <p>Regular Expression </p> <p>For match string a:b:<b>c</b> </p> </td> 
   <td colname="col2"> <span class="codeph"> ^([^\:]+)\:([^\:]+)\:([^\:]+)$</span> </td> 
   <td colname="col3"> c </td> 
   <td colname="col4"> $3 </td> 
  </tr> 
  <tr> 
   <td colspan="5"> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> </td> 
   <td colname="col1"> <p>Regular Expression </p> <p>For match string a:b:c:<b>d</b> </p> </td> 
   <td colname="col2"> <p> <span class="codeph"> ^([^\:]+)\:([^\:]+)\:([^\:]+)\:([^\:])$</span> </p> </td> 
   <td colname="col3"> d </td> 
   <td colname="col4"> $4 </td> 
  </tr> 
 </tbody> 
</table>

## Regular Expressions - "Does Not Contain" Example {#section_FCA88A612A4E4B099458E3EF7B60B59C}

This example provides a regular expression that matches any string that does not contain specific characters, in this case `13`.

Regular expression:

`^(?!.*13.*).*$`

Test strings:

```
a:b:
a:b:1313
c:d:xoxo
c:d:yoyo
```

Match results:

```
a:b:
c:d:xoxo
c:d:yoyo
```

In this result, `a:b:1313` does not indicate a match.

## Regular Expressions - Reference Table {#section_0211DCB1760042099CCD3ED7A665D716}

|  (?ms)  | Makes the entire regular expression match against a multi-line input, allowing the . wildcard to match any newline characters  |
|---|---|
|  (?i)  | Makes the entire regular expression case insensitive  |
|  [abc]  | A single character of: a, b or c  |
|  [^abc]  | Any single character except: a, b, or c  |
|  [a-z]  | Any single character in the range a-z  |
|  [a-zA-Z]  | Any single character in the range a-z or A-Z  |
|  ^  | Start of line (matches the beginning of the line)  |
|  $  | Match the end of the line (or before newline at the end)  |
|  \A  | Start of string  |
|  \z  | End of string  |
|  .  | Match any character (except a new line)  |
|  \s  | Any whitespace character  |
|  \S  | Any non-whitespace character  |
|  \d  | Any digit  |
|  \D  | Any non-digit  |
|  \w  | Any word character (letter, number, underscore)  |
|  \W  | Any non-word character  |
|  \b  | Any word boundary  |
|  (...)  | Capture everything enclosed  |
|  (a|b)  | a or b  |
|  a?  | Zero or one of a  |
|  a&#42;  | Zero or more of a  |
|  a+  | One or more of a  |
|  a{3}  | Exactly 3 of a  |
|  a{3,}  | 3 or more of a  |
|  a{3,6}  | Between 3 and 6 of a  |

A good resource for testing regular expression validity is http://rubular.com/. 

## About Rule Priority {#concept_93527FEB3C9B48FB96FB7DF857E5F980}

If a key is matched to multiple rules, and it sets the same classification column shown in the [!UICONTROL Set Classification] column, the last rule is used. As such, you might want to rank the most important last in your rule set.

<!-- 

rule_priority.xml

 -->

If you create multiple rules that do not share the same classification, processing order does not matter.

What follows a search-term rule example that classifies search types for an athlete: 

|  Rule Number  | Rule Type  | Match  | Set Classification  | To  |
|---|---|---|---|---|
|  1  | Contains  | Cowboys  | Search Type  | Team  |
|  2  | Contains  | Fantasy  | Search Type  | Fantasy  |
|  3  | Contains  | Romo  | Search Type  | Player  |

If a user searches for *`Cowboys fantasy Tony Romo`*, the term *`Player`* is classified, because it matches the last given classification shown in the Set Classification column.

Similarly, suppose you set up two rules in a set for the following search terms: 

|  Rule Number  | Rule Type  | Match  | Set Classification  | To  |
|---|---|---|---|---|
|  1  | Contains  | Cowboys  | City  | Dallas  |
|  2  | Contains  | Broncos  | City  | Denver  |

A user searches for *`Cowboys vs. Broncos`*. If the rule builder finds a conflict in rule matching, the classification for the second rule (Denver) applies to this search. 

## Add a Classification Rule to a Rule Set {#task_86F216DFD2534FA181E64ABDF306782B}

<!-- 

t_classification_rule.xml

 -->

Steps that describe how to add or edit a classification rule. 

Add rules by matching a condition to a classification, and specifying the action.

>[!NOTE]
>
>In this procedure, you must apply the rules to one or more report suites. The recommended number of rules per rule set is between 500 and 1000, although there are no limits. If you have over 100 rules, consider simplifying your rule set by using [sub-classifications](../../c_classifications2/c_sub-classifications.md#concept_19EE5513A7DC43C38CC396E96F306CFE).

1. [Create a Classification Rule Set](../../c_classifications2/crb/classification_rule_set.md#task_86F216DFD2534FA181E64ABDF306782B) .
1. On the rule set page, click **[!UICONTROL Add Rule]**.

   ![](assets/add_rule.png)

1. Next to **[!UICONTROL Report Suites]**, click **[!UICONTROL Add Suites]** to specify one or more report suites to assign to this rule set.

       The **[!UICONTROL Select Report Suites]** page displays.

       >[!NOTE]
       >
       >Report suites display on this page *`only`* when the following conditions are met:        >
       >
       >
       >* The report suites have at least one classification defined for that variable in [!UICONTROL Admin Tools]. 
       >
       >
       >  (See *`Variable`* in [Classification Rule Sets](../../c_classifications2/crb/classification_rule_set.md#concept_CD3D510F5070486584F3BB535AE41524) for an explanation about this prerequisite.) 
       >
       >* You selected the report suite on the **[!UICONTROL Available Report Suites]** page, which displays after you click [Add Rule Set](t_classification_rule_set.md#task_86F216DFD2534FA181E64ABDF306782B) to create the rule set. 
       >
       >
       >

1. Specify whether to overwrite existing values:

       | **Rules overwrite any existing values** | (Default setting) Always overwrite existing classification keys, including classifications uploaded via the importer (SAINT). |
       |---|---|
       | **Rules overwrite only unset values** | Only fill in blank (unset) cells. Existing classifications will not be changed. |

1. [Define the rule or rules](../../c_classifications2/crb/classification_rule_definitions.md#section_4A5BF384EEEE4994B6DC888339833529).

   ![Step Result](assets/classification_rules_page.png)

   For examples of building rules, see [Classifications Rule Builder](../../c_classifications2/crb/classification_rule_builder.md#concept_C1F219E622044D43852EF5168FF7192A) and [Regular Expressions in Classification Rules](../../c_classifications2/crb/classification_quickstart_rules.md#concept_8A63F9BCF9484963962E14E6286D312D).

   >[!NOTE]
   >
   >If a key matches multiple rules that set the same classification (in the Set Classification column), the last rule that matches the classification is used. See [About Rule Priority](rule_priority.md#concept_93527FEB3C9B48FB96FB7DF857E5F980) for more information about sorting rules.

1. [Test your rule set](../../c_classifications2/crb/classification_quickstart_rules.md#task_618A1E7CC8664E728F312250E8367158).
1. After testing, click **[!UICONTROL Active]** to validate and activate the rule.

   Activating a rule automatically builds the file and uploads it for you.

   Field definitions: See [Classification Rule Builder](../../c_classifications2/crb/classification_rule_definitions.md#concept_6CAEFB1CA4564E2CA5808097C11EF468) for complete definitions of interface options on this page. 

## Test a Classification Rule Set {#task_618A1E7CC8664E728F312250E8367158}

<!-- 

t_classifications_test_rule.xml

 -->

Steps that describe how to test a classification rule or rule set. Running a test checks all the rules in a set.

1. [Create a Classification Rule Set](../../c_classifications2/crb/classification_rule_set.md#task_86F216DFD2534FA181E64ABDF306782B) .
1. On the [!UICONTROL Classification Rule Builder], click the rule set name.
1. Ensure that the rule set is associated with a report suite.
1. On the rule editor, click **[!UICONTROL Test Rule Set]**.

   ![Step Result](assets/classification_test_rule_set.png)

1. Type or paste test keys in the [!UICONTROL Sample Keys] field.

   Sample keys include:

* Tracking codes 
* Search keywords or phrases

   See [Regular Expressions in Classification Rules](../../c_classifications2/crb/classification_quickstart_rules.md#concept_8A63F9BCF9484963962E14E6286D312D) for information about testing regular expressions. 
1. Click **[!UICONTROL Run Test]**.

   Rules that match are displayed in the [!UICONTROL Results] table. 
1. (Optional) Click **[!UICONTROL Activate]** to activate the rule, and to overwrite existing classifications.

   See for more information about using rules to overwrite existing classifications. 

## Validate and Activate Classification Rules {#task_2B4FA41F1EE64F4AAC6170C5EFC066AC}

<!-- 

t_validate_rules.xml

 -->

Steps that describe how to validate and activate classification rules.

1. [Create a Classification Rule Set](../../c_classifications2/crb/classification_rule_set.md#task_86F216DFD2534FA181E64ABDF306782B) , then [add classification rules](../../c_classifications2/crb/classification_quickstart_rules.md#task_86F216DFD2534FA181E64ABDF306782B) to the set.
1. On the rule editor, click **[!UICONTROL Activate]**.

   ![](assets/overwrite_keys.png)

1. (Optional) To overwrite classifications, enable **[!UICONTROL Overwrite classifications for]** *`<selection>`*.

   This option lets you overwrite existing classifications for affected keys.

   See [Rules Page](../../c_classifications2/crb/classification_rule_definitions.md#section_4A5BF384EEEE4994B6DC888339833529) for a definition of this option. 
