---
description: Provides answers and troubleshooting suggestions to some of the most frequently asked Analytics questions.
keywords: Troubleshooting Analytics
seo-description: Provides answers and troubleshooting suggestions to some of the most frequently asked Analytics questions.
seo-title: Frequently Asked Troubleshooting Questions
title: Frequently Asked Troubleshooting Questions
uuid: 304d3da4-49e0-4166-a803-5301c64845de
index: y
internal: n
snippet: y
translate: y
---

# Frequently Asked Troubleshooting Questions

For frequently asked questions about Analytics Implementation, go [ here ](https://marketing.adobe.com/resources/help/en_US/sc/implement/faq.html). 

* [ Account/Access Issues ](../reports_analytics_bucket/frequently-asked-questions.md#section_E1B9D3359C5347369D62B612A8F1F7B0)
* [ Troubleshooting Reports ](../reports_analytics_bucket/frequently-asked-questions.md#section_0AC7CE1DCA00492EBC83F05DDA0B217C)
* [ Configuring Reports ](../reports_analytics_bucket/frequently-asked-questions.md#section_DD40BE6889404BE3B36F3E39E1E18612)
* [ Interpreting Reports ](../reports_analytics_bucket/frequently-asked-questions.md#section_E04ECEAD4C9C4C4C97BA396A8A9FF85B)
* [ Customizing Reports ](../reports_analytics_bucket/frequently-asked-questions.md#section_B5112FD4631D4A1994A790812684B789)
* [ Dashboards ](../reports_analytics_bucket/frequently-asked-questions.md#section_B2197214B3C54BC1AC4C39114292686E)
* [ Events ](../reports_analytics_bucket/frequently-asked-questions.md#section_9CAE843868D741AFA48CEF44E59AFE21)
* [ Segmentation ](../reports_analytics_bucket/frequently-asked-questions.md#section_90C6137813784A80A266680715613DF2)
* [ Processing Rules ](../reports_analytics_bucket/frequently-asked-questions.md#section_D2A384C080D04F09905FBC59F4923A39)
* [ Data Warehouse ](../reports_analytics_bucket/frequently-asked-questions.md#section_67D6B9CC8BE140228441D210ED160314)
* [ Classifications ](../reports_analytics_bucket/frequently-asked-questions.md#section_1A01444C17CD4145ADC731DD1FB0F058)
* [ Data Feeds ](../reports_analytics_bucket/frequently-asked-questions.md#section_F1B81518893F4A0C85B5CD2BE44A9998)

## Account/Access Issues {#section_E1B9D3359C5347369D62B612A8F1F7B0}


<table id="table_E0CB584B7CF74C75B1EEB9AF4C274CBA"> 
 <tbody> 
  <tr> 
   <td colname="col1"> <p><b>Q: My Analytics/Experience Cloud account has been locked, how do I unlock it? </b> </p> </td> 
   <td colname="col2"> <p>A: To reactivate the account, contact your organization's Adobe administrator to <a href="https://marketing.adobe.com/resources/help/kb/en_US/analytics/kb/locked-accounts.html" format="https" scope="external"> unlock the account </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Q: How do I reset the password for a user?</b> </p> </td> 
   <td colname="col2"> <p>A: You need to be an Admin user to be able to change passwords. Go to 
     <ignoretag> 
      <span class="uicontrol"> Admin </span>  &gt; 
      <span class="uicontrol"> User Management </span>  &gt; 
      <span class="uicontrol"> [Select the User Name] </span>  &gt; 
      <span class="uicontrol"> Edit </span> 
     </ignoretag> and enter the new password under <span class="uicontrol"> Login </span>. <a href="../reports_analytics_bucket/getting_started.md#topic_0028683CA91A4526BE987363F8005A60" format="dita" scope="local"> More... </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Q: How do I know when a user logged in and what modifications they made?</b> </p> </td> 
   <td colname="col2"> <p>A: You can access logs from 
     <ignoretag> 
      <span class="uicontrol"> Admin </span>  &gt; 
      <span class="uicontrol"> Logs </span> 
     </ignoretag>. </p> <p>Admin logs let you see changes made by administrators. Usage and Access logs lets you view the account activity. Report Suite change logs lets you see modifications made to the report suites. <a href="https://marketing.adobe.com/resources/help/en_US/reference/logs.html" format="https" scope="external"> More... </a> </p> </td> 
  </tr> 
 </tbody> 
</table>


## Troubleshooting Reports {#section_0AC7CE1DCA00492EBC83F05DDA0B217C}


<table id="table_CEA93B037FA348548448E22BED60B0FC"> 
 <tbody> 
  <tr> 
   <td colname="col1"> <p><b>Q: Why are reports not showing data even though it's being sent to Adobe Analytics?</b> </p> </td> 
   <td colname="col2"> <p>A: The most common reason traffic sources reports don't populate data is that the Internal URL Filter List isn't defined. To check which Internal URL Filters have been set up on a report suite, follow the steps below: </p> 
    <ol id="ol_6B5ABA39E6684B66B4A3D66C311CCA63"> 
     <li id="li_1ACEAC0BB9C54687B26B09B8AFFB128C">Go to 
      <ignoretag> 
       <span class="uicontrol"> Admin </span>  &gt; 
       <span class="uicontrol"> Report Suites </span> 
      </ignoretag> and select the report suite from the list of available suites. </li> 
     <li id="li_216D84B2986F45D3A8B83F42DC3C9FA9">Go to 
      <ignoretag> 
       <span class="uicontrol"> Edit Settings </span>  &gt; 
       <span class="uicontrol"> General </span>  &gt; 
       <span class="uicontrol"> Internal URL Filters </span> 
      </ignoretag>. </li> 
     <li id="li_FAFFD512CE554200AFAF15E2573F40CB">Remove the rule listing a period (.) as a filter, and add your own site. </li> 
    </ol> <p>As your site collects data, there are many external factors that can drastically affect data collection or reporting. <a href="https://helpx.adobe.com/analytics/kb/spikes-and-drops.html#" format="dita" scope="local"> Here </a> is a list of potential explanations as to why certain variables or overall traffic dramatically increases or decreases. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Q: Why am I unable to see a report/event in the menu?</b> </p> </td> 
   <td colname="col2"> <p>A: If you cannot see a custom report or event or site section, go to 
     <ignoretag> 
      <span class="uicontrol"> Admin </span>  &gt; 
      <span class="uicontrol"> Report Suites </span>  &gt; 
      <span class="uicontrol"> Edit Settings </span>  &gt; 
      <span class="uicontrol"> General </span>  &gt; 
      <span class="uicontrol"> Customize menus </span> 
     </ignoretag>. Check the 'Toggle Visibility' option for the menu item. Hidden items appear with a gray line pattern in the Menu Customization page. <a href="https://marketing.adobe.com/resources/help/en_US/reference/customize_menus.html" format="html" scope="external"> More... </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Q: Why don't full page names get captured?</b> </p> </td> 
   <td colname="col2"> <p>A: Many Adobe Analytics reports are based on variables populated by each organization. The limitations for allowable characters in these variables are as follows: </p> 
    <ul id="ul_BC6699FDE9924008898EF5D03C4F6CA9"> 
     <li id="li_3D555D5EA45242239B1DE4341B0CA99B">PageName and all custom traffic variables (props): 100 bytes </li> 
     <li id="li_89890E600A074E0F9853877AE07B0052">Tracking Codes and all custom conversion variables (eVars): 255 bytes </li> 
     <li id="li_F2237514208940D48C6D84FEC2C80B45">URL and Referrer: 255 bytes </li> 
     <li id="li_895F908225CE4A9F81880B87E69C7926">Hierarchy variables: 255 bytes total across all levels </li> 
     <li id="li_4504428501374B91A922DD3D1162DF90">Purchase ID: 20 bytes </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Q: Why are we experiencing latencies in our report suite?</b> </p> </td> 
   <td colname="col2"> <p>A: Real-time reporting allows some traffic metrics to be available within minutes, while conversion and other processing-intensive data is usually available within 30-90 minutes. Though the Experience Cloud platform is robust, there are a few situations that may lead to delays in reporting. This delay is referred to as <a href="https://helpx.adobe.com/analytics/using/latency.html" format="https" scope="external"> report suite latency </a>. Contributing factors to latency are: </p> 
    <ul id="ul_801F1FF6DF9045988C2C70BBBA3A52AE"> 
     <li id="li_0B57625B4BE84889A2A23FFB1B914BA7">Unexpected traffic spike </li> 
     <li id="li_7C51DC7685DA4B1891F39508D99FB5EE">Normal hardware issues </li> 
     <li id="li_A5B94F3033474D20B6D5A7F93FFFA1BA">Abnormal data </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Q: Why is the Reports &amp;amp; Analytics Interface slow/lagging/timing out?</b> </p> </td> 
   <td colname="col2"> <p>The following factors contribute to longer report generation times. Increasing one of these factors might not result in a timeout for that report, but it might delay other reports in the report suite queue and cause a subsequent report to timeout: Report Time Range, Number of metrics, Number of breakdowns, Segment complexity, Number of unique values. <a href="https://marketing.adobe.com/resources/help/en_US/reference/report_troubleshooting.html" format="https" scope="external"> More... </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Q: Why do I see no referrer traffic in reports? How do I filter out internal traffic?</b> </p> </td> 
   <td colname="col2"> <p>A: Internal URL filters identify the referrers that you consider internal to your site. This means that traffic coming from the web pages internal to your domain will not be counted as referrers. <a href="https://marketing.adobe.com/resources/help/en_US/reference/internal_URL_filter_admin.html" format="https" scope="external"> More... </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Q: Mobile reports - Why is breakdown not available for iPhone device versions?</b> </p> </td> 
   <td colname="col2"> <p>A: <a href="https://helpx.adobe.com/analytics/kb/comparing-iphone-device-versions.html" format="https" scope="external"> iOS devices report </a> their firmware version in their user agent string, not the device version. Therefore, it is difficult to break down iPhones by their corresponding device versions. Because Adobe uses the device's user agent to populate mobile reports, it's currently impossible to obtain screen resolution without additional implementation. </p> </td> 
  </tr> 
 </tbody> 
</table>


## Configuring Reports {#section_DD40BE6889404BE3B36F3E39E1E18612}


<table id="table_4D1786FB13D74A0EB9238756873D74E9"> 
 <tbody> 
  <tr> 
   <td colname="col1"> <p><b>Q: Why did some settings not work after copying Report Suite settings?</b> </p> </td> 
   <td colname="col2"> <p>A: When creating a new report suite based on an existing report suite in the Admin Console, there are several custom settings that are not copied over, as they are generally contract dependent. <a href="https://marketing.adobe.com/resources/help/kb/en_US/analytics/using/report-suite-settings-not-copied.html#" format="dita" scope="local"> More... </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Q: Does changing the Base Currency of a Report Suite affect historical data?</b> </p> </td> 
   <td colname="col2"> <p>A: Once the report suite has been created, its currency is unalterable unless an Adobe representative alters the report suite's back end settings. If you created a report suite with the incorrect currency code, have one of your organization's supported users contact Adobe ClientCare. They will be able to correct the setting. <a href="https://marketing.adobe.com/resources/help/kb/en_US/analytics/using/currency-conversion.html" format="https" scope="external"> More... </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Q: What is Paid Search detection and how do I configure it?</b> </p> </td> 
   <td colname="col2"> <p>A: Paid Search Detection differentiates paid from natural searches in the Search Engines and Search Keywords reports. You can specify the search engines where you use paid ads, and specify a character string found in the URL of a visit from a paid ad. <a href="https://marketing.adobe.com/resources/help/en_US/reference/paid_search_detection.html" format="https" scope="external"> More... </a> </p> </td> 
  </tr> 
 </tbody> 
</table>


## Interpreting Reports {#section_E04ECEAD4C9C4C4C97BA396A8A9FF85B}


<table id="table_31372F2CD5AC48158D7B1D002938C776"> 
 <tbody> 
  <tr> 
   <td colname="col1"> <p><b>Q: Why do my line items totals not match the report total?</b> </p> </td> 
   <td colname="col2"> <p>Sometimes, the sum of line items may be higher than the report total. <a href="https://marketing.adobe.com/resources/help/kb/en_US/analytics/kb/sum-line-items-different-from-total.html" format="https" scope="external"> More... </a> </p> <p>Sometimes, the report total may be higher than sum of line items. Here are some potential reasons: </p> 
    <ul id="ul_317BFED9F90D412C9268AC98EC2E4A8F"> 
     <li id="li_450B3D07B66C4187B51D1C1C6E46D50B">Some reports, especially in previous versions of Adobe Analytics, report total metrics across the entire site as opposed to the specific variable you are looking at. </li> 
     <li id="li_AB78F4BC869B43E082AECCC9409CFEB6">If you exclude the None line item from reporting, it can make the sum of line items less than the total. </li> 
     <li id="li_B4CDB9519C6840599428FFC3A655BA5C">In the context of some pathing reports (such as the Return Frequency report), data is displayed only for users who return for a second visit. The total, however, is site wide. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Q: How do the metrics "page views", "instances", and "occurrences" differ?</b> </p> </td> 
   <td colname="col2"> <p>A: <b>Page views</b> display the number of times a variable was defined or persisted across all s.t() function calls within the given date range. </p> <p><b>Instances</b> show the number of times a given variable was defined in any image request, including s.t() and s.tl() functions. </p> <p><b>Occurrences</b>: This metric is exclusive to Ad Hoc Analysis, which counts the number times a variable was defined or persisted across both s.t() and s.tl() functions. <a href="https://marketing.adobe.com/resources/help/kb/en_US/analytics/kb/Comparing-pageviews-and-instances.html" format="https" scope="external"> More... </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Q: What do None, Unspecified, Other, or Unknown line items in reports mean?</b> </p> </td> 
   <td colname="col2"> 
    <ul id="ul_4C7738C25BC54987A3409AE56CD2001D"> 
     <li id="li_F0E76560AF144657A7646D62DE17D405"><b>None</b>: This breakdown is seen fairly frequently in the Adobe Experience Cloud. There are four main reasons for a None result: a) A conversion event fires without a conversion variable; b) Non-mobile hits in mobile reports; c) Mobile hits in technology reports; or d) Merchandising eVars that do not fire at or before a conversion event. <a href="https://helpx.adobe.com/analytics/kb/none-unspecified-and-unknown.html" format="https" scope="external"> More... </a> </li> 
     <li id="li_0DEA0631E7B44AEB8A324FFC04B624EF"><b>Unspecified</b>: Similar to "None," this result occurs when the breakdown is unobtainable or otherwise unavailable. This could be due to a) Unclassified data in classification reports; b) Correlation reports where only one variable fired; c) Non-browser hits when viewing Technology reports; or d) Hierarchy reports with different amounts of levels. <a href="https://helpx.adobe.com/analytics/kb/none-unspecified-and-unknown.html" format="https" scope="external"> More... </a> </li> 
     <li id="li_B3AC232B2DA446ED961863221CDB6505"><b>Other</b>: Though slightly less common in reporting, "Other" can occur when a) Pages fire outside your internal URL filters, or b) Visitors using an infrequently used browser. <a href="https://helpx.adobe.com/analytics/kb/none-unspecified-and-unknown.html" format="https" scope="external"> More... </a> </li> 
     <li id="li_2762B20967F7475691987DFC1AE66341"><b>Unknown</b>: This can indicate either a) Non-browser hits when viewing Technology reports, or b) You are using segments in which a variable in the rule is disabled. <a href="https://helpx.adobe.com/analytics/kb/none-unspecified-and-unknown.html" format="https" scope="external"> More... </a> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Q: Why are the latest versions of Chrome/Firefox/Safari classified under 'unknown' versions?</b> </p> </td> 
   <td colname="col2"> <p>A: When you view a Browsers report, it might contain a browser with an <a href="https://helpx.adobe.com/analytics/kb/browser-unknown-version.html" format="https" scope="external"> unknown version </a>. Adobe Analytics uses a lookup table to populate the Browsers report. These lookup table entries are version specific. Therefore, when an organization (such as Mozilla) updates their browser, Analytics doesn't recognize the exact version used. When this event occurs, it specifies the general browser followed with an unknown version. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Q: Why is traffic showing up under 'Low Traffic' ?</b> </p> </td> 
   <td colname="col2"> <p>A: When a report has a large number of unique values, Adobe Analytics reports provide functionality to ensure that the most important values appear in your report. </p> <p>At the beginning of each calendar month, Analytics reports include the first 500,000 values received for any single variable in reports. This includes page names, and other traffic and commerce variables. For example, each unique page name on your site counts toward this total. </p> <p>After 500,000 unique values are received, Analytics reports begin to optimize which values are displayed in reports. When new values are received after this threshold, the system initially groups these values in a single line item in reports titled "(Low-Traffic)". (Note: this line item was previously titled "Uniques Exceeded".) <a href="https://marketing.adobe.com/resources/help/en_US/reference/metrics_uniques_high_numbers.html" format="https" scope="external"> More... </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Q: What are IAB Bot rules and where can I get a list of those that are being filtered (when enabled on the report suite)?</b> </p> </td> 
   <td colname="col2"> <p>A: The IAB database in maintained by a third-party vendor with a standardized database that is updated at regular intervals. Once <a href="https://marketing.adobe.com/resources/help/en_US/reference/bot_rules.html" format="https" scope="external"> bot rules </a> are enabled on the report suite, all the bots maintained by IAB automatically get filtered. The database can be accessed here: <a href="http://www.iab.net/sites/spiders/form.php" format="http" scope="external"> http://www.iab.net/sites/spiders/form.php </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Q: What are the main differences between a Tracking Codes report and a marketing channel that is configured to capture campaign variable values?</b> </p> </td> 
   <td colname="col2"> <p>A: There are four main differences: a) Allocation, b) Prior marketing channels bucket data before the given rule, c) Other marketing channels can steal last-touch credit, and d) Expiration differences. <a href="https://marketing.adobe.com/resources/help/kb/en_US/analytics/kb/comparing-tracking-codes-and-marketing-channels.html" format="https" scope="external"> More... </a> </p> </td> 
  </tr> 
 </tbody> 
