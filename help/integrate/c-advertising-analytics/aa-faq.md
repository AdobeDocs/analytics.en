---
description: Frequently asked questions around Advertising Analytics.
title: Frequently Asked Questions
feature: Advertising Analytics
exl-id: 664a5641-1c79-439f-a9fb-2ff134574412
---
# Frequently Asked Questions

## Access/Entitlements {#section_5F558C5981F747F0AF375A9E4B75C93C}

<table id="table_6713C3B0B6734F768370F974EB5AC5E8"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Question </th> 
   <th colname="col2" class="entry"> Answer </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Q: Do I need to be an <b>Adobe Advertising Cloud or Adobe Advertising Cloud (AMO) customer</b> to access this functionality? </p> </td> 
   <td colname="col2"> <p>A: No, this functionality is available for non-Advertising Cloud and non-AMO customers. </p> <p>AMO customers can leverage the existing Analytics-AMO integration; they will not be able to use Ad Analytics. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Q: Which <b>Adobe Analytics SKUs</b> entitle you to the use of Advertising Analytics? </p> </td> 
   <td colname="col2"> <p>A: Advertising Analytics is available for Adobe Analytics <a href="https://www.adobe.com/data-analytics-cloud/analytics/select.html"  > Select </a>, <a href="https://www.adobe.com/data-analytics-cloud/analytics/prime.html"  > Prime </a>, and <a href="https://www.adobe.com/data-analytics-cloud/analytics/ultimate.html"  > Ultimate </a> SKUs. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Q: Do we have to <b>pay extra</b> to use Advertising Analytics? </p> </td> 
   <td colname="col2"> <p>A: No, outside of proper SKU provisioning Advertising Analytics does not incur extra cost. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Q: Will Advertising Analytics count against my <b>server call usage</b>? </p> </td> 
   <td colname="col2"> <p>A: No, Advertising Analytics uses a special data source type which does not incur server call costs. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Q: If I <b>already use Advertising Cloud/AMO</b>, can I still use the Advertising Analytics functionality? </p> </td> 
   <td colname="col2"> <p>A: Any compatible search engine account will pass into Advertising Analytics and will be displayed as read-only. All edits or updates should be handled in Advertising Cloud/AMO. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Q: I own the correct SKU, but I <b>cannot access</b> Advertising Analytics, why is that? </p> </td> 
   <td colname="col2"> <p>A: Advertising Analytics is available only for Adobe Analytics administrators; however, admins may grant access to non-admins. Please contact your administrator for access rights. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Using Advertising Analytics {#section_3A70C6C4D5A842B2981F0257A01F95FF}

<table id="table_4EC69262B7AB4DF49E736CF3B0362302"> 
 <thead> 
  <tr> 
   <th colname="col01" class="entry"> </th> 
   <th colname="col1" class="entry"> Question </th> 
   <th colname="col2" class="entry"> Answer </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Q: Which <b>search engine accounts</b> are included in Advertising Analytics? </p> </td> 
   <td colname="col2"> <p>A: Search engine accounts include Google AdWords and Microsoft Bing. </p> <p>Note: Yahoo Gemini was absorbed by Microsoft Bing on March 31, 2019. As a result, the Yahoo Gemini advertising account option is no longer available. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Q: Where do I go to <b>access</b> Advertising Analytics? </p> </td> 
   <td colname="col2"> <p>A: After logging in to Adobe Analytics, navigate to the <span class="uicontrol"> Admin </span> menu. Then select the new menu option <span class="uicontrol"> Advertising Analytics </span> to add your search engine accounts. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Q: How is the <b>data collected and passed into Analytics</b>? </p> </td> 
   <td colname="col2"> <p>A: Advertising Analytics utilizes a series of custom APIs to pass data from search engines via the Adobe Advertising Cloud into Analytics. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Q: What <b>search data</b> do I get with this integration? </p> </td> 
   <td colname="col2"> <p>A: You will get 1) Impressions, 2) Clicks, 3) Costs, 4) Quality Score, and 5) Average Position directly from the search engines as well as a 6) AMO ID Instances (Click Instances). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Q: Can I <b>break my Advertising Analytics data down</b> by other Analytics data (metrics/dimensions)? </p> </td> 
   <td colname="col2"> <p>A: No, the raw search data will come in as an independent data set. However, there is an Instances version of the click data that can be broken down by other Analytics data. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Q: What is the definition of the various <b>status indicators</b> for my accounts (Pending, Active, Paused, etc.)? </p> </td> 
   <td colname="col2"> <p>A: Each of these status indicators identifies the lifecycle stage of each search engine account. </p> 
    <ul id="ul_F68AD377B2F04A47B20355B2FF4CF345"> 
     <li id="li_05F8D7C6D00E4742A65373BE6FAA0448"><b>Pending</b> means that the account has been set up, but data is not yet getting pulled. </li> 
     <li id="li_42B1557A8AEC41008B85AF6E3F625CAB"><b>Paused</b> means the account was formerly set up but has been put in an inactive state. </li> 
     <li id="li_30B72CC171874F308A2B8CE552EA6930"><b>Active</b> means the account has been fully set up and is pulling search data. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Q: I am trying to <b>map my Advertising Analytics accounts to a specific report suite</b>, but it is not available in the Report Suite modal. Why? </p> </td> 
   <td colname="col2"> <p>A: Before you can assign a report suite to an Advertising Analytics account, the desired report suite needs to be <a href="/help/integrate/c-advertising-analytics/c-adanalytics-workflow/aa-provision-rs.md"  > provisioned for Advertising Analytics reporting </a>. </p> <p>This is done through a separate Admin page that is accessible from: <span class="ignoretag"> <span class="uicontrol"> Admin </span>  &gt; <span class="uicontrol"> Report Suites </span>  &gt; <span class="uicontrol"> [select Experience Cloud-enabled report suite] </span>  &gt; <span class="uicontrol"> Edit Settings </span>  &gt; <span class="uicontrol"> Advertising Analytics Configuration </span> </span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Q: Is it possible to assign a <b>Virtual Report Suite</b> (VRS) to an Advertising Analytics account? </p> </td> 
   <td colname="col2"> <p>A: Virtual Report Suites do not collect data, so you cannot directly map an Advertising Analytics account to a VRS. </p> <p>However, you can map the Advertising Analytics account to the parent Report Suite of the VRS that you want to see data in. </p> <p>The Search Engine metrics (click/cost/impressions) may not show up in the VRS unless you include an "or" condition in your segment logic based on the AMO ID (or its classification). Example: Adding "all hits where AMO ID exists" would include the search engine metrics in the segment. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Q: Are Advertising Analytics metrics reportable in the <b>Marketing Channels</b> report? </p> </td> 
   <td colname="col2"> <p>A: No, they are not included in the Marketing Channels report. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Q: <b>When</b> does the search data get pulled into Analytics? </p> </td> 
   <td colname="col2"> <p>A: The search data is pulled from the search engines around 6AM (06:00) in the time zone of your Analytics data center. This is when the AMO data is collected and inserted into the report suite. It is then converted into the report suite time zone as part of inserting the data into Analytics. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Q: What can be <b>captured before the click</b>? Do we bring impressions, cost, average position, etc. even without the click? </p> </td> 
   <td colname="col2"> <p>A: The AMO ID will capture the Search engine metrics: Impressions, Cost, Clicks, Average Position, and Average Quality Score. If there are no clicks, but there are impressions, then the impression/position/quality score data will still be sent to Analytics. Typically, if there are no clicks, then there is also no cost. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Q: What level is this data being captured at? <b>Visitor? Hit?</b> </p> </td> 
   <td colname="col2"> <p>A: The Search engine metrics are captured at the hit level and connected to the AMO ID (and its classifications). It is summary level data and not connected to visits/visitors. As such, the search engine metrics can only be used in segments that are hit-level scope and are based on the AMO ID (or its classifications). </p> <p>The AMO ID is also captured on the landing page in the hit for that page (which connects it to the visit/visitor) and will persist downstream to get credit for other Analytics metrics (until it expires or is overwritten by a new AMO ID). It is fully incorporated into the data set like any other eVar. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Q: Do we only capture google.com or <b>country versions</b> (like google.co.uk, google.it, google.fr, or google.de) as well? </p> </td> 
   <td colname="col2"> <p>A: The Ad Platform classification captures these values: "Google Adwords", and "Bing Ads". </p> <p>A common best practice is to include the country code as part of the naming of campaigns. You can then filter down or segment (e.g. if all campaigns start with countrycode_, then creating a segment where Campaigns (AMO ID) starts with "UK_" would provide you with only data for the UK). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Q: The metric "AMO Cost" is the cost paid for each keyword/ad as reported by the search engine. Is this Net cost or Gross cost? </p> </td> 
   <td colname="col2"> <p>A: "AMO cost" is only the cost paid to the search engines. It does not include any agency or search optimization/management platform fees. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Q: Are there plans to include other advertising channels such as <b>Display</b> or <b>Social</b>? </p> </td> 
   <td colname="col2"> <p>A: No, currently we do not have plans for these other channels on the roadmap. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Auto vs. Manual Tracking {#section_7437C4698A6D482EB7ED94A948390119}

<table id="table_9738FF8459574ED2937A860A665BE739"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Question </th> 
   <th colname="col2" class="entry"> Answer </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Q: When setting up my Advertising account, it states that<b> Auto Tracking</b> can lead to unintended consequences. What kinds of consequences may occur? </p> </td> 
   <td colname="col2"> <p>A: 
     <ul id="ul_59EFF4A2ECE947EBBDB6A9FF6D072FE0"> 
      <li id="li_8731E4B7D6ED4F0996B3630A35D5BAC4">Auto mode will attempt to append URL parameters to the end of the tracking templates/destination URLs in the correct format. <b>However, it is your responsibility to ensure that the added URL parameters persist correctly to the final landing page. </b> </li> 
      <li id="li_1202FE1FC88342378A60E8FE65E5426B">Auto mode can insert key words into the landing URL, and your web server may not support keywords with special characters. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Q: If I set up Manual or Automatic Tracking initially, <b>can I switch</b> to the other tracking mode later on? What are the implications? </p> </td> 
   <td colname="col2"> <p>A: Yes you can switch, but you will need to remove the old tracking logic before making the switch. This may result in some downtime of tracking on the day the switch is made (especially if moving from manual to automatic). As such, it is recommended to not switch unless absolutely necessary. </p> 
    <ul id="ul_3F3CADD1C97B4947A13837CEE63A599D"> 
     <li id="li_CB9265951FD040388AEAB9EAD790A36E"><b>Switching from Manual to Automatic</b>: Remove the manual additions to the tracking templates and then switch the toggle in the Advertising Analytics UI from manual to Automatic and save the setting. Note that it may take up to x hours for the system to populate the automatic tracking codes. </li> 
     <li id="li_2B6ED1342E2D443B8AF26D03532AB8E4"><b>Switching from Automatic to Manual</b>: Update the toggle from manual to automatic in the Advertising Analytics setup UI and then deploy the manual tracking codes as quickly as possible. While deploying the manual tracking codes, if you see the automatic tracking codes in the Search Engine tracking templates, remove them. </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>
