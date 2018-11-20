---
description: Descriptions of variables and how each is used in reporting.
seo-description: Descriptions of variables and how each is used in reporting.
seo-title: Variables - how they are used in reporting
solution: Analytics
subtopic: Variables
title: Variables - how they are used in reporting
topic: Developer and implementation,Reports
uuid: bd6b697a-c11a-434c-9d75-d46ecfec49ef
index: y
internal: n
snippet: y
---

# Variables - how they are used in reporting

Descriptions of variables and how each is used in reporting.

## Variables {#section_193C396A80F944E4A5D44ABA75046383}

Analytics variables are usually populated in the HTML code, on each page or template of the site. Additionally, plug-ins and global code may be added to the [!DNL .js] file that also populates the variables, or overrides the values set in the HTML pages. The variables that are populated include the following.

**NOTE:** &#42; Denotes a conversion variable. These variables require that the conversion module be enabled. 

<table id="table_F84FE26A2810470A98D7E477D3F6A1EA"> 
 <tbody> 
  <tr> 
   <td> <p> <b>Implementation Variable</b> </p> </td> 
   <td> <p> <b>Description</b> </p> </td> 
   <td colname="col3"> <p> <b>Reports Populated</b> </p> </td> 
  </tr> 
  <tr> 
   <td> <p> <a href="https://marketing.adobe.com/resources/help/en_US/sc/implement/pageName.html" format="http" scope="external"> pageName</a> </p> </td> 
   <td> <p>The name of the page. Uniquely identifies the page and URL in plain English. For example: </p> <p> <span class="codeph"> "homepage"</span> </p> </td> 
   <td colname="col3"> <p> <a href="reports-pages.md#concept_0219136EA25745B58434D0C7E751D7D5" format="dita" scope="local"> Pages Report </a> </p> <p> <a href="reports_paths.md#topic_39F11BCBEDC3495EA1300149FC6D4F14" format="dita" scope="local"> Paths Reports </a> </p> </td> 
  </tr> 
  <tr> 
   <td> <p> <a href="https://marketing.adobe.com/resources/help/en_US/sc/implement/channel.html" format="http" scope="external"> channel</a> </p> </td> 
   <td> <p>The section of the site, or channel. For example: </p> <p> <span class="codeph"> "electronics"</span>, <span class="codeph"> "news"</span> </p> </td> 
   <td colname="col3"> <p> <a href="reports_site_sections.md#concept_39E550D7A9E34C9580E81F5F9E12BDDD" format="dita" scope="local"> Site Sections Report </a> </p> </td> 
  </tr> 
  <tr> 
   <td> <p> <a href="https://marketing.adobe.com/resources/help/en_US/sc/implement/context_data_variables.html" format="http" scope="external"> contextData</a> </p> </td> 
   <td> Available with version 15 and <a href="../../admin/admin/c-processing-rules/processing-rules.md#concept_1D0EA3DBDEF4412BB7A7D769EA3717C2" format="dita" scope="local"> processing rules</a>. <span class="varname"> contextData</span> variables require no knowledge of the various types of variables Analytics offers (props, eVars, etc). <p> An analyst can request a variable name be implemented, and apply processing rules to assign that context data to a variable. </p> </td> 
   <td colname="col3"> <p>None. Context Data must be mapped to variables for reporting. </p> </td> 
  </tr> 
  <tr> 
   <td> <p> <a href="https://marketing.adobe.com/resources/help/en_US/sc/implement/server.html" format="http" scope="external"> server</a> </p> </td> 
   <td> <p>The server name or vanity domain to be tracked. </p> </td> 
   <td colname="col3"> <p> <a href="reports_servers.md#concept_A5CABE5BB44E4919BE27E7C4EAD8F6CE" format="dita" scope="local"> Servers Report </a> </p> </td> 
  </tr> 
  <tr> 
   <td> <p> <a href="https://marketing.adobe.com/resources/help/en_US/sc/implement/propN.html" format="http" scope="external"> propN</a> (prop1 - prop75) </p> </td> 
   <td> <p>Custom values. The specific meaning of each variable is defined uniquely for each web site. </p> </td> 
   <td colname="col3"> <p>Multiple </p> </td> 
  </tr> 
  <tr> 
   <td> <p> <a href="https://marketing.adobe.com/resources/help/en_US/sc/implement/hierN.html" format="http" scope="external"> hierN</a> (hier1 - hier5) </p> </td> 
   <td> <p>Hierarchy variables, used to record visits and visitors for a hierarchically structured site. </p> </td> 
   <td colname="col3"> <p> <a href="reports_hierarchy.md#concept_845DFC7699C54E4A81C89D7F5396136B" format="dita" scope="local"> Hierarchy Report </a> </p> </td> 
  </tr> 
  <tr> 
   <td> <p> <a href="https://marketing.adobe.com/resources/help/en_US/sc/implement/campaign.html" format="http" scope="external"> campaign</a>* </p> </td> 
   <td> <p>Tracks advertising or email click-throughs to the site. Campaigns are also correlated to many values throughout the system, such as to conversion and custom events, referring domains, and search engines. </p> </td> 
   <td colname="col3"> <p> <a href="reports_tracking_codes.md#concept_CBCAE87060BC4BE1A335DDCA6F4396FB" format="dita" scope="local"> Tracking Codes Report </a> </p> </td> 
  </tr> 
  <tr> 
   <td> <p> <a href="https://marketing.adobe.com/resources/help/en_US/sc/implement/eVarN.html" format="http" scope="external"> eVarN</a> (eVar1 - eVar75*) </p> </td> 
   <td> <p>Custom variables that are tracked and correlated to any events. The specific meaning of each variable is defined uniquely for each web site. <span class="varname"> s.eVar</span> values are stored and correlated to events that happen afterward. </p> </td> 
   <td colname="col3"> <p>Multiple </p> </td> 
  </tr> 
  <tr> 
   <td> <p> <a href="https://marketing.adobe.com/resources/help/en_US/sc/implement/products.html" format="http" scope="external"> products</a>* </p> </td> 
   <td> <p>List of products, used in conjunction with the <span class="varname"> s.events</span> variable </p> </td> 
   <td colname="col3"> <p>All Product reports </p> </td> 
  </tr> 
  <tr> 
   <td> <p> <a href="https://marketing.adobe.com/resources/help/en_US/sc/implement/events.html" format="http" scope="external"> events</a>* </p> </td> 
   <td> <p>The list of events that occurred on the current page. Examples include: <span class="varname"> scOpen</span>, <span class="varname"> scAdd</span>, <span class="varname"> scCheckout</span>, <span class="varname"> prodView</span>, purchase, or any custom event from event1 to event20. </p> </td> 
   <td colname="col3"> <p>All Event reports </p> </td> 
  </tr> 
  <tr> 
   <td> <p> <a href="https://marketing.adobe.com/resources/help/en_US/sc/implement/purchaseID.html" format="http" scope="external"> purchaseID</a>* </p> </td> 
   <td> <p>Up to 20 character code to uniquely identify the purchase, in conjunction with the purchase event </p> </td> 
   <td colname="col3"> <p> <a href="reports_revenue.md#concept_BDB40C65DF2A4F169ACF92649439224F" format="dita" scope="local"> Revenue </a> </p> </td> 
  </tr> 
  <tr> 
   <td> <p> <a href="https://marketing.adobe.com/resources/help/en_US/sc/implement/state.html" format="http" scope="external"> state</a>* </p> </td> 
   <td> <p>State name or ID, to be used on the order confirmation (Thank You) page, in conjunction with the purchase event </p> </td> 
   <td colname="col3"> <p> <a href="reports_state.md#concept_5D646CEA14254F3AA253F1E79D4A6471" format="dita" scope="local"> U.S. State </a> </p> </td> 
  </tr> 
  <tr> 
   <td> <p> <a href="https://marketing.adobe.com/resources/help/en_US/sc/implement/zip.html" format="http" scope="external"> zip</a>* </p> </td> 
   <td> <p>Zip code, to be used on the order confirmation (Thank You) page, in conjunction with the purchase or other event </p> </td> 
   <td colname="col3"> <p> <a href="reports_zip.md#concept_726A7EF8C50B49EB9185008C5FF42031" format="dita" scope="local"> Visitor Zip and Postal Codes Report </a> </p> </td> 
  </tr> 
  <tr> 
   <td> <p> <a href="https://marketing.adobe.com/resources/help/en_US/sc/implement/linkName.html" format="http" scope="external"> linkName</a> </p> </td> 
   <td> <p>Optionally used to identify the name of a link when sending in custom, download, or exit link data. </p> </td> 
   <td colname="col3"> <p> <a href="reports_file_downloads.md#concept_E3D0FEC81E1F4987B39CC467F19FFCFF" format="dita" scope="local"> File Downloads Report </a> </p> <p> <a href="reports_custom_links.md#concept_C2640EE109CD456E8FB9DE7BED2B0499" format="dita" scope="local"> Custom Links Report </a> </p> <p> <a href="reports_exit_links.md#concept_7F6A0867A4F1483E8AF20554DF348454" format="dita" scope="local"> Exit Links Report </a> </p> </td> 
  </tr> 
  <tr> 
   <td> <p> <a href="https://marketing.adobe.com/resources/help/en_US/sc/implement/linkType.html" format="http" scope="external"> linkType</a> </p> </td> 
   <td> <p>Used to identify the type of link: Custom, Download, or Exit </p> </td> 
   <td colname="col3"> <p> <a href="reports_file_downloads.md#concept_E3D0FEC81E1F4987B39CC467F19FFCFF" format="dita" scope="local"> File Downloads Report </a> </p> <p> <a href="reports_custom_links.md#concept_C2640EE109CD456E8FB9DE7BED2B0499" format="dita" scope="local"> Custom Links Report </a> </p> <p> <a href="reports_exit_links.md#concept_7F6A0867A4F1483E8AF20554DF348454" format="dita" scope="local"> Exit Links Report </a> </p> </td> 
  </tr> 
  <tr> 
   <td> <a href="https://marketing.adobe.com/resources/help/en_US/sc/implement/list_props.html" format="http" scope="external"> List Props</a> </td> 
   <td> <p>List variables are a delimited list of values that are passed into a variable, and then reported as individual line items for reporting. </p> </td> 
   <td colname="col3"> <p>Multiple </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <a href="https://marketing.adobe.com/resources/help/en_US/sc/implement/listN.html" format="http" scope="external"> List Variable</a> (list var) </p> </td> 
   <td colname="col2"> <p>Similar to how List Props function, List Vars allow multiple values within the same image request. </p> <p>Version 15 only. </p> </td> 
   <td colname="col3"> <p>Multiple </p> </td> 
  </tr> 
  <tr> 
   <td> <p> <a href="https://marketing.adobe.com/resources/help/en_US/sc/implement/s_objectID.html" format="http" scope="external"> s_objectID</a> </p> </td> 
   <td> <p>A ClickMap variable used to uniquely identify links on a page </p> </td> 
   <td colname="col3"> <p>ClickMap </p> </td> 
  </tr> 
  <tr> 
   <td> <p> <a href="https://marketing.adobe.com/resources/help/en_US/sc/implement/pageType.html" format="http" scope="external"> pageType</a> </p> </td> 
   <td> <p>Used on <i>404-Page Not Found</i> error pages </p> </td> 
   <td colname="col3"> <p> <a href="reports_pages_not_found.md#concept_46A8DB85A4DE428A944C5711B2AE625B" format="dita" scope="local"> Pages Not Found Report </a> </p> </td> 
  </tr> 
  <tr> 
   <td> <p> <a href="https://marketing.adobe.com/resources/help/en_US/sc/implement/pageURL.html" format="http" scope="external"> pageURL</a> </p> </td> 
   <td> <p>Optionally used to override the URL of the page as recorded in Analyitcs </p> </td> 
   <td colname="col3"> <p> <a href="reports-pages.md#concept_0219136EA25745B58434D0C7E751D7D5" format="dita" scope="local"> Pages Report </a> </p> <p> <a href="reports_paths.md#topic_39F11BCBEDC3495EA1300149FC6D4F14" format="dita" scope="local"> Paths Reports </a> </p> </td> 
  </tr> 
  <tr> 
   <td> <p> <a href="https://marketing.adobe.com/resources/help/en_US/sc/implement/referrer.html" format="http" scope="external"> referrer</a> </p> </td> 
   <td> <p>Optionally used to override a page's referrer as recorded in Analyitcs </p> </td> 
   <td colname="col3"> <p> <a href="reports_finding_methods.md#concept_5B8F9F289149440E9553C91EF1E69F0F" format="dita" scope="local"> Finding Methods Report </a> </p> </td> 
  </tr> 
  <tr> 
   <td> <p> <a href="https://marketing.adobe.com/resources/help/en_US/sc/implement/transactionID.html" format="http" scope="external"> transactionID</a> </p> </td> 
   <td> <p>Integration Data Sources utilize a transaction ID to tie offline data to an online transaction (like a lead or purchase generated online) </p> </td> 
   <td colname="col3"> <p>N/A </p> </td> 
  </tr> 
  <tr> 
   <td> <p> <a href="https://marketing.adobe.com/resources/help/en_US/sc/implement/visitorID.html" format="http" scope="external"> visitorID</a> </p> </td> 
   <td> <p>Visitors may be identified by the visitorID variable, or by IP address/User Agent </p> </td> 
   <td colname="col3"> <p>N/A </p> </td> 
  </tr> 
 </tbody> 