</table>


## Customizing Reports {#section_B5112FD4631D4A1994A790812684B789}


<table id="table_4CDF8BC68327450F88B6FEF151D9968A"> 
 <tbody> 
  <tr> 
   <td colname="col1"> <p><b>Q: How do I exclude data from a particular IP addresses in my report suite?</b> </p> </td> 
   <td colname="col2"> <p>A: You can eliminate data from internal website activities, such as site testing and employee usage, from your reports. This feature allows you and your colleagues to visit your site without skewing your traffic data. You may exclude up to 50 different IP addresses. <a href="https://marketing.adobe.com/resources/help/en_US/reference/exclude_IP.html" format="https" scope="external"> More... </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Q: Is it possible to delete or hide a report suite?</b> </p> </td> 
   <td colname="col2"> <p>A: No, it is not possible to delete a Report Suite once it has been created. However, you can hide it if it's no longer required. <a href="https://marketing.adobe.com/resources/help/en_US/reference/c_hide_report_suites.html" format="https" scope="external"> More... </a> </p> <p>To hide a Report Suite, go to <span class="uicontrol"> Admin </span>&gt; <span class="uicontrol"> Company Settings </span> and check <span class="uicontrol"> Hide </span> for the report suite. <a href="https://marketing.adobe.com/resources/help/en_US/reference/c_hide_report_suites.html" format="https" scope="external"> More... </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Q: Can I configure the number of rows that get downloaded for a report?</b> </p> </td> 
   <td colname="col2"> <p>A: Due to differences in processing mechanisms and platforms, the various types of downloadable and scheduled reports available in Adobe Analytics have different limitations regarding the <a href="https://marketing.adobe.com/resources/help/en_US/sc/user/scheduling.html" format="https" scope="external"> maximum number of rows </a> they can process in a single request. Here are the limits: </p> 
    <ul id="ul_91CF6FFEBFED4069B9EEF701F240810D"> 
     <li id="li_E0BF4CE988364F58845022F1B2686746">Word, CSV, Excel, HTML and PDF: The same number of rows visible in the report. By default this limit is 50 rows but can increase up to 200. Breakdown reports have a hard limit of 50 rows. </li> 
     <li id="li_98F9162597BC49EC8C0160017EB70052">Data Extracts: 50,000 rows </li> 
     <li id="li_15C9672767424241A1531F48AAA293DA">Data Warehouse: Unlimited </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>


