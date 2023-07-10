---
description: The Finding Methods page identifies how various finding methods reports receive credit for conversion success events on your site. For example, if a search engine refers a visitor to your site who makes a purchase, Finding Methods specify how the search engine receives credit for the referral.
title: Finding Methods
feature: Admin Tools
uuid: 1053993e-7fc4-4874-84fa-367ecdcd7b45
exl-id: 58c4510c-2343-4b0a-9c09-5583f6d4250f
---
# Finding Methods

The Finding Methods page identifies how various finding methods reports receive credit for conversion success events on your site. For example, if a search engine refers a visitor to your site who makes a purchase, Finding Methods specify how the search engine receives credit for the referral.

**[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Report Suites]** > **[!UICONTROL Edit Settings]** > **[!UICONTROL Conversion]** > **[!UICONTROL Finding Methods]**

## Finding Methods Descriptions {#section_8B6278DB75224EAB9F49D89A86274E8A}

<table id="table_8ABC1C9BD63F419082E4C4C69E401526"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Element </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Name </td> 
   <td colname="col2"> The finding method you want to modify </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Allocation </td> 
   <td colname="col2"> Specifies how to apply credit for a referral. Supported allocation options include: <p> <span class="uicontrol"> Most Recent (Last): </span> Gives all credit to the last referrer (default). </p> <p> <span class="uicontrol"> Original Value: </span> Gives all credit to the first referrer. </p> <p> <span class="uicontrol"> Linear: </span>Divides credit among all referrers equally. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Expire After </td> 
   <td colname="col2"> 
    <ul id="ul_95EB224CAD164E9997B148E08AFA5F9B"> 
     <li id="li_C240460C21E14AA498D2EA62B9354710"> <span class="uicontrol"> Visit: </span> After a specified period of inactivity; usually about 30 minutes. </li> 
     <li id="li_A3AE5438919E44B68DF99BEEA60C44EE"> <span class="uicontrol"> Page View: </span> As soon as any page on your site opens. </li> 
     <li id="li_D5E20FEF313E4C5B99E7097CA175761A"> <span class="uicontrol"> Minute: </span> After 1 minute of inactivity. </li> 
     <li id="li_7315AA3EDDBB47A2BEA3C173881378A1"> <span class="uicontrol"> Purchase: </span> At the time of purchase. </li> 
     <li id="li_C0CF07581654472C9C9EC944E6F18164"> <span class="uicontrol"> Product View: </span> When a visitor views a product web page. </li> 
     <li id="li_A1B04065150B407491D2EC78EC0DBDF5"> <span class="uicontrol"> Cart Open: </span> When a visitor opens a new online shopping cart. </li> 
     <li id="li_2AA50C6B9CB14500B67909CDF2AA700C"> <span class="uicontrol"> Cart Checkout: </span> When a visitor checks out using an online shopping cart. </li> 
     <li id="li_F58CE6FB8DCE4BE4927FFCB35A6D8E31"> <span class="uicontrol"> Cart Add: </span> When a visitor adds a product to an online shopping cart. </li> 
     <li id="li_AD7C846F46604FC48E0919ACB7515E14"> <span class="uicontrol"> Cart Remove: </span> When a visitor removes a product from an online shopping cart. </li> 
     <li id="li_EB66E0563F564C9F985BE922DABD0A56"> <span class="uicontrol"> Cart Open: </span> When a visitor views the contents of an online shopping cart. </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>All Finding Methods expire when the visit ends. If you choose to Expire After a different event (for example, Cart Checkout), the Finding Method expires when Cart Checkout occurs during the visit. If a Cart Checkout does not occur during the visit, the Finding Method still expires when the visit ends.