</table>

## Configuration Variables {#section_C6A32064666248AFBCB5FFA39FE66179}

Configuration variables, which control data collection, are contained in the [!DNL .js] file, but they are not considered data collection elements. Configuration variables are not included in marketing reports, but they may affect the data, or the appearance of the reports. Configuration variables include the following. 

<table id="table_C034CFC4F2314B5E864A5E6B9B0EC587"> 
 <tbody> 
  <tr> 
   <td> <p> <b>Implementation Variable</b> </p> </td> 
   <td> <p> <b>Description</b> </p> </td> 
   <td colname="col3"> <p> <b>Reports Populated</b> </p> </td> 
  </tr> 
  <tr> 
   <td> <p> <a href="https://marketing.adobe.com/resources/help/en_US/sc/implement/s_account.html" format="http" scope="external"> s_account</a> </p> </td> 
   <td> <p>Report suite IDs. The account(s) that the page view is reported in. </p> </td> 
   <td colname="col3"> <p>N/A </p> </td> 
  </tr> 
  <tr> 
   <td> <p> <a href="https://marketing.adobe.com/resources/help/en_US/sc/implement/charset.html" format="http" scope="external"> charSet</a> </p> </td> 
   <td> <p>The character set used on the page. The default is assumed to be ISO-8859-1. A list of available character sets is available from Adobe. </p> </td> 
   <td colname="col3"> <p>N/A </p> </td> 
  </tr> 
  <tr> 
   <td> <p> <a href="https://marketing.adobe.com/resources/help/en_US/sc/implement/currencycode.html" format="http" scope="external"> currencyCode</a> </p> </td> 
   <td> <p>The currency code used in the <span class="varname"> s.products</span> and <span class="varname"> s.events</span> variables. The default is assumed to be USD (U.S. dollars). A list of supported currency codes is available from Adobe. </p> </td> 
   <td colname="col3"> <p> <a href="reports_revenue.md#concept_BDB40C65DF2A4F169ACF92649439224F" format="dita" scope="local"> Revenue </a> </p> <p>All conversion reports showing revenue or monetary values </p> </td> 
  </tr> 
  <tr> 
   <td> <p> <a href="https://marketing.adobe.com/resources/help/en_US/sc/implement/cookiedomainperiods.html" format="http" scope="external"> cookieDomainPeriods</a> </p> </td> 
   <td> <p>The number of sections in a domain on which the visitor ID cookie is set. </p> </td> 
   <td colname="col3"> <p>Affects multiple reports as it controls how the visitor ID is stored and handled. </p> </td> 
  </tr> 
  <tr> 
   <td> <p> <a href="https://marketing.adobe.com/resources/help/en_US/sc/implement/fpCookieDomainPeriods.html" format="http" scope="external"> fpCookieDomainPeriods</a> </p> </td> 
   <td> <p>The number of sections in a domain on which cookies are set by the JavaScript file. This overrides the value of <span class="varname"> cookieDomainPeriods</span> for JavaScript cookies. </p> </td> 
   <td colname="col3"> <p>N/A </p> </td> 
  </tr> 
  <tr> 
   <td> <p> <a href="https://marketing.adobe.com/resources/help/en_US/sc/implement/cookielifetime.html" format="http" scope="external"> cookieLifetime</a> </p> </td> 
   <td> <p>Establishes the lifetime of the visitor cookie (s.vixxxx). Configuration of this variable is completed by Adobe and should not be modified by clients. </p> </td> 
   <td colname="col3"> <p>See <a href="https://marketing.adobe.com/resources/help/en_US/whitepapers/first_party_cookies/" format="http" scope="external"> Implementing First-Party Cookies</a> </p> </td> 
  </tr> 
  <tr> 
   <td> <p> <a href="https://marketing.adobe.com/resources/help/en_US/sc/implement/doPlugins.html" format="http" scope="external"> doPlugins</a> </p> </td> 
   <td> <p>The function that should be called before data is sent to Analytics. </p> </td> 
   <td colname="col3"> <p>The doPlugins variable is a reference to the <span class="filepath"> s_doPlugins</span> function, and allows the <span class="filepath"> s_doPlugins</span> function to be called at the appropriate location within the JavaScript file. </p> </td> 
  </tr> 
  <tr> 
   <td> <p> <a href="https://marketing.adobe.com/resources/help/en_US/sc/implement/dynamicAccountSelection.html" format="http" scope="external"> dynamicAccountSelection</a> </p> </td> 
   <td> <p>Set to <span class="codeph"> "true"</span> if <span class="codeph"> "s.dynamicAccountList"</span> contains a list of domain/report suite ID pairs to be used to dynamically select the report suite ID based on domain, host, or directory name. </p> </td> 
   <td colname="col3"> <p>N/A </p> </td> 
  </tr> 
  <tr> 
   <td> <p> <a href="https://marketing.adobe.com/resources/help/en_US/sc/implement/dynamicAccountList.html" format="http" scope="external"> dynamicAccountList</a> </p> </td> 
   <td> <p>A list of domains and which report suite ID should be used for each (such as <span class="codeph"> "abc.com=reportabc"</span>). </p> </td> 
   <td colname="col3"> <p>N/A </p> </td> 
  </tr> 
  <tr> 
   <td> <p> <a href="https://marketing.adobe.com/resources/help/en_US/sc/implement/dynamicAccountMatch.html" format="html" scope="external"> dynamicAccountMatch</a> </p> </td> 
   <td> <p>The section of the URL that all filters in <span class="varname"> dynamicAccountList</span> are applied to </p> </td> 
   <td colname="col3"> <p>N/A </p> </td> 
  </tr> 
  <tr> 
   <td> <p> <a href="https://marketing.adobe.com/resources/help/en_US/sc/implement/trackDownloadLinks.html" format="http" scope="external"> trackDownloadLinks</a> </p> </td> 
   <td> <p>Set to <span class="codeph"> "true"</span> to track clicks on links that have extension names listed in <span class="varname"> s.linkDownloadFileTypes</span>. </p> </td> 
   <td colname="col3"> <p>N/A </p> </td> 
  </tr> 
  <tr> 
   <td> <p> <a href="https://marketing.adobe.com/resources/help/en_US/sc/implement/trackExternalLinks.html" format="http" scope="external"> trackExternalLinks</a> </p> </td> 
   <td> <p>Set to <span class="codeph"> "true"</span> to track clicks on links that are external. External links are domains not listed in <span class="varname"> s.linkInternalFilters</span>. </p> </td> 
   <td colname="col3"> <p>N/A </p> </td> 
  </tr> 
  <tr> 
   <td> <p> <a href="https://marketing.adobe.com/resources/help/en_US/sc/implement/trackInlineStats.html" format="http" scope="external"> trackInlineStats</a> </p> </td> 
   <td> <p>Set to <span class="codeph"> "true"</span> to capture data for ClickMap reporting. </p> </td> 
   <td colname="col3"> <p> ClickMap </p> </td> 
  </tr> 
  <tr> 
   <td> <p> <a href="https://marketing.adobe.com/resources/help/en_US/sc/implement/linkDownloadFileTypes.html" format="http" scope="external"> linkDownloadFileTypes</a> </p> </td> 
   <td> <p>The list of download file types. </p> </td> 
   <td colname="col3"> <p> <a href="reports_file_downloads.md#concept_E3D0FEC81E1F4987B39CC467F19FFCFF" format="dita" scope="local"> File Downloads Report </a> </p> </td> 
  </tr> 
  <tr> 
   <td> <p> <a href="https://marketing.adobe.com/resources/help/en_US/sc/implement/linkInternalFilters.html" format="http" scope="external"> linkInternalFilters</a> </p> </td> 
   <td> <p>Determines which links on your site are exit links, which is any link that takes a visitor away from your site. It is a comma-separated list of filters that represent the links that are part of the site. </p> </td> 
   <td colname="col3"> <p> <a href="reports_exit_links.md#concept_7F6A0867A4F1483E8AF20554DF348454" format="dita" scope="local"> Exit Links Report </a> </p> </td> 
  </tr> 
  <tr> 
   <td> <p> <a href="https://marketing.adobe.com/resources/help/en_US/sc/implement/linkExternalFilters.html" format="http" scope="external"> linkExternalFilters</a> </p> </td> 
   <td> <p>The list of all domains which should be considered external. This is used to <i>limit</i> the number of external links that will be used, not to specify specific links as external. </p> </td> 
   <td colname="col3"> <p> <a href="reports_exit_links.md#concept_7F6A0867A4F1483E8AF20554DF348454" format="dita" scope="local"> Exit Links Report </a> </p> </td> 
  </tr> 
  <tr> 
   <td> <p> <a href="https://marketing.adobe.com/resources/help/en_US/sc/implement/linkLeaveQueryString.html" format="http" scope="external"> linkLeaveQueryString</a> </p> </td> 
   <td> <p>Whether or not the query string of exit links and download links should be included for tracking purposes. </p> </td> 
   <td colname="col3"> <p> <a href="reports_file_downloads.md#concept_E3D0FEC81E1F4987B39CC467F19FFCFF" format="dita" scope="local"> File Downloads Report </a> </p> <p> <a href="reports_exit_links.md#concept_7F6A0867A4F1483E8AF20554DF348454" format="dita" scope="local"> Exit Links Report </a> </p> </td> 
  </tr> 
  <tr> 
   <td> <p> <a href="https://marketing.adobe.com/resources/help/en_US/sc/implement/linkTrackVars.html" format="http" scope="external"> linkTrackVars</a> </p> </td> 
   <td> <p>The variables that should be sent on custom links, download links, and external links. By default, this variable is set to "None" so that variables set on the page are not recounted by link clicks. </p> </td> 
   <td colname="col3"> <p>Any </p> </td> 
  </tr> 
  <tr> 
   <td> <p> <a href="https://marketing.adobe.com/resources/help/en_US/sc/implement/linkTrackEvents.html" format="http" scope="external"> linkTrackEvents</a> </p> </td> 
   <td> <p>The events to be sent on custom links, download links, and external links. By default, this variable is set to "None" that variables set on the page are not recounted by link clicks. </p> </td> 
   <td colname="col3"> <p>Conversion </p> </td> 
  </tr> 
  <tr> 
   <td> <p> <a href="https://marketing.adobe.com/resources/help/en_US/sc/implement/s_usePlugins.html" format="http" scope="external"> usePlugins</a> </p> </td> 
   <td> <p>If set to <span class="codeph"> "true"</span>, <span class="varname"> s_doPlugins()</span> will be called by the <span class="filepath"> .JS</span> code prior to creating the image request. </p> </td> 
   <td colname="col3"> <p>N/A </p> </td> 
  </tr> 
 </tbody> 
