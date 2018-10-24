---
description: Answers to frequently asked questions about Adobe's data retention policy for Adobe Analytics.
seo-description: Answers to frequently asked questions about Adobe's data retention policy for Adobe Analytics.
seo-title: Data retention FAQ
solution: Analytics
title: Data retention FAQ
uuid: 6a27e0c5-4414-49b6-b024-36745cd65140
index: y
internal: n
snippet: y
---

# Data retention FAQ

Answers to frequently asked questions about Adobe's data retention policy for Adobe Analytics.

## Background {#section_398C549965E94A65B2EA2212056D4AFD}

The European Union’s General Data Protection Regulation (GDPR), which applies as from May 25, 2018, provides that Adobe, in its role as your data processor, must take appropriate measures to assist its customers in fulfilling access, deletion, and other requests from individuals. Applying appropriate, secure, and timely deletion policies is an important part of complying with this obligation.

GDPR applies to all customers that market to or process information of EU citizens. Therefore, GDPR is a worldwide regulatory change.

As a result, Adobe would like to work with you to implement a data retention policy before GDPR takes effect on May 25, 2018.

Going forward, Adobe will begin applying data retention as currently specified in customer contracts for Adobe Analytics, unless other arrangements are made. Most Adobe Analytics contracts state that Adobe may delete data after 25 months.

## Analytics Data Retention - Frequently Asked Questions {#section_A384B221313D4857B71EEC3F3F73E684}

<table id="table_E37C41A0F1D44A2BBE39D80201BAFA32"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Question </th> 
   <th colname="col2" class="entry"> Answer </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><b> How does setting my data retention benefit my company?</b> </p> </td> 
   <td colname="col2"> <p> By setting your data retention period, this helps you, our customer and the data controller, prepare for regulatory requirements worldwide (specifically, in Europe, some Latin America countries, and most APAC countries) that require companies to keep data only as long as necessary to perform a service. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b> What is the most common contracted data retention period?</b> </p> </td> 
   <td colname="col2"> <p> Most contracts state, by default, that Adobe has the right to delete data after 25 months. When this data retention policy is in place, Adobe deletes Adobe Analytics data older than 25 months, based on the timestamp of the data. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>How do I decide on my data retention?</b> </p> </td> 
   <td colname="col2"> <p>Your company, as the data controller, should identify stakeholders (such as your marketing, analytics, and privacy teams) within your organization responsible for making decisions about data retention. Your organization is in the best position to know the appropriate period for which Adobe Analytics data should be retained. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b> How do I enroll in data retention?</b> </p> </td> 
   <td colname="col2"> <p> Contact your Customer Success Manager to set your data retention and learn your options. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b> What Is the data retention window?</b> </p> </td> 
   <td colname="col2"> <p> The data retention policy defines a rolling data retention window in which complete data can be viewed and reported. The data retention window is determined as follows: </p> <p><span class="codeph"> start date</span> = current date - data retention period </p> <p><span class="codeph"> end date</span> = current date </p> <p> Data is included in the data retention window if the timestamp of the data is between the start date and end date. The timestamp is defined as the date of the transaction represented by the data, which may or may not match the date that the data was received by Adobe. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b> Can my company request that data be deleted sooner than 25 months?</b> </p> </td> 
   <td colname="col2"> <p> Yes, though your contract should be updated to define the specific terms that are agreed upon. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b> Can my company extend their retention settings beyond 25 months?</b> </p> </td> 
   <td colname="col2"> <p>Before May 25, 2018, customers are eligible for up to 1 additional year of data retention for free for a total of 37 months of data retention. These customers will retain a 37 month rolling data retention period at no additional charge as long as they remain an Adobe Analytics customer. </p> <p>They can extend data retention beyond 37 months by purchasing an extension. </p> <p>After May 25, 2018 the retention period can be extended beyond 25 months in increments of one year by purchasing an extension(s). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Can I request a copy of my data prior to it being deleted?</b> </p> </td> 
   <td colname="col2"> <p> Yes, if requested, Adobe will provide a historical data dump of the raw, hit-level data that is stored in data warehouse. The method for delivering this data will vary based on data size. Costs may vary. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b> How do I request a copy of my data?</b> </p> </td> 
   <td colname="col2"> <p> Contact Customer Care and be ready to provide the following information about the data you want to export: </p> 
    <ol id="ol_009A840D23F4400CB0E5488D06174431"> 
     <li id="li_06C444BAB8EE4F13B259159C99FB4DAC"> Report Suite Names </li> 
     <li id="li_803645ECCADC4B0988D7505E0BA0D826">Date Range </li> 
     <li id="li_F8087EC72E4048678DA5AD8E9DD2B993">Feed Interval (Hourly/Daily) </li> 
     <li id="li_7703632C80A14693AFACCDD7DB22978D">Column Preset (All columns / Selected columns) </li> 
     <li id="li_3A9E57C5AE4B43BB9299E553566BF353">Destination Server details (S3/ FTP/ SFTP/Azure) </li> 
     <li id="li_49FE9D0C98C24CC4BD4B05E43A24D704">Destination Server details (S3/ FTP/ SFTP/Azure) </li> 
     <li id="li_8EA4500327BD4DB1AE4B1624B58B4230">Any customization required like File rename/ encryptions </li> 
     <li id="li_BB7D729100494563916A0EA1B6D2403B">Remove Escaped Characters [CR/LF/Tab] - (True/False) </li> 
    </ol> <p> After providing the above information, your Adobe representative will let you know the cost of exporting the data. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>When will Adobe start deleting my data?</b> </p> </td> 
   <td colname="col2"> <p>Contact your Customer Success Manager for the specific time frame your data is scheduled to be deleted. Once a customer contacts Customer Care and enrolls in data retention, their data will be deleted on a rolling monthly basis. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>How often will my data be deleted?</b> </p> </td> 
   <td colname="col2"> <p> After data retention is applied, data will be deleted immediately on a recurring monthly basis. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b> What should I do if my decision process is taking longer than expected?</b> </p> </td> 
   <td colname="col2"> <p> Contact Customer Care to set your policy on hold. This will let Adobe Analytics know that you need more time to work on finalizing a decision. </p> </td> 
  </tr> 
 </tbody> 
</table>