## Dashboards {#section_B2197214B3C54BC1AC4C39114292686E}


<table id="table_F43A983E65D34995B94DA13931BBCA91"> 
 <tbody> 
  <tr> 
   <td colname="col1"> <p><b>Q: How do I push dashboard to multiple users?</b> </p> </td> 
   <td colname="col2"> <p>A: When you <a href="../reports_analytics_bucket/dashboard/dashboard_manage.md#task_2776BDE3FBC64E66B78DB6D6A53AAF49" format="dita" scope="local"> push dashboards to users </a>, the dashboards become available in user's Shared Dashboards menu. </p> 
    <ol id="ol_3BCBCAFCBA85450EBB5E6C010ACDCA2B"> 
     <li id="li_8FF80DAFD67A4607B1E2596E4AA698A5">In the Dashboard Manager, locate the dashboard, then enable <span class="uicontrol"> Shared </span>. </li> 
     <li id="li_B55E4F392B834B2D895637B382CC0E3A">Click <span class="uicontrol"> Push To Users </span>. </li> 
     <li id="li_6B869EC4BB9543E8AAEBD21A11DA2AEC">On the <span class="wintitle"> Push Dashboard </span> page, select the target users or click <span class="uicontrol"> Check All </span>. </li> 
     <li id="li_9113105E32A049B48202B9F517F7A4C5">Click <span class="uicontrol"> Save </span>. </li> 
    </ol> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Q: How do I set a dashboard as the default landing page?</b> </p> </td> 
   <td colname="col2"> A: 
    <ol id="ol_5D7C6F9FED5D43A199ACF19F27D32127"> 
     <li id="li_83ACCBB55A664785874D14A300965676">Log in as the user who created the dashboard. <p>Note:  This user must have administrative privileges. </p> </li> 
     <li id="li_D2D31D458D174247BFDC69D68445B3E3">Navigate to 
      <ignoretag> 
       <span class="uicontrol"> Favorites </span>  &gt; 
       <span class="uicontrol"> Dashboards </span>  &gt; 
       <span class="uicontrol"> Manage Dashboards </span> 
      </ignoretag>. </li> 
     <li id="li_FCD0F5F9838C4591BA3EDDC6C4BF6B04">Click the icon next to the dashboard that you wish to designate as everyone's default landing page. </li> 
     <li id="li_533512632E70413AA4C5D0686014166D">Check the box that reads <span class="uicontrol"> Set as landing page for all users </span>. </li> 
     <li id="li_286FADAD5EE74AD198AAE3328366BEC2">Click <span class="uicontrol"> OK </span>. </li> 
    </ol> </td> 
  </tr> 
 </tbody> 