</table>

## Automatic Variables {#section_2264E57132144263BFEEC40F63AB85F3}

Automatic variables are obtained by the [!DNL .JS] code either automatically, or they are populated in the [!DNL .JS] file as a result of the control variables explained above. The names of these variables are defined only within the query string of the image request. There is no equivalent HTML-based variable. The automatic variables include the following. 

<table id="table_306062E7991C41039E0E9C0A736FD961"> 
 <tbody> 
  <tr> 
   <td> <b>Automatic Variable</b> </td> 
   <td> <b>Description</b> </td> 
  </tr> 
  <tr> 
   <td> <p>r (Referring URL) </p> </td> 
   <td> <p>The referring URL as defined by the browser. This value includes all query string parameters for the referring URL, including search strings and other information. </p> </td> 
  </tr> 
  <tr> 
   <td> <p>g (Current URL) </p> </td> 
   <td> <p>The current page's URL. This value may include all query string parameters, depending upon the account settings and configuration. </p> </td> 
  </tr> 
  <tr> 
   <td> <p>ClickMap data (various) </p> </td> 
   <td> <p>Various information about the page ID, link clicked, including destination URL, link number, etc. </p> </td> 
  </tr> 
  <tr> 
   <td> <p>t </p> </td> 
   <td> <p>The time and date that the event request occurred, in local time. </p> </td> 
  </tr> 
  <tr> 
   <td> <p>v </p> </td> 
   <td> <p>Whether Java is enabled (Y/N). </p> </td> 
  </tr> 
  <tr> 
   <td> <p>j </p> </td> 
   <td> <p>The version of JavaScript supported by the browser. </p> </td> 
  </tr> 
  <tr> 
   <td> <p>bw, bh </p> </td> 
   <td> <p>The width and height of the browser window. </p> </td> 
  </tr> 
  <tr> 
   <td> <p>s </p> </td> 
   <td> <p>The width and height of the screen (the physical monitor). </p> </td> 
  </tr> 
  <tr> 
   <td> <p>c </p> </td> 
   <td> <p>Monitor depth (number of available colors). </p> </td> 
  </tr> 
  <tr> 
   <td> <p>ct </p> </td> 
   <td> <p>Connection type, including LAN, modem, etc. </p> </td> 
  </tr> 
  <tr> 
   <td> <p>p </p> </td> 
   <td> <p>Netscape plug-ins (if running Netscape, the list of plug-ins installed in the browser) </p> </td> 
  </tr> 
  <tr> 
   <td> <p>k </p> </td> 
   <td> <p>Cookies enabled (whether or not cookies are enabled in the browser based on a test cookie) </p> </td> 
  </tr> 
  <tr> 
   <td> <p>hp </p> </td> 
   <td> <p>Whether the current page is set as the browser's Home page </p> </td> 
  </tr> 
 </tbody> 
