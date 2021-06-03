---
description: What you need to know about the Analytics user ID migration to the Admin Console in the Adobe Experience Cloud.
title: Analytics User Migration to the Admin Console
uuid: 7d020713-693b-4945-aa52-3669a631aacb
---

# Analytics User Migration to the Admin Console{#analytics-user-migration-to-the-admin-console}

What you need to know about the Analytics user ID migration to the Admin Console in the Adobe Experience Cloud.

For general help on Admin Console topics (not related to the Analytics migration), see [Admin Console User Guide](https://helpx.adobe.com/enterprise/administering/user-guide.html).

After you migrate, you can [manage Experience Cloud users and products](https://experienceleague.adobe.com/docs/core-services/interface/manage-users-and-products/admin-getting-started.html) in the Admin Console.

## What is the Analytics user ID migration? {#section-adbe49aba10c4e62afa836a97894107c}

The Analytics user ID migration enables administrators to easily migrate user accounts in Analytics User Management to the Adobe Admin Console. After your users are migrated, they will have access to the solutions and core services available in the Experience Cloud. The migration is being rolled out to customers in phases.

The benefits of using the Admin Console include: 

<table id="table_E4465796E224474680D750CAC5434ED3"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Benefit </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Single sign-on </p> </td> 
   <td colname="col2"> <p>Analytics users can sign in to the Experience Cloud and all solutions using their Adobe ID or Enterprise ID. This sign-in enables access to integrated solutions and core services in the Experience Cloud. </p> <p>After the migration, users who attempt to sign in via legacy logins (<span class="filepath"> my.omniture.com</span> and <span class="filepath"> sc.omniture.com</span>) are redirected to <span class="filepath"> experiencecloud.adobe.com</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Manage user identity and permissions </p> </td> 
   <td colname="col2"> <p>Analytics administrators can manage users and permissions exclusively in the <a href="http://adminconsole.adobe.com/enterprise/"> Admin Console</a> (http://adminconsole.adobe.com/enterprise/). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Manage products and core services </p> </td> 
   <td colname="col2"> 
    <ul id="ul_01043FEF271E4B27BF34980D629D1932"> 
     <li id="li_DC31AE8BAAB843F39A7CC9EB047265D5">Invite new users </li> 
     <li id="li_73724DD7D79E41F8A1D58C74E37674BA">Create product profiles </li> 
     <li id="li_7E75FC68E0F84873A9A211D2707B6DE7">Grant users permission to specific products and services </li> 
     <li id="li_9C8A340A7C9A45A98EC0BD4AF9E100FF">Gain access to <a href="https://experienceleague.adobe.com/docs/core-services/interface/experience-cloud.html"> cross-solution core services</a> available in the Adobe Experience Cloud </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

## What to know (and do) before migrating user IDs (FAQ) {#section-b0fc7f0bbd4b488e95b0c8e77ff077a9}

Answers to questions you might have before the migration.

<table id="table_36FD7EF1DAB44D359F4FC186D93147E5"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Question / Task </th> 
   <th colname="col2" class="entry"> Answer </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>I am an Analytics administrator and received a pre-migration email. What do I do first? </p> </td> 
   <td colname="col2"> <p>Verify that you have an Adobe ID and can access the <a href="https://adminconsole.adobe.com/enterprise/"> Experience Cloud Admin Console</a>. </p> <p>If not, contact <a href="https://helpx.adobe.com/marketing-cloud/contact-support.html"> Adobe Customer Care</a>. (You should first contact your system or product administrator who can invite you to the proper organization.) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>AEM integrations with Analytics </p> </td> 
   <td colname="col2"> <p> AEM users with an integration to Analytics will need to change their configuration to use the Analytics shared secret instead of the password. </p> <p> You should do this before the migration is enabled. Once the migration is disabled, the originally configured password will no longer be valid. </p> <p><b>To obtain the shared secret in Analytics</b> </p> <p> The shared secret can be obtained from Analytics (<span class="uicontrol"> Analytics</span> &gt; <span class="uicontrol"> User Management</span>) and is different for each user. </p> <p><b>To update your AEM configuration with the shared secret</b> </p> <p>See <a href="https://helpx.adobe.com/experience-manager/6-3/sites/administering/using/adobeanalytics-connect.html"> Connecting to Adobe Analytics and Creating Frameworks</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Update Report Builder </p> </td> 
   <td colname="col2"> <p> <p>Important: Update your installation of <a href="https://experienceleague.adobe.com/docs/analytics/analyze/report-builder/report-builder-setup/t-install-arb.html"> Report Builder</a> to the latest version. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>When does the migration begin? </p> </td> 
   <td colname="col2"> <p>Adobe will notify Analytics administrators via email with instructions about when the migration will begin. </p> <p>Migrations to the Admin Console will occur in waves. On the day of migration, Adobe notifies Analytics administrators and grants them access to the migration tool. After a login company meets the criteria defined for each migration wave, Adobe will: </p> 
    <ul id="ul_D7DDC62A08AB4407B122985EDEA6ABD1"> 
     <li id="li_BA0AD50DCDC14C90ADD513DEF6F78180">Set the start and end dates for the company's migration. </li> 
     <li id="li_C048A5C64FAA46C4BB41EF24F1CEDF62">Send an email notification to the company's current Analytics administrators, approximately 30 days before their migration. </li> 
     <li id="li_476265B24CE2404B995201170C75D674">Display an in-product notification informing administrators of the start date of the migration. </li> 
    </ul> <p> On the day of the migration, your former permission groups are automatically copied to the Admin Console. You will no longer be able to invite new users or create new groups in Analytics Admin Tools. </p> <p>After the migration: </p> 
    <ul id="ul_4639963EB08F407F8C18ACE2B3D30223"> 
     <li id="li_7F24A3FC900146C3B2E988D399C859EA">Administrators will use the Admin Console to manage their Analytics users and permissions. (You will no longer use the user management interface in Analytics &gt; Admin &gt; User Management.) </li> 
     <li id="li_5B5234D4F94A4B96A8920F6A5831A64C">Users will access Analytics using their Adobe or Enterprise ID through the Experience Cloud instead of <span class="filepath"> my.omniture.com</span>. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>What will happen on the start date of the migration? </p> </td> 
   <td colname="col2"> <p>At 10:00 a.m. UTC on the start date of the migration: </p> 
    <ul id="ul_25D1DBDF5C804D048E741F31550FF5F3"> 
     <li id="li_418476105FE341229CE146E730AAB33D">Your existing permission groups in Analytics will be replicated automatically in the Admin Console as Product Profiles, including their description and granular permissions across report suites, metrics, dimensions, Analytics, and Report Suite Tools. </li> 
     <li id="li_412F88C454B0455A8F3BC8016226855C">If any of your current Analytics users were created in the Admin Console (meaning they have a linked Adobe/Enterprise ID), they will be added to the appropriate Product Profiles in the Admin Console. </li> 
     <li id="li_8A05137EC05C4FD5910E73FE58300DCB">The User Management section under the Admin tab in Analytics will be set to <span class="term"> read-only</span>. You will no longer be able to create new users or permission groups here and will need to perform both these functions in the Admin Console. See <a href="/help/admin/user-management2/user-migration/c-migration-tool.md#section-928ffba27a0446e0af575b720434ef56"> Unsupported Analytics features in the Admin Console</a> for more information. </li> 
     <li id="li_2742DE69E9B547198A58E1F33E908361">As an administrator, you will be granted access to the <a href="https://experienceleague.adobe.com/docs/analytics/admin/user-product-management/user-management/migrate-users/t-migrate-users.html">User ID Migration tool</a>. Additionally, an in-product notification appears that includes the end date of the migration (typically 60 days in the future) in addition to links to help content and FAQs. </li> 
     <li id="li_095D42E3A3544FC59A60A8C8F94C971B">You will be granted access to a Permissions tab in the Admin Console that allows you to create Product Profiles with all the granular options you are familiar with in Analytics. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>How do I migrate user IDs? </p> </td> 
   <td colname="col2"> <p> Click <a href="/help/admin/user-management2/user-migration/t-migrate-users.md#task-f3355f3b14a340feae58cfa04c0ba1c9"> Migrate User IDs</a> on the Admin page, under User Management. Use the tool to add users to product profiles in the Admin Console (replicated from permission groups in Analytics). You can migrate user IDs at your own pace. </p> <p>Administration privileges are required. Once the migration is complete, it cannot be reversed. </p> <p>On the end date of the migration, <span class="filepath"> my.omniture.com</span> access will be disabled for users within their login company. Users (including those that are yet to be migrated) will be redirected to login via the new Experience Cloud URL (<span class="filepath"> experiencecloud.adobe.com</span>) </p> <p>Note:  Adobe recommends taking the opportunity to perform an audit of your users and groups before migrating. Delete old and unused accounts, or accounts that should no longer have access to the product (such as employees no longer with the organization). </p> <p>Related topic: <a href="/help/admin/user-management2/user-migration/migrate-enterprise.md"> Migrate Analytics user accounts for Enterprise and Federated IDs</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Will the migration affect my Analytics implementation or how data is collected? </p> </td> 
   <td colname="col2"> <p>No. </p> <p>The migration tool exists to help you transition user IDs and permissions from Analytics User Management to the <a href="https://adminconsole.adobe.com/enterprise/"> Experience Cloud Admin Console</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>How long does the migration process take? </p> </td> 
   <td colname="col2"> <p>All current Analytics administrators will receive a pre-migration notification email four weeks prior to the migration. (The actual start date will appear in the Analytics interface.) </p> <p>When the migration begins, administrators will have 60 days to complete the process. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Can I expedite my migration? </p> </td> 
   <td colname="col2"> <p>Yes. However, Adobe recommends that you use the time before the migration begins to: </p> 
    <ul id="ul_52C7EC44A5534975BFD7A6F37A829C25"> 
     <li id="li_8CFFF72877E8456DAC3241143AD648AD">Verify that you are an Analytics product administrator in the Admin Console. </li> 
     <li id="li_25DAA8D1EEDA45A0B5B59472BD8896C4">Communicate to your user base that their login experience will change when the migration begins. </li> 
     <li id="li_5B50F942F6A8483FAFA500AFF428702C">Audit your current users and permissions and perform clean-up activities. </li> 
    </ul> <p>To expedite your migration, contact your Customer Success Manager at <a href="https://helpx.adobe.com/marketing-cloud/contact-support.html"> Adobe Customer Care</a> and submit a request for an earlier start date. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> I am an Analytics administrator without access to the Admin Console. Who can help me gain access to the Admin Console? </p> </td> 
   <td colname="col2"> <p>Any system or product administrator that has access to your organization's Admin Console can give you access. If you are not sure who within your organization has administrator privileges in the console, contact <a href="https://helpx.adobe.com/marketing-cloud/contact-support.html"> Adobe Customer Care</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Can I postpone the migration start date? </p> </td> 
   <td colname="col2"> <p>Yes. Contact <a href="https://helpx.adobe.com/marketing-cloud/contact-support.html"> Adobe Customer Care</a>. </p><p>See below for a description of the changes to your current Analytics User and Permissions management on the start date. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Now that my company is migrating to the Admin Console, where do I create new users and permission groups before the start date of the migration? </p> </td> 
   <td colname="col2"> <p>Before your migration start date, you can create users in the Admin Console or in Analytics &gt; User Management. </p> <p>After migration begins, you can create users and permission groups only in the Admin Console. </p><p>see the Migration section below for more details on what happens on the start date of the migration. </p>
   </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> When can I implement single sign-on using Federated IDs? </p> </td> 
   <td colname="col2"> <p> A tool will be available soon in the Admin Console that enables you to change ID types from Adobe IDs to Federated IDs. During the migration, you cannot migrate users as Federated IDs. </p> </td> 
  </tr> 
 </tbody> 
</table>

## What to know during the migration (FAQ) {#section-d394524aa6d046d79025bbd7499792bc}

Important information about the migration process and how it impacts current user management.

<table id="table_0E37BB1DEA6143F0B5F4E861FCFA7189"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Question </th> 
   <th colname="col2" class="entry"> Answer </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>How are permission groups replicated to the Admin Console? What about my users? </p> </td> 
   <td colname="col2"> <p>A migrated Analytics group is a called a <i>Product Profile</i> in the Admin Console. Permission settings for the original group are retained in the migration. However, the users assigned to the group are not migrated. When a user belonging to that group is migrated using the migration tool, that user is assigned to that product profile. </p> <p>For example, a West Coast Operations permission group that entitled its members to Report Builder and Analysis Workspace (with certain report suites, metrics, dimensions) will become a West Coast Operations product profile. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Can I delegate the migration effort to another administrator? </p> </td> 
   <td colname="col2"> <p>Once your migration begins, any administrator that accesses your Analytics instance via the Experience Cloud can use the migration tool to begin (or continue) migrating users. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Can I update permission group membership for un-migrated users? </p> </td> 
   <td colname="col2"> <p>Yes. You can change the group membership of un-migrated users from within the Analytics User Management section. </p><p>Awaiting clarification from Ashok about where that's done. </p>
   </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Can I create users and permission groups in Analytics after my migration begins, and then use the migration tool to move them to the Admin Console? </p> </td> 
   <td colname="col2"> <p> No. Once migration begins, all new users and permission groups (called Product Profiles in the Admin Console) must be created in the Admin Console. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Would users I migrate using the migration tool be assigned the same permissions they had in Analytics? </p> </td> 
   <td colname="col2"> <p>Yes. Users migrated using the tool will be accorded the permissions they currently have in Analytics. Furthermore, they will retain access to their Analytics assets (like segments, projects, calculated metrics, and so on) when they access Analytics via the Experience Cloud. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Do users I migrate to the Admin Console continue to have access to Analytics using <span class="filepath"> my.omniture.com</span>? </p> </td> 
   <td colname="col2"> <p>Yes. Migrated users will continue to be able to access Analytics using their existing user name and password via <span class="filepath"> my.omniture.com</span> until the end date of the migration, unless you disable their legacy login access via the migration tool. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Two or more of my users have the same email ID in their Analytics record. What happens if I migrate them? </p> </td> 
   <td colname="col2"> <p>Because user accounts in the Admin Console require unique email IDs, you will run into a "Duplicate Email ID" error when you try migrating more than one of these users. You can update the email IDs of un-migrated users under the User Management (legacy) section before you retry the migration. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> What do I do after migrating my users? </p> </td> 
   <td colname="col2"> <p>Disable their legacy login access to <span class="filepath"> my.omniture.com</span>. You will not be able to turn off legacy login unless they have been migrated. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Can I track the migration process? </p> </td> 
   <td colname="col2"> <p>The migration tool includes a dashboard that displays how many of your users have been successfully migrated, and how many of them have their legacy login disabled. </p> <p> Ideally, you will have successfully migrated your login company to the Admin Console when a 100% of your users have completed migration and have had their legacy logins disabled. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>I need to perform user and permission management during the migration. Which tool can I use to perform this task? </p> </td> 
   <td colname="col2"> <p>After the migration begins, you will use the Admin Console to create and manage new users and product profiles. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>What do my users experience when I migrate them using the tool? </p> </td> 
   <td colname="col2"> <p>They will receive a welcome email addressed to the email ID in their Analytics user record, notifying them about their new way to access Analytics via the Experience Cloud. If they do not have an existing Adobe ID, they will be prompted to create one, after which they can access the solution using their Adobe ID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Can I use APIs to migrate my users instead of using the migration tool? </p> </td> 
   <td colname="col2"> <p>No. You must use the migration tool to ensure all your existing users are migrated to the Admin Console. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>What Analytics user-management features are not available in the Admin Console? </p> </td> 
   <td colname="col2"> 
    <ul id="ul_3F3747D4C1D3420699F7D28EC0CA1AA0"> 
     <li id="li_BD943B3245FF47E7A0DDA6107EA1EF89">Asset transfer </li> 
     <li id="li_2DF7004D67ED4C6CB40461EEFB038A5A">User expiration </li> 
     <li id="li_980E3F5B98F344A492B0EBAD7F1DA60C">User logs </li> 
    </ul> <p>These will remain available to you in Analytics user management. </p> <p>See <a href="/help/admin/user-management2/user-migration/c-migration-tool.md"> Unsupported Analytics features in the Admin Console</a> for more information. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>We created several configurations in the Admin Console and mapped them to Analytics permission groups. What will happen to those configurations when the migration begins? </p> </td> 
   <td colname="col2"> <p>Analytics permission groups are recreated in the Admin Console as product profiles, just like all your other groups. This means you will see two product profiles in the console that essentially have duplicate permissions. You can delete duplicate product profiles from the Admin Console. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>What is my next step after migrating user? </p> </td> 
   <td colname="col2"> <p>Once you have migrated the user or a set of users, your next step is to disable their legacy login via <span class="filepath"> my.omniture.com</span>. You can do that by selecting these users in the migration tool and clicking on the contextual "Disable Legacy Login" option that appears at the top of the screen. Note that this option is only visible when you select a user or set of users that have all been migrated successfully to the Admin Console. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>What happens on the migration end date? </p> </td> 
   <td colname="col2"> <p>After the migration end date (60 days from the start of the migration), all users within your login company are redirected to login via the Experience Cloud login page using their Adobe IDs. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>I haven't been able to migrate all my users by the migration-end date. Would un-migrated users lose their access to Analytics? </p> </td> 
   <td colname="col2"> <p>Users that have not been migrated by the end date will be redirected to the Experience Cloud login page (experiencecloud.adobe.com) and will be unable to access Analytics. However, you will continue to have access to the migration tool so you can find and migrate them to restore their access. </p> </td> 
  </tr> 
 </tbody> 
</table>

## What to know after the migration (FAQ) {#section-9681baa01b8c41cdb9659b73b70b50ff}

<table id="table_F48CC9DFE3424AC9AD76A16882701C8F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Question / Issue </th> 
   <th colname="col2" class="entry"> Answers </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Deleting users from the Admin Console </p> </td> 
   <td colname="col2"> <p> In Analytics, a deleted user is set as <span class="term"> expired</span>, but the account continues to exist. Preserving the account enables the transferring assets, such as segments, calculated metrics, scheduled reports, projects, and so on. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Account expirations </p> </td> 
   <td colname="col2"> <p> You can manually set an account expiration date in Analytics in Admin Tools. Once the expiration date is met, the user will not be able to access Analytics, but their actual Experience Cloud user account (e.g. Adobe ID, Enterprise ID, Federated ID, etc.) doesn't expire. They can still log into Experience Cloud, they just won't be able to click into Analytics. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Unsupported Analytics features in the Admin Console {#section-928ffba27a0446e0af575b720434ef56}

>[!IMPORTANT]
>
>Review the following issues that may apply to you during the migration.

<table id="table_88E2FA03D5F241B79AB54D12F64B51DA"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Question / Issue </th> 
   <th colname="col2" class="entry"> Answers </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Log-in As </p> </td> 
   <td colname="col2"> <p> Admins migrating to the Admin Console will no longer be able to use the "Log-In As" function to access non-Admin user accounts that have been migrated to the Admin Console. This feature is being deprecated from Analytics. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>User expiration and asset transfer </p> </td> 
   <td colname="col2"> <p> The Admin Console does not support user expiration or asset transfer. Admins will use the Analytics Users and Assets section under Admin Tools in Analytics for both functions. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Last Access (Last Login) </p> </td> 
   <td colname="col2"> <p> Details around a users' last-login date and time will be available in the Analytics Users and Assets link and not the Admin Console. The last-login date in Analytics is specific to when users actually accessed Analytics from within Experience Cloud and does not reflect the date/time when they logged into the Experience Cloud. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>User Management APIs <a href="https://helpx.adobe.com/enterprise/help/identity.html"> Adobe-supported identity types</a> </p> </td> 
   <td colname="col2"> <p> Admins migrating to the Admin Console should configure<a href="https://www.adobe.io/apis/cloudplatform/usermanagement/docs/gettingstarted.html"> user management APIs</a> offered at Adobe I/O for programmatic access to user accounts in the Admin Console. </p> <p>The Analytics Permission APIs will be turned off when you are enabled for the migration. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Web Service Credentials </p> </td> 
   <td colname="col2"> <p> Users' web-service credentials (and their shared secret) will not be available in the Admin Console and can be accessed by clicking into the specific user from the Analytics Users and Assets section. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Single Sign-On </p> </td> 
   <td colname="col2"> <p> Analytics single sign-on configurations will be removed when you have completed the migration. They will remain active during the migration. Customers that use Analytics single sign-on should upgrade to <a href="https://helpx.adobe.com/enterprise/help/identity.html"> Adobe Federated ID</a>. </p> <p>Analytics recommends that you migrate your users as Adobe IDs first to easily create the Experience Cloud accounts, and then convert those accounts to Federated single-sign users. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Downloading permission groups </p> </td> 
   <td colname="col2"> <p> Downloading of Permission Group information will no longer be supported in either the Analytics Admin Tools or the Adobe Admin Console. Customers should use the adobe.io user management APIs to get permission group information in bulk. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Account Creation Date </p> </td> 
   <td colname="col2"> <p>Account Creation Date information is no longer supported in either the Analytics Admin Tools or the Adobe Admin Console. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Bulk Email </p> </td> 
   <td colname="col2"> <p>Bulk email to users will no longer be supported in either the Analytics Admin Console or the Adobe Admin Console. Customers can bulk export their users' email addresses from Adobe Admin Console and send an email using any email client they wish. </p> </td> 
  </tr> 
 </tbody> 
</table>

## How to notify your users about the migration {#section-f3b25f672a3a4d03b0559656fd99d20a}

You may want to pro-actively communicate this migration plan to your current users. Here is a template you can customize to send all your current Analytics users:

To email all users, navigate to **[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL All admin]** > **[!UICONTROL User management]** > [Email Users](https://docs.adobe.com/help/en/analytics/admin/user-product-management/t-email-users.html).

**Subject:** Coming Soon - A new way to login to Adobe Analytics and Adobe Experience Cloud.

**Body:** Hello Adobe Analytics users!

Our company will begin migrating all Adobe Analytics accounts away from [!DNL https://my.omniture.com/login/] to Adobe Experience Cloud ([experiencecloud.adobe.com](http://experiencecloud.adobe.com/)). With this migration, your Adobe Analytics account will be upgraded to enable access to Analytics via the Adobe Experience Cloud. While the method to access Analytics will change, all your existing permissions to your report suites and tools will be preserved.

**Next steps:** We will begin to migrate users beginning on **INSERT DATE**. Watch for a welcome message with your new login addressed to the email id listed under your analytics account. If you have not setup an [Adobe ID](https://helpx.adobe.com/x-productkb/global/adobe-id-account-change.html) linked to your email address, you will be asked to setup an account .

**Helpful resources:**

[Sign in and manage your profile settings](https://experienceleague.adobe.com/docs/core-services/interface/manage-users-and-products/getting-started-experience-cloud.html).

Please contact your Analytics administrators if you have any questions or concerns.

Best,

Analytics Admin 