</table>


## Events {#section_9CAE843868D741AFA48CEF44E59AFE21}


<table id="table_EAFA76BEDCAD45B7B576E14DDEF53B35"> 
 <tbody> 
  <tr> 
   <td colname="col1"> <p><b>Q: How does Event Serialization work?</b> </p> </td> 
   <td colname="col2"> <p>A: Event serialization is the process of implementing measures to prevent duplicate events from entering Analytics reporting. This can commonly occur when a user refreshes the page multiple times, navigates to a certain page multiple times, or saves the web page to their computer (for example, if a customer saves a purchase confirmation page to their computer, every time they view it orders and revenue would be counted again if event serialization was not in place). <a href="https://marketing.adobe.com/resources/help/en_US/sc/implement/event_serialization.html" format="https" scope="external"> More... </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Q: How are eVars populated and allocated? </b> </p> </td> 
   <td colname="col2"> <p>A: Allocation determines how Analytics assigns credit for a success event if a variable receives multiple values before the event. <a href="https://marketing.adobe.com/resources/help/kb/en_US/analytics/kb/compare-first-last-linear-allocations.html" format="https" scope="external"> More... </a> Supported values include: </p> 
    <ul id="ul_14B2BE604DAD4B2A8056B7C3F34B4A98"> 
     <li id="li_87E62BCDC5EA4F00BFDB1CD3424F6224">Most Recent: The last eVar value always receives credit for success events until that eVar expires. </li> 
     <li id="li_F2C7A81583D64C69BCE51F17EDEECC99">Original Value: The first eVar always receives credit for success events until that eVar expires. </li> 
     <li id="li_C567B421D5864643948E86629B859509">Linear: Allocates success events equally across all eVar values. Since Linear allocation accurately distributes values only within a visit, use Linear allocation with an eVar expiration of Visit. </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>