</table>

## Direct Variables {#section_73B40376C5D847DC82CB9863F26D086F}

Direct variables are those set directly by the browser in the HTTP header of the image request sent to Analytics. These variables are set in each request that is made for any content on the Internet and include some of the most basic user information. The variables are reported directly or indirectly in a number of marketing reports. Direct variables include the following. 

<table id="table_869DA2245CDA438CA73CFC80F7DF8B33"> 
 <tbody> 
  <tr> 
   <td> <p> <b>Direct Variable</b> </p> </td> 
   <td> <p> <b>Description</b> </p> </td> 
  </tr> 
  <tr> 
   <td> <p>IP address </p> </td> 
   <td> <p>The IP address is the Internet Protocol address of the user's browser or machine. That IP addresses may be pooled among multiple users, and that a single user may also use more than one IP address from page to page. </p> <p>The user's IP address is resolved to geographic location based on data provided by Digital Envoy through a partnership with Adobe. </p> </td> 
  </tr> 
  <tr> 
   <td> <p>domain </p> </td> 
   <td> <p>The domain from which the user is requesting data. In many cases, this is a company or an Internet Service Provider (ISP) such as AOL. </p> </td> 
  </tr> 
  <tr> 
   <td> <p>user agent string </p> </td> 
   <td> <p>The user agent string indicates the browser and version, and the Operating System used. In some cases, it may also contain major plug-in or customization features (i.e., .NET). The <span class="wintitle"> Browser</span>, <span class="wintitle"> Browser Version</span>, and <span class="wintitle"> Operating System</span> reports are based on the user agent string. </p> </td> 
  </tr> 
  <tr> 
   <td> <p>language </p> </td> 
   <td> <p>The preferred language setting of the browser. </p> </td> 
  </tr> 
  <tr> 
   <td> <p>cookies </p> </td> 
   <td> <p>The names and values of all cookies that have been set. </p> </td> 
  </tr> 
 </tbody> 
</table>

