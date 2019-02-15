---
description: Segment IQ (Segment Comparison) is one of the most widely used feature in Analysis Workspace, and customers are constantly finding new an innovative ways to drive insights with it. Here are just a handful of successful use cases.
keywords: Segment IQ
seo-description: Segment IQ (Segment Comparison) is one of the most widely used feature in Analysis Workspace, and customers are constantly finding new an innovative ways to drive insights with it. Here are just a handful of successful use cases.
seo-title: Segment IQ use cases
title: Segment IQ use cases
uuid: 2a98b96b-5529-4c7f-a787-27920603d5b0
---

# Segment IQ use cases

Segment IQ (Segment Comparison) is one of the most widely used feature in Analysis Workspace, and customers are constantly finding new an innovative ways to drive insights with it. Here are just a handful of successful use cases.

## Use case 1: compare mobile vs desktop implementations {#section_B3A5983E58D0470895C030EA527C4966}

**"We compared hits from one site to another site and quickly found a number of tagging inconsistencies. This way, we avoided data problems before product release."**

**Scenario**: A product manager in charge of a mobile website and a desktop website was tasked with making sure the tags were consistent across mobile and desktop. To make sure he hadn’t missed anything important, he used Segment IQ to compare the hits coming from the mobile site to the hits coming from the desktop site. He noticed that he has forgotten to tag the checkout event on the mobile website and was able to get the proper tags placed before the mobile site was released. As a result, the product manager avoided a data disaster due to the mobile site not having recorded any conversions.

**How to set up this comparison:** 

<table id="table_B5FA23CB34DE4331A8BD65ED4B351038"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Segment 1 </th> 
   <th colname="col3" class="entry"> Segment 2 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Use/Create a hit-level segment where </p> <p> </p> <p> 
     <ul id="ul_1F5D5136620E449D93A771CD2576A18A"> 
      <li id="li_CB32DD1033DA4E5CA3B9AD41030800E6">Mobile Device Type equals Mobile Phone or Tablet </li> 
     </ul> </p> </td> 
   <td colname="col3"> <p>Use/Create a hit-level segment where </p> <p> </p> <p> 
     <ul id="ul_79CC51C4C9494275B3F37B6D2AB0505E"> 
      <li id="li_83BE21AD1FB34195BAFF3F15421DBB3D">Mobile Device Type does not equal Mobile Phone or Tablet </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Use case 2: compare customers who use a certain feature to those who don't {#section_878B08FDD70A45E186C1F28EBA296636}

**"We found customers who used our product comparison feature were 10% more likely to convert. We moved it to the top of the page, and grew orders by 4%!"**

**Scenario:** A retail site optimization team wanted to better understand the users who were interacting with a product comparison feature they had recently released. By creating a segment of visitors who had interacted with the feature, they were able to use Segment IQ to compare those users to everyone else on the site. Segment IQ quickly identified several important differences including the fact that these users were 10% more likely to purchase a product. The site optimization team decided to test the product comparison feature more prominently at the top of the page.

**How to set up this comparison:** 

| Segment 1 | Segment 2 |
|--- |--- |
|Use/Create a visitor-level segment for Visitors who interacted with the price comparison tool.|Use the  Everyone Else  segment that gets generated automatically and encompasses everyone not included in Segment 1.|

## Use case 3: compare news site visitors to other site section visitors {#section_0EAFC90C450244058B161200AC9901B8}

**"We discovered that visitors to our news section were twice as likely to watch video ads, so we added more video options to that section. We experienced a 7% increase in video ads viewed!"**

**Scenario:** A major media publishing company was looking at ways to improve the content engagement for audiences in their news section. To better understand the news audience they created a segment of visitors who had visited the News site section. Segment IQ scanned through every metric and dimension and immediately surfaced that these users were twice as likely to watch video ads than visitors to any other site section. The video team put together a recommended video section on their news side rail and were able to achieve a 7% increase in video ads viewed. Considering all of the things they could have spent time and effort on, this was seriously low hanging fruit and produced quick and measurable results.

**How to set up this comparison:** 

| Segment 1 | Segment 2 |
|--- |--- |
|Use/Create a visitor-level segment for Visitors to the News site section.|Use the  Everyone Else  segment that gets generated automatically and encompasses everyone not included in Segment 1.|

## Use case 4: compare visitors from paid search to everyone else {#section_73912670409349CAB131FE9D8B4FB11C}

**"Visitors coming to our site from search engines were 3 times more likely to up-sell than everyone else. We upped our spend on specific keywords as a result and achieved a 56% increase in up-sells.”**

**Scenario:** A major B2B services company wanted to understand the type of traffic that paid search keywords were bringing to their site. Paid search had not resulted in a lot of conversions directly, and the marketing executive was considering decreasing budget for it. The marketing team created a segment of visitors who came to the site via paid search and compared them to all other visitors using Segment IQ. They discovered that although these visitors were not as likely to convert directly, they were however 3 times more likely to up-sell on a previously purchased service. The marketing team was then able to focus their budget on just the up-sell related keywords and saw a 56% increase in service up-sells.

**How to set up this comparison:**

| Segment 1 | Segment 2 |
|--- |--- |
|Use/Create a visitor-level segment for Visitors referred by Natural Search or who came from an SEM campaign.|Use the  Everyone Else  segment that gets generated automatically and encompasses everyone not included in Segment 1.|

## Use case 5: compare Fitbit purchasers to everyone else {#section_9142B8A270764545B0A516AA309F1785}

**"We found that people buying Fitbits were 6 times more likely to get an ‘out of stock’ message than everyone else, so we quickly ordered more Fitbits and avoided running out of stock!"**

**Scenario:** A major online retailer was interested in how one of the hottest holiday products - Fitbit - was selling and what made Fitbit purchasers unique among other customers. The marketing team was able to simply right click on the “Fitbit” line item in their products report and quickly run a Segment IQ analysis. What they found was that users purchasing Fitbits were 6 times more likely to get an “out of stock” message than any other customer. After further analysis, the marketing team was able to direct these visitors to their brick and mortar stores while they waited on their purchasing department to order more Fitbits to ship. As a result, the retailer avoided more "out of stock" messages, and was able to satisfy more of the holiday demand.

**How to set up this comparison:** 

<table id="table_9018BEB4C2DE429FA773B250CB5C3E58"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Segment 1 </th> 
   <th colname="col3" class="entry"> Segment 2 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Use/Create a visitor-level segment where, </p> <p> 
     <ul id="ul_52E8ED6F4F7241D5ABE4EE7EA1E556D8"> 
      <li id="li_33750601AB2A43728834B29AF86D5CCF">Orders is greater than or equal to 1, AND </li> 
      <li id="li_4E09D1286DAE4BABA49E4834E73BDC28">Brand equals Fitbit </li> 
     </ul> </p> </td> 
   <td colname="col3"> <p>Use the <span class="wintitle"> Everyone Else </span> segment that gets generated automatically and encompasses everyone not included in Segment 1. </p> </td> 
  </tr> 
 </tbody> 
</table>