## Segmentation {#section_90C6137813784A80A266680715613DF2}


<table id="table_3FEFBBED2977463EBAACD3D3EDC9F099"> 
 <tbody> 
  <tr> 
   <td colname="col1"> <p><b>Q: How do I determine which segmentation container I should use?</b> </p> </td> 
   <td colname="col2"> <p>A: Data captured at each level of the Visitor &amp;gt; Visit &amp;gt; Hit container hierarchy affects how you build your segments. </p> <p>If you take the same segment applied to the same report using the same data set, you will get different values based on the container from which you generate the report. Factors such as container reporting level and persistence of values across hits can mean big changes in your reporting accuracy. <a href="https://marketing.adobe.com/resources/help/en_US/analytics/segment/seg_container_reports.html " format="https" scope="external"> More... </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Q: Why are my segments not compatible in Data Warehouse?</b> </p> </td> 
   <td colname="col2"> <p>A: You will get an error when you try to save a segment in the Data Warehouse folder where the <a href="https://marketing.adobe.com/resources/help/en_US/analytics/segment/seg_compatibility.html " format="https" scope="external"> segment contains elements not compatible with Data Warehouse </a>. <a href="https://helpx.adobe.com/analytics/kb/incompatible-elements-in-segments.html " format="https" scope="external"> More... </a> </p> <p>To resolve this error, do one of two things: </p> 
    <ul id="ul_128CAA12209342B99C85EF82DB29F896"> 
     <li id="li_8FEAFA4F3882466DAFF6F39657B368B6">Save the segment in a different folder. </li> 
     <li id="li_1260FD102E5C4D84AE2F0A5556F1BAC8">Remove or change the incompatible portions of the segment. </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>


