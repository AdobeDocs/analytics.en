---
description: You can filter on dimensions that you add to the Row Labels grid. Filters narrow the data returned by requests and can be applied from the Pivot or Custom Layouts. When you configure dimension filtering from the Pivot Layout, you can additionally specify the number of entries from cell.
title: Filter dimensions overview
uuid: c54d5add-f278-476d-8f14-73f1c2e37671
feature: Report Builder
role: User, Admin
exl-id: eded07d5-3c06-419b-92fd-1a48856ac293
---
# Filter dimensions overview

You can filter on dimensions that you add to the Row Labels grid. Filters narrow the data returned by requests and can be applied from the Pivot or Custom Layouts. When you configure dimension filtering from the Pivot Layout, you can additionally specify the number of entries from cell.

The selected filter form is populated based on the element & metric that is selected in the report builder request.

## Define filter - values and special characters {#section_15840216A4044C40974945FAA435AD93}

Information about filters in the **[!UICONTROL Most Popular Filter]** > **[!UICONTROL Define Filter]** panel.

![](assets/define_filter.png)

The following tables provide examples and information about filters: 

<table id="table_8AC3A26FF02143DBA949B30F2A46CF11"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Filter </th> 
   <th colname="col02" class="entry"> Description </th> 
   <th colname="col2" class="entry"> Example Filter </th> 
   <th colname="col3" class="entry"> Match Results </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Contains all terms </p> </td> 
   <td colname="col02"> <p>Contains every space-delimited value in any order. </p> </td> 
   <td colname="col2"> <p>a b c </p> </td> 
   <td colname="col3"> <p>Matches <span class="term"> a b c</span>and <span class="term"> b a c</span>, and so on. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Contains any term </p> </td> 
   <td colname="col02"> <p>Contains at least one of the filters (space-delimited). </p> </td> 
   <td colname="col2"> <p>A B C </p> </td> 
   <td colname="col3"> <p>Matches <span class="term"> A1</span>, <span class="term"> B2</span>, <span class="term"> C3</span>, but not <span class="term"> D4</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Contains the phrase </p> </td> 
   <td colname="col02"> <p>Contains the search filter and possibly other terms. </p> </td> 
   <td colname="col2"> <p>abc </p> </td> 
   <td colname="col3"> <p>Matches <span class="term"> abc</span> and <span class="term"> abc def</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Does not contain any term </p> </td> 
   <td colname="col02"> <p>Returns everything unless it contains a value you enter. </p> </td> 
   <td colname="col2"> <p>a b c </p> </td> 
   <td colname="col3"> <p>Matches <span class="term"> d e f</span> but not <span class="term"> c d e f</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Does not contain the phrase </p> </td> 
   <td colname="col02"> <p>Returns everything that does not contain your phrase. </p> </td> 
   <td colname="col2"> <p>abc </p> </td> 
   <td colname="col3"> <p>Excludes <span class="term"> abc</span>, <span class="term"> abc def</span> and matches <span class="term"> def</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Equals </p> </td> 
   <td colname="col02"> <p>Returns an exact match. </p> </td> 
   <td colname="col2"> <p>abc </p> </td> 
   <td colname="col3"> <p> <span class="term"> abc</span> is returned, and nothing else. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Does not equal </p> </td> 
   <td colname="col02"> <p>Returns anything that does not exactly match your entry. </p> </td> 
   <td colname="col2"> <p>a </p> </td> 
   <td colname="col3"> <p>Does not match <span class="term"> a</span>. </p> <p>Matches <span class="term"> a b c</span>. </p> <p>Matches <span class="term"> abc</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Starts with </p> </td> 
   <td colname="col02"> <p>Returns results that start with a specific value. </p> </td> 
   <td colname="col2"> <p>abc </p> </td> 
   <td colname="col3"> <p>Matches <span class="term"> abcd</span> but not <span class="term"> 1abc</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Ends with </p> </td> 
   <td colname="col02"> <p>Returns results that end with the specific value. </p> </td> 
   <td colname="col2"> <p>xyz </p> </td> 
   <td colname="col3"> <p>Matches <span class="term"> wxyz</span> but not <span class="term"> wxyz0</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Advanced (special characters) </p> </td> 
   <td colname="col02"> <p>Lets you regex characters: </p> <p> <code> "", ^, -, *, $, | </code> </p> </td> 
   <td colname="col2"> <p>"^Home*Page$" | sports </p> </td> 
   <td colname="col3"> <p> This defines a filter that starts with <span class="term"> Home</span>, and then looks for zero or more characters, and then ends with <span class="term"> Page</span>. </p> <p>Also, any page with <span class="term"> sports</span> in it. </p> <p>A few example matches: </p> 
    <ul id="ul_72D76C5AFEAF405E8A0E4E3C604D10AE"> 
     <li id="li_4D490059B667450DA8A0103167C7B391">HomePage </li> 
     <li id="li_1351619156274092AEB2771D882AD357">Home and (other characters) Page </li> 
     <li id="li_940EAA99A8CF49308E8471065EB317B1">Home sports </li> 
     <li id="li_50A895F14A454BE9BF06EE0F07F99B3B">sports Page </li> 
     <li id="li_F3CE0D07941D4C2485D2DE0B73E00677">sports </li> 
     <li id="li_E84C15C061824A5D922D9900392F2996">xyz sports abc </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

<table id="table_8BBB06C8860745DEA41B39673699DC0F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Special Characters </th> 
   <th colname="col2" class="entry"> Purpose </th> 
   <th colname="col3" class="entry"> Notes </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> " " </td> 
   <td colname="col2"> Equals </td> 
   <td colname="col3"> <p>Not escaped unless it is not paired with another quote. For example, <span class="term"> 17" Display</span> is not a phrase. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> * </td> 
   <td colname="col2"> Wildcard </td> 
   <td colname="col3"> <p>Same as the asterisk used in a regular expression. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> ^ </td> 
   <td colname="col2"> Starts with </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> $ </td> 
   <td colname="col2"> Ends with </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> - </td> 
   <td colname="col2"> Not </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> | </td> 
   <td colname="col2"> Or </td> 
   <td colname="col3"> <p>Supported only in the <span class="term"> Advanced (special characters)</span> filter. </p> </td> 
  </tr> 
 </tbody> 
</table>
