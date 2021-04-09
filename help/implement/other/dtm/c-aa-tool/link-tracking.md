---
description: Field descriptions in Dynamic Tag Management for link tracking when deploying Analytics.
keywords: Dynamic Tag Management;link tracking;enable clickmap;track download links;download extensions;track outbound links;keep url parameters
solution: Experience Cloud,Analytics
title: Link tracking
uuid: 982b744b-5696-4c31-b1d1-410486b0eedd
exl-id: cdce5e3f-bc36-47ab-9c96-f2faaa2c40b4
---
# Link tracking

Field descriptions in Dynamic Tag Management for link tracking when deploying Analytics.

 **[!UICONTROL Property]** > ![Gear icon](assets/settings_gear.png) **[!UICONTROL Edit Tool]** > **[!UICONTROL Link Tracking]**

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
   <td colname="col2"> <p>Determines whether visitor click map data is gathered. </p> <p>See <a href="../../../vars/config-vars/trackinlinestats.md">trackInlinestats</a>. </p> </td>
  </tr>
  <tr>
   <td colname="col1"> Track download links </td>
   <td colname="col2"> <p>Tracks links to downloadable files on your site. </p> <p>See <a href="../../../vars/config-vars/trackdownloadlinks.md">trackDownloadLinks</a>.</p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> Download Extensions </td> 
   <td colname="col2"> <p>If your site contains links to files with any of the listed extensions, the URLs of these links will appear in reporting. </p>See <a href="../../../vars/config-vars/linkdownloadfiletypes.md">linkDownloadFileTypes</a>. </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> Track outbound links </td>
   <td colname="col2"> <p>Determines whether any link clicked is an exit link. </p> <p>See <a href="../../../vars/config-vars/trackexternallinks.md">trackExternalLinks</a>. </p> <p><b>Single-Page App Considerations: </b>Because of the way some SPA websites are coded, an internal link to a page on the SPA site might look like it is an outbound link. </p> <p>You can use one of the following methods to track outbound links from SPA sites: </p>
    <ul id="ul_A4179633ED0644C3BA5F548A58CA4EC9">
     <li id="li_1959FBF14E42469FA8724B37EB58BC54"> <p>If you do not want to track any outbound links from your SPA, insert an entry into the <span class="wintitle"> Never Track</span> section. </p> <p>For example, <span class="filepath"> https://testsite.com/spa/#</span> </p> <p>All # links to this host are ignored. All outbound links to other hosts are tracked, such as <span class="filepath"> https://www.google.com</span>. </p> </li>
     <li id="li_37DD4D37887243FB928C9C04ACE9D39E"> <p>If there are some links that you want to track on your SPA, use the <span class="wintitle"> Always Track</span> section. </p> <p>For example, if you have a <span class="filepath"> spa/#/about</span> page, you could put "about" in the <span class="wintitle"> Always Track</span> section. </p> <p>The "about" page is the only outbound link that is tracked. Any other links on the page (for example, <span class="filepath"> https://www.google.com</span>) are not tracked. </p> </li>
    </ul> <p>Note that these two options are mutually exclusive. </p> </td> 
  </tr>
  <tr>
   <td colname="col1"> Keep URL Parameters </td>
   <td colname="col2"> <p>Preserves query strings. </p> <p>See <a href="../../../vars/config-vars/linkleavequerystring.md">linkLeaveQueryString</a>. </p> </td>
  </tr>
 </tbody>
</table>
