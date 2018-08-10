---
description: Ways you can optimize report builder delivery, and a list of error messages that could occur occasionally.
seo-description: Ways you can optimize report builder delivery, and a list of error messages that could occur occasionally.
seo-title: Troubleshooting and best practices for Report Builder
solution: Analytics
title: Troubleshooting and best practices for Report Builder
topic: Report builder
uuid: 75b2432b-c3b3-410c-97ee-2f309354c13a
index: y
internal: n
snippet: y
translate: y
---

# Troubleshooting and best practices for Report Builder


* [ Report Builder 5.0 Users and Opening 5.1 Workbooks](troubleshoot.md#section_C29898775999453FABB5FB0E098415C8)
* [ Authentication Issues in Report Builder ](troubleshoot.md#section_FD79104DF1414FE2B36591606C963DE6)
* [ Recommendations for Optimizing Requests ](troubleshoot.md#section_33EF919255BF46CD97105D8ACB43573F)
* [ Error Message Descriptions ](troubleshoot.md#section_3DF3A1EEDAD149CB941BEABEF948A4A5)

## Report Builder 5.0 users and opening 5.1 workbooks {#section_C29898775999453FABB5FB0E098415C8}

Adobe changed the separator between dimensions and classifications from an underscore character (_) to ||. This change has compatibility implications for a Report Builder 5.0 user who opens a Report Builder v5.1 workbook with classification requests. Each time a workbook from a version older than v5.1 is opened, all its serialized classifications requests will be converted to this format. 

This introduces a forward compatibility problem: Once converted to v5.1, if a workbook is shared with a user on Report Builder v5.0, that user will not be able to recognize the classification request (indeed, it is looking for "_" but v5.1 serialized "||"). 

You will experience the following side effect when opening a ARB v5.1 workbook with classification request: 

* When opening the workbook, you will get the following warning: “This workbook was last saved using Report Builder v5.1. This version has introduced some features that are incompatible with the Report Builder version installed on this computer. It is highly recommended that you upgrade to the latest Report Builder version before updating this workbook.”
* If you right-click an ARB request with classification, the Report Builder context menus (edit request, add dependent request...) will not show up.
* If you perform a Refresh All, by clicking the third button, or by refreshing a set of requests from the Request Manager form, the classification request will execute without error. However, the classifications values will not be written out.
* You can still edit the request by opening the Request Manager, then going from row to row, until it reaches the right request.
* If you edit the request and leave all parameters the same and then click Finish, the response will be properly written out. Indeed, editing the request resolves the problem as the Response Layout parameters are re-serialized. So there is a workaround, although it is time consuming.

## Authentication issues in Report Builder {#section_FD79104DF1414FE2B36591606C963DE6}

Report Builder requires authentication to create data requests from your report suites. Sometimes there are issues logging in to report builder depending on your settings within [!DNL  Analytics] or your network. 

<table id="table_7A2070A17B70448981A85CF77176EBF2"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Item </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Invalid Login Company </td> 
   <td colname="col2">This error most commonly occurs when either the login company is improperly entered, or if there are network activity issues. Do the following: 
    <ul id="ul_2F65EB64EF2040AEB0DD519C3053E37B"> 
     <li id="li_8601336246B64A6696A0DB6EF349D5D8">Check the login company spelling to ensure that there is not a typo or an errant space. </li> 
     <li id="li_ECD83E29D1A04B828FA9AAEE38029672">Log in to <span class="keyword"> Analytics</span> with the same login company to ensure that it is correct. If you are not able to log in with those credentials, contact one of your organization's administrators to obtain the correct login company. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Firewall </td> 
   <td colname="col2"> Report Builder uses ports 80 and 443. Ensure that these ports are allowed through your organization's firewall. See also Adobe's Internal IP Addresses for additional firewall exclusions. </td> 
  </tr> 
 </tbody> 
</table>


## Recommendations for optimizing requests {#section_33EF919255BF46CD97105D8ACB43573F}

The following factors can increase request complexity and result in slower processing: 

<table id="table_7B2E48E1D78F49668A70476E211926D3"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Item </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Factors that can slow down deliveries </td> 
   <td colname="col2"> 
    <ul id="ul_61FFD31E3F04424393F3F886C9547526"> 
     <li id="li_6497332FDF07488AAAC587863651BF8D">Too many bookmarks, dashboards, and Report Builder workbooks were scheduled within a few hours </li> 
     <li id="li_CBE0E455CEBE4FF99ADE317E00A96BA1">Too many Report Builder workbooks were scheduled at around the same time. When this occurs, the report API queue becomes backlogged. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Factors that can slow down workbook runtime </td> 
   <td colname="col2"> 
    <ul id="ul_F3383A91CBF24621999763E2BA57995F"> 
     <li id="li_57F37C48A87D4174ABB65C020979A5BB">Significant increase in classifications. </li> 
     <li id="li_F0D9EC30C7C9446FAA3DE05C408B5E1E">Increasing the request date range over time. <p><b>Example</b>: Suppose you create a trended request using the <span class="wintitle"> Current Year</span> setting, broken down by <span class="wintitle"> Day</span> granularity. At the end of the year, the request will return more periods than the one created at the beginning of the year. </p> <p>(January 1 - January 30 versus January 1 - December 31.) </p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Causes that result in workbook delivery failure </td> 
   <td colname="col2"> Complex Excel formulas in a workbook, particularly ones that involve date and time. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Cells returning 0s (no values) </td> 
   <td colname="col2"> An apostrophe or single quote in the Excel sheet name will cause report builder to return no values. (This is a Microsoft Excel limitation.) </td> 
  </tr> 
 </tbody> 
</table>

**Individual request performance** 

Processing speed can be affected by the following settings: 

<table id="table_7B4281D2E9B9493FB0932F69C0573AA5"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Setting </th> 
   <th colname="col2" class="entry"> Faster Performance </th> 
   <th colname="col3" class="entry"> Slower Performance </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Breakdowns and the breakdown order </td> 
   <td colname="col2"> Few </td> 
   <td colname="col3"> Many </td> 
  </tr> 
  <tr> 
   <td colname="col1"> </td> 
   <td colspan="2"> <b>Example</b>: If you break down A by Z, the number of items for A should always be less than the number of items for Z. If it is the other way around, the request time can increase significantly. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Date range </td> 
   <td colname="col2"> Small range </td> 
   <td colname="col3"> Wide range </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Filtering </td> 
   <td colname="col2"> Specific filtering </td> 
   <td colname="col3"> Most Popular filtering </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Granularity </td> 
   <td colname="col2"> Aggregated </td> 
   <td colname="col3"> 
    <ul id="ul_16955051AAA64C58B97DFEA18D70521C"> 
     <li id="li_919E9C3082CA4E649D7F7E603784FFE7">Hourly </li> 
     <li id="li_837DAEF7B7F64B549C88EB208091D495">Daily </li> 
     <li id="li_CB9E0DB1315140A584EE25A57D6CA9FC ">Weekly </li> 
     <li id="li_446DB7356BFE40298509350809BF2209">Monthly </li> 
     <li id="li_4E85CB239D91497F959A7E2D7468A27C">Quarterly </li> 
     <li id="li_E641534E051A4EBEBEAD9F766AD285DE">Yearly </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Number of entries </td> 
   <td colname="col2"> Small data set </td> 
   <td colname="col3"> Large data set </td> 
  </tr> 
 </tbody> 
</table>

**Scheduling time** 

Stagger scheduling over 24-hour period (see table below). Existing bookmarks , dashboards, and Report Builder workbooks scheduled close together may cause delays. 

Schedule larger, more complex requests in the early morning to allow for manual pulls and refreshing to occur during the business day. 

<table id="table_A10D4EE572814DF3A4C14A6BFADB0B3C"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Scheduling Time </th> 
   <th colname="col2" class="entry"> 1 a.m. - 2 a.m. </th> 
   <th colname="col3" class="entry"> 2 a.m. - 7 a.m. </th> 
   <th colname="col4" class="entry"> 7 a.m. - 6 p.m. </th> 
   <th colname="col5" class="entry"> 6 p.m. - Midnight </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Report Builder usage </td> 
   <td colname="col2"> Quiet </td> 
   <td colname="col3"> Very busy </td> 
   <td colname="col4"> <p>Client-side usage. </p> <p> Higher volumes of users refreshing locally and requesting to "Send immediately." </p> <p>Additionally, verify whether the API queue is cleared when scheduled workbooks time out. </p> </td> 
   <td colname="col5"> Not busy </td> 
  </tr> 
 </tbody> 
</table>

**Timeouts** 

Any scheduled report times out after four hours. The system attempts scheduling three more times, potentially resulting in a failure. (Generally, the larger the data set the longer it takes to run.) These can be seen in [!DNL  Analytics] reporting and Report Builder: 

* [!DNL  Analytics]: ** [!UICONTROL  Favorites] ** > ** [!UICONTROL  Scheduled Reports] **
* Report Builder: Click ** [!UICONTROL  Management] ** in the [!UICONTROL  Add-ins] tab in Excel.

## Error message descriptions {#section_3DF3A1EEDAD149CB941BEABEF948A4A5}

A list of error messages that could occur occasionally while you are using Report Builder. 


>[!NOTE]
>
>This is only a selection of error messages, and not an exhaustive list. For more information about resolving errors, contact your administrator.



** *This feature can only be applied on an open workbook.* ** 

If no workbooks (spreadsheet documents) are open in Excel, and you click one of the icons in the report builder toolbar, this message is displayed. In addition, the toolbar becomes disabled until you open a spreadsheet. However, you can click the on-line help icon while the toolbar is still enabled without causing this error. 

** *You first need to exit the [!UICONTROL  Request Wizard]before activating the [!UICONTROL  Request Manager].* ** 

While the [!UICONTROL  Request Manager] and the [!UICONTROL  Request Wizard] are linked functionally, it is not possible to start working with the [!UICONTROL  Request Manager] before completing or cancelling actions taken in the [!UICONTROL  Request Wizard]. 

** *There is no request associated with this range.* ** 

This error message occurs if you click on the [!UICONTROL  From Sheet] button in the [!UICONTROL  Request Manager] when a cell of the spreadsheet contains no requests. 

To identify which cells in the spreadsheet contain requests, click individual requests listed in the table in the [!UICONTROL  Request Manager]. If a request is associated with cells, the cells will show up highlighted when the request is selected in the table. 

** *The selected Range is not valid. Please select another Range.* ** 

If a cell of the spreadsheet is selected and already has a request mapped to it, this error occurs. Either delete the request mapped to the cells or choose another range of cells to map. 

When you want to delete cells, it is important to locate cells containing requests and delete the request before deleting the cells (removing rows or columns). 

** *Please Exit the Excel Cell with focus before using this feature.* ** 

If you are in *edit mode* in an Excel cell and click one of the Report Builder icons, this error message appears. Edit mode in an Excel cell means that the cell is selected and the cursor appears inside the cell. You are also in edit mode in an Excel cell when you type directly into the [!UICONTROL  Formula] bar or into the [!UICONTROL  Name Box] at the top of Excel. 

** *The range selected intersects another request's range. Please change your selection.* ** 

If you have already mapped a set of cells to the spreadsheet, this error is displayed. 

One way to determine which cells are mapped before adding new requests is to close the [!UICONTROL  Request Wizard] and open the [!UICONTROL  Request Manager]. Then, select items listed in the request summary table one by one. Whenever you select a request in the list, the corresponding cells containing request mappings in the spreadsheet are highlighted. 

This is one reason you should consider marking cells with highlighting, row or column information, or a formatting style before mapping multiple cells to multiple areas. 
