---
description: Field descriptions in Dynamic Tag Management for link tracking when deploying Analytics.
keywords: Dynamic Tag Management;link tracking;enable clickmap;track download links;download extensions;track outbound links;keep url parameters
seo-description: Field descriptions in Dynamic Tag Management for link tracking when deploying Analytics.
seo-title: Link tracking
solution: Marketing Cloud,Analytics,Dynamic Tag Management
title: Link tracking
uuid: 201beb91-7f08-4936-ba91-7418292d4f66
index: y
internal: n
snippet: y
---

# Link tracking

Field descriptions in Dynamic Tag Management for link tracking when deploying Analytics.

 **[!UICONTROL  *`Property`*]** > **[!UICONTROL   ![](assets/settings_gear.png)

Edit Tool]** > **[!UICONTROL Link Tracking]** 

<table id="table_F23FB0B284E74B66A107B1D69D22A51C"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Element </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Enable ClickMap </td> 
   <td colname="col2"> <p>Determines whether visitor click map data is gathered. </p> <p>See <a href="trackInlineStats.md#concept_E3A811D9761E4917935F6CD9059C7FCC" format="dita" scope="local"> s.trackInlineStats</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Track download links </td> 
   <td colname="col2"> <p>Tracks links to downloadable files on your site. </p> <p>See <a href="trackDownloadLinks.md#concept_0A7AEAB3172A4BEA8B2E8B1A3A8F596C" format="dita" scope="local"> s.trackDownLoadLinks</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Download Extensions </td> 
   <td colname="col2"> <p>If your site contains links to files with any of the listed extensions, the URLs of these links will appear in reporting. </p> <p>See <a href="linkDownloadFileTypes.md#concept_06CC14C69DFD4887A5E6967A157A9E05" format="dita" scope="local"> s.linkDownloadFileTypes</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Track outbound links </td> 
   <td colname="col2"> <p>Determines whether any link clicked is an exit link. </p> <p>See <a href="trackExternalLinks.md#concept_E1321318696841648A54CF77F6C4A7AF" format="dita" scope="local"> s.trackExternalLinks</a>. </p> <p><b>Single-Page App Considerations: </b>Because of the way some SPA websites are coded, an internal link to a page on the SPA site might look like it is an outbound link. </p> <p>You can use one of the following methods to track outbound links from SPA sites: </p> 
    <ul id="ul_A4179633ED0644C3BA5F548A58CA4EC9"> 
     <li id="li_1959FBF14E42469FA8724B37EB58BC54"> <p>If you do not want to track any outbound links from your SPA, insert an entry into the <span class="wintitle"> Never Track</span> section. </p> <p>For example, <span class="filepath"> http://testsite.com/spa/#</span> </p> <p>All # links to this host are ignored. All outbound links to other hosts are tracked, such as <span class="filepath"> http://www.google.com</span>. </p> </li> 
     <li id="li_37DD4D37887243FB928C9C04ACE9D39E"> <p>If there are some links that you want to track on your SPA, use the <span class="wintitle"> Always Track</span> section. </p> <p>For example, if you have a <span class="filepath"> spa/#/about</span> page, you could put "about" in the <span class="wintitle"> Always Track</span> section. </p> <p>The "about" page is the only outbound link that is tracked. Any other links on the page (for example, <span class="filepath"> http://www.google.com</span>) are not tracked. </p> </li> 
    </ul> <p>Note that these two options are mutually exclusive. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Keep URL Parameters </td> 
   <td colname="col2"> <p>Preserves query strings. </p> <p>See <a href="linkLeaveQueryString.md#concept_118C280E29394DB5A16DBBF41EB4D742" format="dita" scope="local"> s.linkLeaveQueryString</a>. </p> </td> 
  </tr> 
 </tbody> 
</table>

