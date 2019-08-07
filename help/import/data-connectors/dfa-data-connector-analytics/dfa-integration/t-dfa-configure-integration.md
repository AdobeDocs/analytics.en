---
description: Step through the DFA Data Connectors Integration.
seo-description: Step through the DFA Data Connectors Integration.
seo-title: Configure the DFA integration
title: Configure the DFA integration
uuid: 4c2ac58a-87c6-46f3-9033-9404beb18c39
index: y
internal: n
snippet: y
---

# Configure the DFA integration{#configure-the-dfa-integration}

Step through the DFA Data Connectors Integration.

The configuration pages provide an overview of the integration, along with helpful links for more information. There are both Adobe and DoubleClick fees associated with this integration. Contact your appropriate Sales Representatives for both organizations and make sure you understand the fee structure. 

1. Log in to the [!DNL Adobe Analytics].
1. Click **[!UICONTROL Admin]** > **[!UICONTROL Data Connectors]**.

   ![](assets/data_connectors.png)

1. Locate **[!UICONTROL DoubleClick DFA]**, then click **[!UICONTROL Add New]**.

   ![Step Result](assets/wizard-01.png)

   On each page of the Integration Wizard, provide the required information, then click **[!UICONTROL Next]**. The following table explains the information you need to complete the integration through the wizard.

<table id="table_8F6F7F304C36431DA5FD6E5D54F60FC0"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Wizard Page # </th> 
   <th colname="col2" class="entry"> Field </th> 
   <th colname="col3" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 1 </td> 
   <td colname="col2"> Integration Name </td> 
   <td colname="col3"> The integration name that Genesis displays in the report suite’s Active Integration List. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 1 </td> 
   <td colname="col2"> Integration Email Address </td> 
   <td colname="col3"> The email address that receives all notifications related to this integration. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 2 </td> 
   <td colname="col2"> User name </td> 
   <td colname="col3"> The DFA API username to use with this integration. To enable a user for API login, check the API attribute in the DFA interface. After you enable API login, a password field appears to provide a password for the user. This password is entered along with the username into the wizard to authenticate. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 2 </td> 
   <td colname="col2"> Password </td> 
   <td colname="col3"> The DFA API password. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 2 </td> 
   <td colname="col2"> Advertiser ID </td> 
   <td colname="col3"> <p>The DFA advertiser ID or the parent Floodlight Configuration ID. Data Connectors uses this ID to identify the DFA Advertiser to track (version 1.5 of the integration). This Advertiser ID is not used in version 2.0 of the integration - the parent Floodlight Configuration ID will be looked up and used. See the instructions on the screen </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 3 </td> 
   <td colname="col2"> DFA Ad Variable </td> 
   <td colname="col3"> The Analytics eVar that receives DFA campaign attribute, impressions, and clicks data. Typically, this is the Tracking Code eVar ( <span class="varname"> s.campaign </span>), but you can choose any available eVar. Data Connectors also adds the following DFA-related classifications to the selected eVar: <p><b>Campaigns</b>: A collection of ads served to multiple sites that carry common messaging. </p> <p><b>Site Name</b>: The site where the ad was served. </p> <p><b>Ad Name</b>: The Ad name, as defined in your DFA account. </p> <p><b>Site Placement Name</b>: The Web site and page where the Ad was served. </p> <p><b>Delivery Tool</b>: DoubleClick for Advertisers. </p> <p><b>Channel</b>: Banner Ad. </p> <p><b>Cost Structure</b>: CPM, CPC, or Fixed, based on the cost structure of the ad. </p> <p><b>Creative Name</b>: The name of the creative associated with an ad/placement/creative ID. </p> <p><b>DFA &gt; SearchCenter Deduplication</b>: Specifies that DFA should place values in Searchcenter variables when DFA Click-throughs or View-throughs occur. For more information, see <a href="../../dfa-data-connector-analytics/dfa-integration-features.md#concept-ff93289d1662410e98f62c200394b3e3" format="dita" scope="local"> SearchCenter Deduplication </a> . </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 4 </td> 
   <td colname="col2"> Impressions </td> 
   <td colname="col3"> The Custom Event that receives DFA Impressions metric data. Impressions indicates the number of times the ad was served. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 4 </td> 
   <td colname="col2"> Clicks </td> 
   <td colname="col3"> Select the custom Event that receives DFA Clicks metric data. Clicks indicates the number of times visitors clicked on the ad as measured by DFA’s redirect. The Clicks metric correlates with the Analytics Click-throughs metric. <p>Note:  DFA Clicks and Analytics Click-throughs might not match exactly due to differences in the way data is collected. For more information, see <a href="../../dfa-data-connector-analytics/dfa-reconciling-metric-discrepancies/dfa-metric-definitions.md#concept-2d5cd5ddd2594bb386a16a2764f30982" format="dita" scope="local"> Metric Definitions </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 5 </td> 
   <td colname="col2"> View-Through Variable </td> 
   <td colname="col3"> <p>The Analytics eVar that receives DFA View-Through data. The View-Through variable helps you see how view-throughs affect conversion rates on your site. </p> <p>Data Connectors adds the same DFA-related classifications to this eVar as it does to the DFA Ad Variable (see above). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 5 </td> 
   <td colname="col2"> Time Since Last View (view-through time bucket variable) </td> 
   <td colname="col3"> The Analytics eVar that receives DFA Time Since Last View data. The Time Since Last View indicates the amount of time that has lapsed since the last ad view-through. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 5 </td> 
   <td colname="col2"> View-Throughs </td> 
   <td colname="col3"> The Custom Event that receives DFA View-Throughs metric data. Use the View-Throughs event with the View-Through Variable to see which campaigns didn’t influence a direct click-through, but may have played a role in driving traffic to the site at some subsequent time. <p>Data Connectors renames the selected Custom Event to “View Throughs”. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 6 </td> 
   <td colname="col2"> DFA Query Failure </td> 
   <td colname="col3"> (Optional) The Analytics eVar that receives any reported DFA query failure message codes. Possible DFA message codes include: 
    <ul id="ul_85FC7FB19F7F4ADF83ABCA6DDB44CE19"> 
     <li id="li_0A3181DED5A149588A0D3F1584E2FE8B"><b>nc</b>: No DoubleClick cookie. </li> 
     <li id="li_D397AA73AD5E4086A18B87F271E4EC14"><b>oo</b>: User has opted out. </li> 
     <li id="li_5AC1D0C8049340B4AD857D88E275CBD6"><b>nh</b>: No campaign history. </li> 
     <li id="li_73A8C5E905C54E2BB531A1FCDBC6AA1A"><b>qe</b>: Query error (time out, server down, etc.) </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 6 </td> 
   <td colname="col2"> Timeout Event </td> 
   <td colname="col3"> <p>The Analytics Counter Event that increments each time the <span class="varname"> s.maxDelay </span> timer expires, and no response was received from the DFA servers. Use this event to configure the <span class="varname"> s.maxDelay </span> variable (see <a href="../../dfa-data-connector-analytics/dfa-integration/dfa-tuning-s-maxlelay.md#concept-6deb28eee18e414db220d6009d449f0d" format="dita" scope="local"> Tuning s.maxDelay </a>.) </p> </td> 
  </tr> 
 </tbody> 
</table>