## Processing Rules {#section_D2A384C080D04F09905FBC59F4923A39}


<table id="table_1EC9025164414D729EC70989FA23D815"> 
 <tbody> 
  <tr> 
   <td colname="col1"> <p><b>Q: Do I require a certification to create/modify Processing Rules?</b> </p> </td> 
   <td colname="col2"> <p>A: Because Processing Rules permanently affect Analytics data, processing rule users must be well trained to prevent accidental deletion or alteration of data. Therefore, all users (including administrators) must pass the Adobe Processing Rule Certification test to acquire access to create and modify processing rules. <a href="https://marketing.adobe.com/resources/help/en_US/reference/processing_rules.html#" format="dita" scope="local"> More... </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Q: How do I get authorized access to processing rules after passing the certification test?</b> </p> </td> 
   <td colname="col2"> <p>A: After you have passed the certification exam, follow these instructions: </p> 
    <ol id="ol_B44C3EA78F40465780AE5DF366D94FB7"> 
     <li id="li_E280A28132D34E4BBF976B1357F2B94E">Share your username and certificate with the supported user in your company. </li> 
     <li id="li_E49F14DD8A0E45C0A8D4090A4B9C92ED">Have your supported user contact Adobe ClientCare with the request. </li> 
     <li id="li_7B93E65CC48343919ED10D418EF4AD29">ClientCare will then enable your access to processing rules. <a href="https://marketing.adobe.com/resources/help/en_US/home/?f=http%3a%2f%2fhelpx.adobe.com%2fanalytics%2fkb%2fprocessing-rules-authorization.html#" format="dita" scope="local"> More... </a> </li> 
    </ol> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Q: How do I use Context Data Variables in Processing Rules?</b> </p> </td> 
   <td colname="col2"> <p>A: The Context Variables list contains all variables that were sent to the report suite in the previous 30 days. If you know the context data variable name but have not sent it into the current report suite, you can add a value by typing the variable name and clicking Add variable name context data. <a href="https://marketing.adobe.com/resources/help/en_US/reference/processing_rules_copy_context_data.html#" format="dita" scope="local"> More... </a> </p> </td> 
  </tr> 
 </tbody> 
