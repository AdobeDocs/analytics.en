---
description: This reference table defines the fields, options, and hit attributes you can select on the Marketing Channel Processing Rules page.
seo-description: This reference table defines the fields, options, and hit attributes you can select on the Marketing Channel Processing Rules page.
seo-title: Marketing Channel processing rules - definitions
solution: Analytics
subtopic: Marketing channels
title: Marketing Channel processing rules - definitions
topic: Reports and analytics
uuid: 4e71ff5b-912a-4dc0-9c22-4be74c5e3cc0
---

# Marketing Channel processing rules - definitions

This reference table defines the fields, options, and hit attributes you can select on the Marketing Channel Processing Rules page.

<table id="table_C18A0F1C9E214EB585A29801BA2400F8"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Term </p> </th> 
   <th colname="col2" class="entry"> <p>Definition </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>All </p> </td> 
   <td colname="col2"> <p>Activates this channel only when all of the rules in the numbered rule are true. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Any </p> </td> 
   <td colname="col2"> <p>Activates this channel when any of the rules in the rule set are true. This option is available only if more than one rule exists in the numbered rule. </p> </td> 
  </tr>
  <tr> 
   <td colname="col1"> <p>AMO ID </p> </td> 
   <td colname="col2"> <p>The primary tracking code used by the Advertising Cloud and Advertising Analytics integrations. When one of these integrations is enabled, then the tracking code prefix can be used to identify Advertising Cloud specific channels. Use "AMO ID" starts with "AL" for Search, "AC" for Display, or "AO" for Social. When the AMO ID is used in marketing channels the click/cost/impression metrics can be attributed to the correct channel (when not configured, these metrics will go to Direct or None). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>AMO ED ID </p> </td> 
   <td colname="col2"> <p>The secondary tracking code used by Advertising Cloud. The main purpose of this tracking code is to serve as the key for sending data back to Ad Cloud. It can however also be used to identify display ClickThroughs vs. display ViewThroughs if you desire to see these as two separate marketing channels. This can be done by setting the marketing channel logic for "AMO EF ID" ends with ":d" for Display ClickThroughs or "AMO EF ID" ends with ":i" for Display ViewThroughs. If you do not desire to split Display into two channels, then use the AMO ID dimension instead. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Conversion Variables </p> </td> 
   <td colname="col2"> <p>Consists of eVars that are enabled for this report suite, and applies only when these variables are set via the Adobe code on the page. </p> <p>See the <a href="https://marketing.adobe.com/resources/help/en_US/sc/implement/oms_sc_implement.pdf"  > Implementation Guide </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Exists </p> </td> 
   <td colname="col2"> <p>Several selections are available, including: </p> <p> 
     <ul id="ul_FE39B5F36235441FB757CC73CA2C4F51"> 
      <li id="li_6DC09918D69B443091AB94DB773D5189"> <p> <span class="uicontrol"> Does Not Exist </span>: Specifies that the hit attribute does not exist on the request. For example, in a referring domain, if the user types a URL or clicks a bookmark, the referring domain attribute does not exist. </p> </li> 
      <li id="li_3AB958F997974682824E85014CA266D6"> <p> <span class="uicontrol"> Is Empty </span>: Specifies that a hit attribute exists, usually an eVar or query string parameter, but there is no value associated with the hit attribute. </p> </li> 
      <li id="li_25EDA39748D141BA8173CC4C41035ABA"> <p> <span class="uicontrol"> Does Not Contain </span>: Lets you specify, for example, that a referring domain does not contain a specific value (as opposed to using the selection <span class="term"> Contains </span>. </p> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Identify the channel as </p> </td> 
   <td colname="col2"> <p>Associates the rule with a marketing channel that you added to the <span class="wintitle"> Marketing Channel Manager </span> page. </p> <p>See <a href="../../components/c-marketing-channels/c-channels.md#task_98C9D3F5DBBC4B198E0A9ED4D3891E03"   > Add marketing channels </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Matches Paid Search Detection Rules </p> </td> 
   <td colname="col2"> <p>A paid search detected by Adobe. Paid searches are when companies pay a fee for the search engine to list their site. Paid searches usually appear at the top or the right side of the search results. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Matches Natural Search Detection Rules </p> </td> 
   <td colname="col2"> <p>A non-paid search detected by Adobe reporting. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Referrer Matches Internal URL Filters </p> </td> 
   <td colname="col2"> <p> A visit whose page URL matches an internal URL filter, as defined for the report suite in Admin Tools. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Referrer Does Not Match Internal URL Filters </p> </td> 
   <td colname="col2"> <p>The referring URL does not match an internal URL filter, as defined for the report suite in Admin Tools. You can use this setting with <span class="term"> Page URL </span> and <span class="term"> Exists </span> to set up a catch-all rule, so that no visits land in the <a href="../../components/c-marketing-channels/c-faq.md#section_451E42994DA247A8A7B8559C715A5EE7" type="section"  > No Channel Identified </a> section of the report. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Ignore hits matching internal URL filters </p> </td> 
   <td colname="col2"> <p>(For referrers) Tracks only hits coming from externally referred sites. Typically, leave this setting enabled unless you want to include internal traffic. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Is First Page of Visit </p> </td> 
   <td colname="col2"> <p>The first page of a visit detected by Adobe reporting. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Page </p> </td> 
   <td colname="col2"> <p>The page name of a web page on your site that is tagged using Adobe’s web beacon. This value is equivalent to <span class="varname"> s.pageName </span>. Examples include <span class="varname"> Home Page </span> and <span class="varname"> About Us </span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Page Domain </p> </td> 
   <td colname="col2"> <p>The domain of the page on which the visitor lands, such as <span class="filepath"> products.example.co.uk </span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Page Domain and Path </p> </td> 
   <td colname="col2"> <p>The domain and path, such as <span class="filepath"> products.example.co.uk/mens/pants/overview.html </span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Page Root Domain (TLD+1) </p> </td> 
   <td colname="col2"> <p>The root domain of the page on which the visitor lands, such as <span class="filepath"> example.co.uk </span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Page URL </p> </td> 
   <td colname="col2"> <p>The URL of a web page on your site. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Referring Domain </p> </td> 
   <td colname="col2"> <p>The domain your visitors came from before they visited your site, for example, referrers coming from <span class="filepath"> abcsite.com </span> versus <span class="filepath"> xyzsite.com </span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Query String Parameter </p> </td> 
   <td colname="col2"> <p>If a page URL on your site looks like <span class="filepath"> https://example.com/?page=12345&amp;cat=1 </span>, then page and cat are both query string parameters. (See <span class="filepath"> https://en.wikipedia.org/wiki/Query_string </span>.) </p> <p>You can specify only one query string parameter per rule set. To add additional query string parameters, use <span class="uicontrol"> ANY </span>&nbsp;as your operator, then add new query string parameters to the rule. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Referrer </p> </td> 
   <td colname="col2"> <p>The web page location (full URL) your visitors were at before coming to your site. A referrer exists outside your defined domain. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Referring Domain and Path </p> </td> 
   <td colname="col2"> <p>A concatenation of the Referring Domain and URL path. Examples include: </p> <p> <span class="filepath"> www.example.com/products/id/12345 </span> </p> <p> <span class="filepath"> ad.example.com/foo </span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Referring Parameter </p> </td> 
   <td colname="col2"> <p>A query string parameter on the referrer URL. For example, if your visitors come from <span class="filepath"> example.com/?page=12345&amp;cat=1 </span>, then page and cat are the referring parameters. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Referring Root Domain </p> </td> 
   <td colname="col2"> <p>The root domain of the referrer. A referrer exists outside of your defined domain. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Search Engine </p> </td> 
   <td colname="col2"> <p>A search engine like Google or Yahoo! that brought visitors to your site. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Search Keywords </p> </td> 
   <td colname="col2"> <p>A word used to perform a search using a search engine. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Search Engine + Keywords </p> </td> 
   <td colname="col2"> <p>A concatenation of the Search Keyword and Search Engine to uniquely identify the search engine. For example, if you search for the word computer, the search engine and keyword are identified as follows: </p> 
    <code>
      Search&nbsp;Tracking&nbsp;Code&nbsp;= &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;"&lt;search_type&gt;:&lt;search&nbsp;engine&gt;:&lt;search&nbsp;keyword&gt;"&nbsp;where &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;search_type&nbsp;=&nbsp;"n"&nbsp;or&nbsp;"p",&nbsp;search_engine&nbsp;=&nbsp;"Google",&nbsp;and&nbsp;search_keyword&nbsp;= &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;"computer" 
    </code> <p><b>Note:</b> n = natural; p = paid </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Set the channel's value to </p> </td> 
   <td colname="col2"> <p>In addition to knowing which marketing channel brings a visitor to your site, you can know which banner ad, search keyword, or email campaign within the channel is getting credit for a visitor’s site activity. This ID is a channel value that is stored along with the channel. Often this value is a campaign ID embedded in the landing page or the referring URL; in other cases it is the search engine and search keyword combination, or the referring URL that most correctly identifies the visitor from a particular channel. </p> </td> 
  </tr> 
 </tbody> 
</table>



