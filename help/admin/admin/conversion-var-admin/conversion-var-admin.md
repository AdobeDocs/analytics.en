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



| Element | Description |
| --- | --- |
| Name | The friendly name of the conversion variable. This name is how the eVar is referred to in general reporting, and will be the name of the report in the left-hand menu. |
| Type  (eVar only) | The type of variable value:<ul><li>**Text String**: Captures text values used on your site. This is the most common type of eVar, and the default setting. It acts similar to other variables, where the value within it is a static text string. If you are tracking things such as internal campaigns or internal search keywords, this is the recommended setting.</li><li>**Counter**: Counts the number of times an action occurs before the success event. For example, if you use an eVar to track internal searches on your site, set this value to  Text String to track the use of search terms. Set this value to  Counter to count the number of searches made, regardless of search terms used. For example, you can use a counter eVar to track the number of times someone used your internal search before making a purchase.</li></ul> |
| Allocation | Determines how Analytics assigns credit for a success event if a variable receives multiple values before the event. Supported values include:<ul><li>**Most Recent**: The last eVar value always receives credit for success events until that eVar expires.</li><li>**Original Value**: The first eVar always receives credit for success events until that eVar expires.</li><li>**Linear**: Allocates success events equally across all eVar values. Since Linear allocation accurately distributes values only within a visit, use Linear allocation with an eVar expiration of Visit.</li></ul> **Note**:  Switching allocation to or from Linear prevents historical data from displaying. Mixing allocation types in the reporting interface can lead to misstated data in reports. For example, Linear allocation might divide revenue across a number of different eVar values. After changing back to Most Recent allocation, 100% of that revenue would be associated with the most recent single value. This association can lead to incorrect conclusions by users.<br><br>To avoid the likelihood of confusion in reporting, Adobe Analytics makes the historical data unavailable to the interface. It can be viewed if you decide to change the given eVar back to the initial allocation setting, although you should not change eVar allocation settings simply to access the historical data. Adobe recommends using a new eVar when new allocation settings are desired for data already being recorded, rather than changing allocation settings on an eVar that already has a significant amount of historical data built up. |
| Expire After | Specifies a time period, or event, after which the eVar value expires (no longer receives credit for success events). If a success event occurs after eVar expiration, the None value receives credit for the event (no eVar was active).  If you select an event as an expiration value, the variable expires only if the event occurs. If the event does not occur, the variable never expires.  The available expiration options can be classified under four main categories:<ul><li>**At a page view or visit level.** Conversion events beyond the page view or visit do not associate with the eVar.</li><li>**Based on a time period, such as day, week, month, or year.** Conversion events beyond the specified time period do not associate with the eVar. The expiration period starts when the variable is set. eVars expire based on the time they were set, to the second (minute, hour, day, month, etc): <ul><li>MINUTE=60 seconds</li><li>HOUR=3600 seconds (60 minutes)</li><li>DAY=86400 seconds (24 hours)</li><li>WEEK=604800 seconds (7 days)</li><li>MONTH=2678400 seconds (31 days)</li><li>QUARTER=8035200 seconds (93 days - 3 months of 31 days)</li><li>YEAR=31536000 seconds (365 days)</li><br>If a visit starts at 7:00 AM on Monday and an eVar is set within that visit at 7:15 AM, expiration is as shown below:<li>Day expiration: eVar expires at 7:15 AM on Tuesday.</li><li>Week expiration: eVar expires on the following Monday at 7:15 AM.</li><li>Month expiration: eVar expires 31 days from Monday at 7:15 AM.</li></ul><li>**Specific conversion events.** Any other conversion events that fire after the specific event designated associate with the eVar.</li><li>**Never.** As long as the  visitorID cookie is intact, any amount of time can pass between eVar and event.</li></ul>|
| Status  (eVar only) | Defines the eVar status:<ul><li>**Disabled**: Disables the eVar. Removes the eVar from the conversion variable list.</li><li>**No Subrelations**: Prevents you from breaking down the eVar with a subrelation.</li><li>**Basic Subrelations**: Lets you break down an eVar by any report with full subrelations (for example, Products or Campaign).</li></ul> |
| Reset | Resets any existing value in the eVar.  Use this setting when repurposing an eVar so you do mix an old value into a new report. Resetting does not erase historical data. |
| Merchandising  (eVar only) | Merchandising variables can follow one of two syntaxes:<ul><li>**Products Syntax**: Associates the eVar value to a product. Note:  If Products Syntax is selected, the Merchandising Binding Event section is disabled and not selectable for edit. For this syntax, Binding Events are not applicable.</li><li>**Conversion Variable Syntax**: Associates the eVar with a product only if a Binding Event occurs. In this case, you select the events that act as Binding Events.  Changing this setting without updating your JavaScript code accordingly causes lost data. See [Merchandising Variables](https://experienceleague.adobe.com/docs/analytics/components/variables/merchandising-variables/var-merchandising.html).</li></ul>|
| Merchandising Binding Event  (eVar only) | If Merchandising is set to [!UICONTROL Conversion Variable Syntax], the selected events bind the current eVar value with a product. To use a Binding Event, set Allocation to Most Recent. If  Allocation is Original Value, the first eVar product binding remains until the eVar expires. Multiple events can be selected by holding down ctrl (Windows) or cmd (Mac) and clicking on multiple items in the list. You can select an event only when the "Conversion Variable Syntax" is selected. |

**Expiration**

`eVars` expire after a time period you specify. After the eVar expires, it no longer receives credit for success events. eVars can also be configured to expire on success events. For example, if you have an internal promotion that expires at the end of a visit, the internal promotion receives credit only for purchases or registrations that occur during the visit in which they were activated.

There are two ways to expire an eVar:

* You can set the eVar to expire after a specified time period or event.
* You can use force the expiration of an eVar by resetting it, which is useful when repurposing a variable.

For example, if you change the expiration of an eVar from 30 to 90 days, eVar values collected will continue to persist for the duration of the new expiration set (in this case, 90 days). The system simply looks at the current expiration setting and the last set timestamp of the eVar value collected to determine expiration. Only the **[!UICONTROL Reset]** option expires values and does so immediately. 

Another example: If an eVar is used in May to reflect internal promotions and expires after 21 days, and in June it is used to capture internal search keywords, then on June 1, you should force the expiration of, or reset, the variable. Doing so will help keep internal promotion values out of June's reports.

**Case Sensitivity**

The upper or lower case used in reporting is based on the first value the backend system registers. This value could either be the first instance ever seen or vary by some time period (e.g., monthly), depending on the variety and quantity of data associated with the report suite.

**Counters**

While eVars are most often used to hold string values, they may also be configured to act as counters. eVars are useful as counters when you are trying to count the number of actions a user takes before an event. For example, you may use an eVar to capture the number of internal searches before purchase. Each time a visitor searches, the eVar should contain a value of '+1.' If a visitor searches four times before a purchase, you will see an instance for each total count: 1.00, 2.00, 3.00, and 4.00. However, only the 4.00 receives credit for the purchase event (Orders and Revenue Metrics). Only positive numbers are allowed as values of an eVar counter.