</table>


## Data Warehouse {#section_67D6B9CC8BE140228441D210ED160314}


<table id="table_7F4D54EB6A46470DB7156B052905E3C6"> 
 <tbody> 
  <tr> 
   <td colname="col1"> <p><b>Q: How do I enable Data Warehouse for Users and Report Suites?</b> </p> </td> 
   <td colname="col2"> <p>A: Enable Data Warehouse access by creating a user group and adding the report suites in the group. <a href="https://marketing.adobe.com/resources/help/en_US/reference/t_dw_group.html" format="https" scope="external"> More... </a> </p> </td> 
  </tr> 
 </tbody> 
</table>



## Classifications {#section_1A01444C17CD4145ADC731DD1FB0F058}


<table id="table_5B35870D95BD46C1AF5B5190A438B5E1"> 
 <tbody> 
  <tr> 
   <td colname="col1"> <p><b>Q: How can I tell if a classifications file has been completely processed/propagated?</b> </p> </td> 
   <td colname="col2"> <p>A: If processing is not complete, either one of the following messages appear: </p> 
    <ul id="ul_56123B504B44453EB7AC192580A40E44"> 
     <li id="li_80B0036DE21C4C2BB7C316913CAD68A5">The selected report has a classifications import that is processing. </li> 
     <li id="li_E6E8695C06CD4863BCBDE75ED9377289">The selected report has classifications data that hasn't propagated to all servers yet. <a href="https://helpx.adobe.com/analytics/kb/saint-processing-time.html" format="https" scope="external"> More... </a> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Q: Why is classification data not visible in reporting even though it has been sent to FTP? </b> </p> </td> 
   <td colname="col2"> <p>A: Classification Data takes time to upload to the servers and reflect into Reports &amp; Analytics. The time this takes depends on the number of files uploaded and the size of the files. Data file processing takes about 72 hours. <a href="https://marketing.adobe.com/resources/help/en_US/reference/c_uploading_saint_data_files_via_ftp.html" format="https" scope="external"> More... </a> </p> </td> 
  </tr> 
 </tbody> 
