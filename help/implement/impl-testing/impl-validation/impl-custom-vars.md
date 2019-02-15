---
description: List of custom variables used in Analytics.
keywords: Analytics Implementation
seo-description: List of custom variables used in Analytics.
seo-title: Custom variables
solution: Analytics
title: Custom variables
topic: Developer and implementation
uuid: 54adf622-7f05-49c0-b7e6-702bb2f17b1c
---

# Custom variables

List of custom variables used in Analytics.

<table id="table_E8C7871F63F648A59644638FB56BD0E1"> 
 <thead> 
  <tr> 
   <th class="entry"> Variable </th> 
   <th class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td> Traffic Variables </td> 
   <td> Check the value of prop1 - 75. Here is a checklist of items to check. 
    <ul id="ul_0EE2D50BA90F4F21BD63268A5082F980"> 
     <li id="li_A6E4D66E8A03400491A26A08E4945908">Is the correct case used? "ValueA" is a different record than "valueA." You can use all lowercase since a small subset of browsers convert all variables to lower case. </li> 
     <li id="li_65CBFB908E7B4ED5AF9518FE5B58D4E2">Are the values less than 100 characters in length? If not, some clipping of the values can occur. </li> 
     <li id="li_CC506D114AFE44699D89AB84BBCCEBFC"> Are all the values in a single property variable related, or do some values look out of place? </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td> Conversion Variables </td> 
   <td> <span class="wintitle"> Econversion</span> variables include eVar 1 - 75. Here is a list of issues to check for the following. 
    <ul id="ul_CA10C5B9F24B4C49A64CA84A9DCE8E63"> 
     <li id="li_8CCD92F3AD5E49EBA91C9B008DA47016">Is the correct case used? "ValueA" is a different record than "valueA." You can use all lowercase since a small subset of browsers convert all variables to lower case. </li> 
     <li id="li_5B6FDEDB2C32409AA59D6BB0DF2346CB">Are the values less than 255 characters in length? If not, some clipping of the values can occur. </li> 
     <li id="li_C31AFBAC99D84E96A1244E795CE7765D">Are all the values in a single eVar related, or do some values look out of place? </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td> Custom Events </td> 
   <td> Events include both standard values (<span class="wintitle"> prodView</span>, <span class="wintitle"> scOpen</span>, <span class="wintitle"> scAdd</span>, <span class="wintitle"> scCheckout</span>, <span class="wintitle"> purchase</span>), as well as custom events from event1 to event100. All events are sent in the events variable. Multiple events on the same page should be comma-delimited (no white space). 
    <ul id="ul_2213CC9DE892433FAF6FC1F5A2B841B4"> 
     <li id="li_15E31A9FF1654DFA93C158F422B9EAE3">For all the standard conversion events, products should also be populated with the applicable products. For all events except purchase, the qty and price elements are optional. </li> 
     <li id="li_03ED9AAC45DA47A58AB482E2CEBF5108">The <span class="wintitle"> purchase</span> event, must be set only once in a session after the purchase has been completed and confirmed. </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

