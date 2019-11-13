---
description: Page variables directly populate a report, such as pageName, List Props, List Variables, and so on.
keywords: Analytics Implementation
solution: Analytics
subtopic: Variables
title: Page variables
topic:
uuid:
---

# List Variable

Also known as List Var. Similar to how List Props function, List Vars allow multiple values within the same image request. They also act similarly to eVars, which persist beyond the image request they were defined on. You can use these variables to see cause and effect among multiple elements on a single page, such as product lists, wish lists, lists of search refinements, or lists of display ads.

<!-- 

listN.xml

 -->

**Considerations**

* List Vars remember their specific values by referencing the VisitorID cookie in the visitor's browser.
* A limit of 250 maximum values are stored at one time per visitor. If 250 values per visitor are exceeded, the latest 250 values are used. Expiration for these values is based on the configured expiration for the variable.
* Each delimited value can contain a maximum of 255 characters (or less if using multi-byte characters). This is the maximum length of each element.
* There is no limit to the number of characters within this variable. The only exception to this limitation is within older Internet Explorer browsers, which impose a 2083-character limitation on all URL requests.
* A total of three List Vars are available per report suite.
* Using List Vars requires H23 code or higher.
* List Vars can be classified.
* If duplicate values are defined in the same image request, list vars deduplicate all instances of those values.
* The most granular list vars can be segmented is on a hit (or page view) level. If you have a list var with three values in the same image request, any segment rules that match one value will pull all three into reporting. Conversely, if an exclude rule is defined that matches a single value, all three values are excluded.

**Configuration** {#section_8CADFF581D2447518BA3F7F79B2D80A9}

You can access the configuration in the Admin Console and update it without Adobe Client Care having to get involved:

1. Go to  **[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Report Suites]** 
1. Select the report suite.
1. Click  **[!UICONTROL Edit Settings]** > **[!UICONTROL Conversion]** > **[!UICONTROL List Variables]** .

* **Name**: Each delimited value can contain a maximum of 255 characters (or less if using multi-byte characters). This is the maximum length of each element.
* **Value Delimiter**: The character used to separate values within the List Var. Most commonly these are characters such as commas, colons, pipes, or something similar.

  >[!NOTE]
  >
  >Multi-byte characters are not supported as delimiters in List Vars. The delimiter must be single byte.

* **Expiration**: Similar to eVar expiration, this determines the amount of time that can occur between the List Var and the conversion event for them to be related.

    * **At a page view or visit level**: Success events beyond the page view or visit would not link back to any values within the List Var.
    * **Based on a time period, such as day, week, month, etc**: Success events beyond the specified time period would not link back to any values within the List Var. A custom number of days can be defined as well.
    * **Specific conversion events**: Any other success events that fire after the specific event designated would not link back to any values within the List Var.
    * **Never**: Any amount of time can pass between the List Var and success event.

* **Allocation**: This setting determines how success events divide credit between values:

    * **Full**: All variable values defined prior to the variable's expiration get full credit for success events.
    * **Linear**: All variable values defined prior to the variable's expiration get credit divided credit for conversion events.
    * Variable values are never overwritten, but instead added to the values that get credit for success events.

* **Max Values**: Designates the number of active values allowed for this list variable. For example, if set to 3, only the last 3 values captured is saved and any previous values captured are discarded. Note that if multiple values for the same list var are sent in on the same hit and you have restricted using max values, each value will have the same timestamp and there is not guarantee as to which value is saved.

  A limit of 250 maximum values are stored at one time per visitor. If 250 values per visitor are exceeded, the latest 250 values are used. Expiration for these values is based on the configured expiration for the variable.

  The Max Values setting is useful to limit attribution to a specific number of values. For example, if a list var is set to "A,B,C" on the first page of a visit, then set to "X,Y,Z" on the next page, attribution is distributed to these six values based on the allocation. If you wanted to limit attribution to only "X,Y,Z", you can set max values to three.

To set up or edit List Vars, go to  **[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Report Suites]** > **[!UICONTROL Edit Settings]** > **[!UICONTROL Conversion]** > **[!UICONTROL List Variables]** .

**Implementation Examples** {#section_564AFE6A2F524BFEB372EC0F7FEBA656}

Each of the following examples use a comma for the value delimiter.

**Defining a single value within a List Var:**

```js
s.list1="Cat";
```

**Passing in multiple values:**

```js
s.list2="Tabby,Persian,Siamese"; 
s.list1="Product 1,Product 2,Product 3";
```

**Attributing revenue to a List Var:**

```js
//Define this code on the landing page: 
s.list3="Top Banner Ad,Side Bar Ad,Internal Campaign 1"; 
 
//Have these variables fire on the purchase confirmation page: 
s.products=";Kitten;1;50" 
s.events="purchase";
```

This result would show three line items with $50 each in revenue. (Top Banner Ad; Side Bar Ad; and Internal Campaign 1.) Note the total for this report deduplicates revenue, so the total would also reflect $50.

**Attributing revenue to a List Var that was set multiple times during a visit:**

**Allocation**: Full

**Expiration**: Visit 

<table id="table_09E1879B44624A858555449E2DC74E69"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Page </th> 
   <th colname="col2" class="entry"> s.list1 </th> 
   <th colname="col3" class="entry"> s.events/s.products </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Page 1 </td> 
   <td colname="col2"> <code> s.list1="value1,value2,value3"; </code> </td> 
   <td colname="col3"> (not set) </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Page 2 </td> 
   <td colname="col2"> <code> s.list1="value4,value5,value6"; </code> </td> 
   <td colname="col3"> <p> <code> s.events="purchase"; </code> </p> <p> <code> s.products=";product;1;200" </code> </p> </td> 
  </tr> 
 </tbody> 
</table>

**Result**: All values set in the list var1 at any point during the visit (value1,value2,value3,value4,value5,value6) get full credit for the purchase.

