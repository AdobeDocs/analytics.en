---
description: Create a data element in Dynamic Tag Management.
keywords: Dynamic Tag Management;data element;create new data element;name;type;default value;force lowercase value;remember this value for
solution: Experience Cloud,Analytics,Target
title: Create a data element
uuid: eacd5c60-6197-4129-a9e1-a39e9a58b38a
---

# Create a data element

Create a data element in Dynamic Tag Management.

1. [Create Web Property](/help/implement/other/dtm/t-create-web-property.md), if you haven't done so already.
1. In the web property, click **[!UICONTROL Rules]** > **[!UICONTROL Data Elements]**.
1. Click **[!UICONTROL Create New Data Element]**.
1. Complete the following fields and options:

   <table id="choicetable_681F7D5B86534FF0B6DB67E117B8E381"> 
    <thead class="chhead sthead"> 
      <th class="choptionhd"> Option</th> 
      <th class="chdeschd"> Description</th> 
    </thead> 
    <tr class="chrow strow"> 
      <td class="choption"><strong>Name</strong></td> 
      <td class="chdesc stentry"> <p>The data element friendly name that a marketer can recognize. For example, 
        <code>
          Product ID
        </code>. </p> <p> <p>Note:  The name is referenced by the rules builder, not an ID. If you change the name of the Data Element , you must change its reference in every rule that uses it. </p> </p> </td> 
    </tr> 
    <tr class="chrow strow"> 
      <td class="choption"><strong>Type</strong></td> 
      <td class="chdesc stentry"> <p> Specifies where the data is pulled from, such as JS Object, CSS Selector, Cookie, URL Parameter, or Custom Script. </p> <p>Depending on which type you select, different options display. See <a href="https://docs.adobe.com/content/help/en/dtm/using/resources/data-elements.html"> Types of Data Elements</a> in the Dynamic Tag Management Product Documentation for more information and examples. </p> </td> 
    </tr> 
    <tr class="chrow strow"> 
      <td class="choption"><strong>Default Value</strong></td> 
      <td class="chdesc stentry"> <p>A default element. This value ensures that the data element always has a value, even if a URL parameter does not exist or cannot be found by Dynamic Tag Management. </p> <p> <p>Note:  If there is no value and no default value, then nothing is returned. Any variable referencing that data element won't get set. Note also that the default value field is ignored if it's a "custom code" data element. </p> </p> </td> 
    </tr> 
    <tr class="chrow strow"> 
      <td class="choption"><strong>Force lowercase value</strong></td> 
      <td class="chdesc stentry"> <p>Dynamic Tag Management automatically makes the value lowercased. </p> </td> 
    </tr> 
    <tr class="chrow strow"> 
      <td class="choption"><strong>Remember this value for</strong></td> 
      <td class="chdesc stentry"> <p>How long you want Dynamic Tag Management to remember this value. </p> <p> Valid values include: </p> 
      <ul id="ul_52F6CD8FC22942208F3F45492E914104"> 
        <li id="li_32E4366C5B2E46D788CD8478620FE3E0"> <p>Session: Session-based timing can vary depending on the implementation. Session data elements are set to the session cookie. However, this setting could be based on a web server or the browser. It is not related to the session used in marketing reports &amp; analytics. </p> </li> 
        <li id="li_8A944564BF7643E4B21F0EF2394B3FE8"> <p>Pageview </p> </li> 
        <li id="li_5C8A2F2392FD475AA89DDA7D5B5CF88B"> <p>Visitor </p> </li> 
      </ul> </td> 
    </tr> 
   </table>

   See [Data Elements](https://docs.adobe.com/content/help/en/dtm/using/resources/data-elements.html) in the Adobe Tag Management Product Documentation for more information about how to use data elements.
1. Click **[!UICONTROL Save Data Element]**.
