---
description: Information about the three ways to sign in to Report Builder.
seo-description: Information about the three ways to sign in to Report Builder.
seo-title: Report Builder Sign-In
solution: Analytics
title: Report Builder Sign-In
topic: Report builder
uuid: 930b7aec-bc9a-49bb-a327-44f5cc17df29
index: y
internal: n
snippet: y
translate: y
---

# Report Builder Sign-In

Currently, the following login options are available when you click ** [!UICONTROL  Sign In] ** to Report Builder. 

![](../../assets/login_screen.png) 

* [ Standard](../../report_builder_bucket/setup/login.md#section_6D54B8ADAE7F416BB83F5082B3771CFA)
* [ Single Sign-On](../../report_builder_bucket/setup/login.md#section_6970A5F926774976B85FFE576610E85F)
* [ Experience Cloud and Single Sign-On](../../report_builder_bucket/setup/login.md#section_1FA230F35AB54021A874A7A28DE4C850)

## Standard {#section_6D54B8ADAE7F416BB83F5082B3771CFA}

Use this login if you want to sign in to Report Builder using your Adobe Analytics credentials. 

**Report Builder login - field definitions** 

<table id="table_2D2239345A4643DB84A56A525FAF048D"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Field </th> 
   <th colname="col2" class="entry"> Definition </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Company </p> </td> 
   <td colname="col2"> <p>The Company login credential that you use for Adobe Analytics. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Username </p> </td> 
   <td colname="col2"> <p>The Username login that you use for Adobe Analytics. Scheduled tasks for a user are linked to the username. You can view your scheduled tasks from any computer if you log in to report builder with the same login credentials. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Password </p> </td> 
   <td colname="col2"> <p>Your Analytics password. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Remember me </p> </td> 
   <td colname="col2"> <p>Login information is encrypted and stored in a user profile file on the machine where Report Builder is installed. Because login information is saved, anyone using the same PC as the report creator who opens a spreadsheet containing a report can refresh and edit the data. If you share your computer with others and you wish to keep the spreadsheet data private, do not enable this option. </p> <p>To disable your automatic login setting, click <span class="uicontrol"> Log in With Different Credentials</span> on the Toolbar and disable <span class="uicontrol"> Remember Me</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Use a Proxy Server </p> </td> 
   <td colname="col2"> <p>Enable if you are accessing the Internet through a proxy server and are required to provide a proxy username and password. </p> </td> 
  </tr> 
 </tbody> 
</table>


## Single sign-on {#section_6970A5F926774976B85FFE576610E85F}

This (legacy) single sign-on logs you in to Adobe Analytics only, not the entire Experience Cloud. 

You can also type in a domain and the system will recognize the domain and redirect you to your company's sign-in page to log in to Adobe Analytics. 

## Experience Cloud {#section_1FA230F35AB54021A874A7A28DE4C850}

The Experience Cloud login lets you use your Enterprise ID (email and password) to log in to the Adobe Experience Cloud. Click ** [!UICONTROL  Sign In] ** > ** [!UICONTROL  Sign in with an Enterprise ID] ** to be redirected to your company's single sign-on page. For more information on Enterprise ID, click [ here](https://helpx.adobe.com/enterprise/kb/enterprise-id-faq.html#whatis). 

![](../../assets/adobe_id_login.png) 

>[!NOTE]
>
>The Experience Cloud login is session based and the token expires after 30 days.

