---
description: The Custom Insight Conversion Variable (or eVar) is placed in the Adobe code on selected web pages of your site. Its primary purpose is to segment conversion success metrics in custom marketing reports. An eVar can be visit-based and function similarly to cookies. Values passed into eVar variables follow the user for a predetermined period of time.
keywords: eVar
title: Conversion Variables (eVar)
feature: Admin Tools
uuid: 1eed0cb1-0735-4142-be21-43f264216b50
exl-id: 822ecaff-a06c-42e1-aee8-ef4a43df4230
---
# Conversion Variables (eVars)

The Custom Insight Conversion Variable (or eVar) is placed in the Adobe code on selected web pages of your site. Its primary purpose is to segment conversion success metrics in custom marketing reports. An eVar can be visit-based and function similarly to cookies. Values passed into eVar variables follow the user for a predetermined period of time.

When an eVar is set to a value for a visitor, Adobe automatically remembers that value until it expires. Any success events that a visitor encounters while the eVar value is active are counted toward the eVar value.

eVars are best used to measure cause and effect, such as:

* Which internal campaigns influenced revenue 
* Which banner ads ultimately resulted in a registration 
* The number of times an internal search was used before making an order

If traffic measurement or pathing is desired, using traffic variables is recommended.

>[!NOTE]
>
>Only a single value can be stored in an eVar in an image request. If multiple values are desired in an eVar value, we recommend that you implement [List variables (list vars)](https://experienceleague.adobe.com/docs/analytics/implementation/vars/page-vars/page-variables.html).

## Conversion Variables - Descriptions {#section_7C317BB0287A4B8EB0A1A4ECC40627BF}

Descriptions of fields used when [editing conversion variables](/help/admin/admin/conversion-var-admin/t-conversion-variables-admin.md).

<table id="table_E48D50926E6B492183300CA58A886927"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Element </p> </th> 
   <th colname="col2" class="entry"> <p>Description </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="uicontrol"> Name </span> </p> </td> 
   <td colname="col2"> <p>The friendly name of the conversion variable. This name is how the eVar is referred to in general reporting, and will be the name of the report in the left-hand menu. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="uicontrol"> Type</span> </p> <p>(eVar only) </p> </td> 
   <td colname="col2"> <p>The type of variable value: </p> <p> <b>Text String</b>:</span> Captures text values used on your site. This is the most common type of eVar, and the default setting. It acts similar to other variables, where the value within it is a static text string. If you are tracking things such as internal campaigns or internal search keywords, this is the recommended setting. </p> <p> <b>Counter</b>:</span> Counts the number of times an action occurs before the success event. For example, if you use an eVar to track internal searches on your site, set this value to <span class="uicontrol"> Text String</span> to track the use of search terms. Set this value to <span class="uicontrol"> Counter</span> to count the number of searches made, regardless of search terms used. For example, you can use a counter eVar to track the number of times someone used your internal search before making a purchase. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="uicontrol"> Allocation </span> </p> </td> 
   <td colname="col2"> <p>Determines how Analytics assigns credit for a success event if a variable receives multiple values before the event. Supported values include: </p> <p> <b>Most Recent</b>: The last eVar value always receives credit for success events until that eVar expires. </p> <p> <b>Original Value</b>: The first eVar always receives credit for success events until that eVar expires. </p> <p> <b> Linear</b>:Allocates success events equally across all eVar values. Since Linear allocation accurately distributes values only within a visit, use Linear allocation with an eVar expiration of Visit. </p> <p>Note:  Switching allocation to or from Linear prevents historical data from displaying. Mixing allocation types in the reporting interface can lead to misstated data in reports. For example, Linear allocation might divide revenue across a number of different eVar values. After changing back to Most Recent allocation, 100% of that revenue would be associated with the most recent single value. This association can lead to incorrect conclusions by users. </p> <p>To avoid the likelihood of confusion in reporting, Analytics makes the historical data unavailable to the interface. It can be viewed if you decide to change the given eVar back to the initial allocation setting, although you should not change eVar allocation settings simply to access the historical data. Adobe recommends using a new eVar when new allocation settings are desired for data already being recorded, rather than changing allocation settings on an eVar that already has a significant amount of historical data built up. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="uicontrol"> Expire After</span> </p> </td> 
   <td colname="col2"> <p>Specifies a time period, or event, after which the eVar value expires (no longer receives credit for success events). If a success event occurs after eVar expiration, the None value receives credit for the event (no eVar was active). </p> <p>If you select an event as an expiration value, the variable expires only if the event occurs. If the event does not occur, the variable never expires. </p> <p>The available expiration options can be classified under four main categories: </p> 
    <ul id="ul_810A37C9B6624F429F2FB45C18F7B43F"> 
     <li id="li_654D9D9044EC4E61AA7ABA372DBF8A93"><b>At a page view or visit level.</b> Conversion events beyond the page view or visit do not associate with the eVar. </li> 
     <li id="li_689FBC8B4DAC41B3B0166E6586DD1990"><b>Based on a time period, such as day, week, month, or year.</b> Conversion events beyond the specified time period do not associate with the eVar. The expiration period starts when the variable is set. eVars expire based on the time they were set, to the second (minute, hour, day, month, etc): 
      <ul id="ul_80C7E3182B6B4356B8A3CA920B81C6D5"> 
       <li id="li_F16F60319CCE406D9EDEFEC0A200BC4D">MINUTE=60 seconds </li> 
       <li id="li_45F47F3F5691415B84052B235DF3BB54">HOUR=3600 seconds (60 minutes) </li> 
       <li id="li_5288CE7D168E4C85B3D9BB67A44D32EC">DAY=86400 seconds (24 hours) </li> 
       <li id="li_60FC8BCD657745EE87B4E458CBA69583">WEEK=604800 seconds (7 days) </li> 
       <li id="li_7A05A66613C84F929F030310B9567CF5">MONTH=2678400 seconds (31 days) </li> 
       <li id="li_DCD3CABF59E34D5999B03E606B08AD85">QUARTER=8035200 seconds (93 days - 3 months of 31 days) </li> 
       <li id="li_54351D2899454D39A8BA205910D2CCB1">YEAR=31536000 seconds (365 days) </li> 
      </ul> <p> </p> <p>If a visit starts at 7:00 AM on Monday and an eVar is set within that visit at 7:15 AM, expiration is as shown below: </p> 
      <ul id="ul_72B311006BE6428698313D251C0940DB"> 
       <li id="li_50925D4A40AD4ACA88704A523138C5B9">Day expiration: eVar expires at 7:15 AM on Tuesday. </li> 
       <li id="li_25846328766D4B4BAF407236C65C956C">Week expiration: eVar expires on the following Monday at 7:15 AM. </li> 
       <li id="li_82DB2D7F53304623A5E1241D75C7DF94">Month expiration: eVar expires 31 days from Monday at 7:15 AM. </li> 
      </ul> </li> 
     <li id="li_C132C5C5A5344B91BDF5EB6A1C717C37"><b>Specific conversion events.</b> Any other conversion events that fire after the specific event designated associate with the eVar. </li> 
     <li id="li_5A782D743FB940649E6CB3E4BEA9B8B6"><b>Never.</b> As long as the <span class="varname"> visitorID</span> cookie is intact, any amount of time can pass between eVar and event. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="uicontrol"> Status</span> </p> <p>(eVar only) </p> </td> 
   <td colname="col2"> <p>Defines the eVar status: </p> <p><b>Disabled</b>:</span> Disables the eVar. Removes the eVar from the conversion variable list. </p> <p> <b>No Subrelations</b>:</span> Prevents you from breaking down the eVar with a subrelation. </p> <p> <b>Basic Subrelations</b>: </span>Lets you break down an eVar by any report with full subrelations (for example, Products or Campaign). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="uicontrol"> Reset</span> </p> </td> 
   <td colname="col2"> <p>Resets any existing value in the eVar. </p> <p>Use this setting when repurposing an eVar so you do mix an old value into a new report. Resetting does not erase historical data. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="uicontrol"> Merchandising</span> </p> <p>(eVar only) </p> </td> 
   <td colname="col2"> <p>Merchandising variables can follow one of two syntaxes: </p> <p> <b>Products Syntax</b>:</span> Associates the eVar value to a product. Note:  If Products Syntax is selected, the Merchandising Binding Event section is disabled and not selectable for edit. For this syntax, Binding Events are not applicable. </p> </p> <p> <b>Conversion Variable Syntax</b>:</span> Associates the eVar with a product only if a Binding Event occurs. In this case, you select the events that act as Binding Events. </p> <p>Changing this setting without updating your JavaScript code accordingly causes lost data. See <a href="https://experienceleague.adobe.com/docs/analytics/components/variables/merchandising-variables/var-merchandising.html"> Merchandising Variables</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="uicontrol"> Merchandising Binding Event</span> </p> <p>(eVar only) </p> </td> 
   <td colname="col2"> <p>If Merchandising is set to <span class="uicontrol"> Conversion Variable Syntax</span>, the selected events bind the current eVar value with a product. </p> <p>To use a Binding Event, set <span class="uicontrol"> Allocation to Most Recent</span>. If <span class="uicontrol"> Allocation is Original Value</span>, the first eVar product binding remains until the eVar expires. Multiple events can be selected by holding down <code>ctrl</code> (Windows) or <code>cmd</code> (Mac) and clicking on multiple items in the list. You can select an event only when the "Conversion Variable Syntax" is selected.</p> </td> 
  </tr> 
 </tbody> 
</table>

**Expiration**

`eVars` expire after a time period you specify. After the eVar expires, it no longer receives credit for success events. eVars can also be configured to expire on success events. For example, if you have an internal promotion that expires at the end of a visit, the internal promotion receives credit only for purchases or registrations that occur during the visit in which they were activated.

There are two ways to expire an eVar:

* You can set the eVar to expire after a specified time period or event.
* You can use force the expiration of an eVar by resetting it, which is useful when repurposing a variable.

For example, if you change the expiration of an eVar from 30 to 90 days, eVar values collected will continue to persist for the duration of the new expiration set (in this case, 90 days). The system simply looks at the current expiration setting and the last set timestamp of the eVar value collected to determine expiration. Only the **[!UICONTROL Reset]** option expires values and does so immediately. 

Another example: If an eVar is used in May to reflect internal promotions and expires after 21 days, and in June it is used to capture internal search keywords, then on June 1, you should force the expiration of, or reset, the variable. Doing so will help keep internal promotion values out of June's reports.

**Case Sensitivity**

eVars are case insensitive, but they are displayed in the capitalization of the first occurrence. For example, if the first instance of eVar1 is set to "Logged In," but all subsequent instances are passed as "logged in," reports always show "Logged In" as the value of the eVar.

**Counters**

While eVars are most often used to hold string values, they may also be configured to act as counters. eVars are useful as counters when you are trying to count the number of actions a user takes before an event. For example, you may use an eVar to capture the number of internal searches before purchase. Each time a visitor searches, the eVar should contain a value of '+1.' If a visitor searches four times before a purchase, you will see an instance for each total count: 1.00, 2.00, 3.00, and 4.00. However, only the 4.00 receives credit for the purchase event (Orders and Revenue Metrics). Only positive numbers are allowed as values of an eVar counter.