</table>


## Data Feeds {#section_F1B81518893F4A0C85B5CD2BE44A9998}


<table id="table_48BCAFF5449742D2A52D9DBFDBBF4CF5"> 
 <tbody> 
  <tr> 
   <td colname="col1"> <p><b>Q: Why are data feeds to FTP failing?</b> </p> </td> 
   <td colname="col2"> <p>A: In the event of an FTP transfer failure (login denied, lost connection, out of quota, etc), Adobe attempts to automatically connect and send the data up to three separate times. If the failures persist, the feed is marked as failed and an email notification is sent. <a href="https://marketing.adobe.com/resources/help/en_US/sc/clickstream/datafeeds_troubleshooting.html" format="https" scope="external"> More... </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Q: Why are data feeds arriving late?</b> </p> </td> 
   <td colname="col2"> <p>A: Processing time for any FTP file, whether it is Classifications or Data Sources, is based on the number of files already in the processing queue and the size of your file. <a href="https://marketing.adobe.com/resources/help/en_US/whitepapers/ftp/ftp_processing.html" format="https" scope="external"> More... </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Q: What are the files and formats associated with data feeds?</b> </p> </td> 
   <td colname="col2"> <p>A: These are the files found in a data feed delivery: Manifest File, Lookup File, Hit Data File, Delivery Contents. <a href="https://marketing.adobe.com/resources/help/en_US/sc/clickstream/datafeeds_contents.html" format="https" scope="external"> More... </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Q: How do I interpret pre and post columns? </b> </p> </td> 
   <td colname="col2"> <p>A: The pre column contains the data as it was sent to data collection. The post column contains the value after processing. <a href="https://marketing.adobe.com/resources/help/en_US/sc/clickstream/datafeeds_column_types.html" format="https" scope="external"> More... </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Q: Where can I find column reference for data feeds? </b> </p> </td> 
   <td colname="col2"> <p>A: The Table data describing the columns in the data feed contains Columns, Descriptions, and Data Types, as well as Example Lookup for Solution Variables. <a href="https://marketing.adobe.com/resources/help/en_US/sc/clickstream/datafeeds_reference.html" format="https" scope="external"> More... </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Q: What is the FTP size limit? </b> </p> </td> 
   <td colname="col2"> <p>A: Data Feed FTP accounts allow 2 GB or 63 files (by default). All other standard FTP accounts are 50MB by default. In cases where clients are using the FTP account for its proper intended use, some users with high traffic amounts can quickly fill up these accounts. When an FTP account is full, no additional files can be pushed to them. <a href="https://marketing.adobe.com/resources/help/en_US/whitepapers/ftp/ftp_datafeeds.html" format="https" scope="external"> More... </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Q: Is sFTP supported for daily data feed delivery? </b> </p> </td> 
   <td colname="col2"> <p>A: Yes, Data Feeds can be configured for sFTP delivery. </p> <p> <a href="https://marketing.adobe.com/resources/help/en_US/reference/r_feed-destination.html" format="html" scope="external"> More... </a> </p> </td> 
  </tr> 
 </tbody> 
</table>

