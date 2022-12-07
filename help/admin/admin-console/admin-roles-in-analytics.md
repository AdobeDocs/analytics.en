---
title: Administrator roles in Adobe Analytics
description: Understand how to get started with Adobe Analytics, general role types, and logging in to the UI.
feature: Admin Tools
exl-id: 9d10716f-5b66-42dc-b288-af34da203c35
---
# Administrator roles in Adobe Analytics

Adobe Analytics supports various types of administrators. Full Adobe Analytics admins have access to everything in Adobe Analytics, while other admins and users can perform more specialized tasks. 

>[!NOTE]
>
>Before any users can be assigned roles in Adobe Analytics, a user must be assigned as a first admin in Experience Cloud. The first admin can then provision users in the organization with other key roles, as described in this article. For more information about the first admin, see [Adobe Analytics first admin guide](/help/admin/admin-console/first-admin-guide.md).


## Key roles in Experience Cloud and Adobe Analytics

Consider the following key roles when using Adobe Analytics:

* **Full Adobe Analytics admins:** These users have full access to everything in Adobe Analytics, including report suite settings and user permissions. Depending on how your organization is structured, different people or teams can be responsible for different facets of Analytics administration. For example, one person is responsible for the designation of what variables to use in an implementation. Another person can be responsible for enabling users to correctly pull reports by ensuring everyone has the correct permissions. Identify at least one user who can be responsible for Analytics report suite settings and user permissions, and they can invite other Analytics admins from there.
* **Data Collection admins:** These users have full access to everything in Adobe Experience Platform Data Collection, including publishing permissions, creating containers, and user permissions. These users are not necessarily programmers, but having at least a beginner's knowledge of HTML, CSS, and JavaScript is beneficial. They are responsible for working with your organization's website owners to get tags implemented on your site. Identify at least one user who is responsible for your organization's implementation, and they can invite other data collection admins from there.
* **Product Profile admins:** These users can add or remove users to a product profile, adjust permissions items in their product profile, and assign or remove product profiles to user groups. Product Profile admins do not have full access to Adobe Analytics. However, they are ideal for team leads or managers who need to grant and manage access to Adobe Analytics for their team. For more information about product profiles, see [Product profiles for Adobe Analytics](/help/admin/admin-console/permissions/product-profile.md).
* **Support delegates**: Also known as supported users, they have no additional privileges in the Analytics interface. Instead, they receive additional privileges when communicating with Adobe Customer Care. These users are almost always Analytics admins as well, as it helps Customer Care troubleshoot issues with them. Identify at least one Analytics admin who is responsible for facilitating interactions between end users and Adobe Customer Care.
* **Website owners:** These individuals or teams are responsible for the coding and development of your website. They do not require accounts, but they want to work with data collection admins to get the tag code and implement it on your website.
* **End users:** these users typically view reports and seek answers to business questions. Analytics admins grant these users permissions to work in the product.

## Grant full product admin access for Analytics

System-level admins do not have direct access to products; however, they can give themselves access by adding themselves as a product-level admin. 

To give Adobe Analytics access to yourself or to others:

1. Log in to the [Admin Console](https://adminconsole.adobe.com/) with your Adobe ID credentials.
1. Click the **[!UICONTROL Products]** tab at the top. All products purchased by your organization are on the left. Click **[!UICONTROL Adobe Analytics]**, then click the **[!UICONTROL New Profile]** button.
1. Name this profile 'Analytics full admin access', then click **[!UICONTROL Next]** > **[!UICONTROL Save]**.
1. Back on the Product Profiles page, click the newly created profile, then click the **[!UICONTROL Permissions]** tab.
1. Click one of the permission line items. If **[!UICONTROL Auto-include]** is available, enable it. If **[!UICONTROL Auto-include]** is not available, click **[!UICONTROL Add all]**. Both options move all permission items to the right column.
1. Click **[!UICONTROL Save]**. 
Repeat the above step for all permission categories.
1. After all permission categories are granted to the profile, go back to the Products page by clicking **[!UICONTROL Product]** at the top.
1. Under the Adobe Analytics tile, click **[!UICONTROL Assign Users]**.
1. Enter the email address you would like to give full Analytics access to, and assign them the newly created full admin access profile. Click **[!UICONTROL Save]**.

The user now has full access to Adobe Analytics.

## Grant product admin access for Data Collection in Experience Platform

Product admin access for Data Collection in Experience Platform is nearly identical to granting product admin access for Analytics.

1. Log in to the [Adobe Admin Console](https://adminconsole.adobe.com) with your Adobe ID credentials.
1. Click the **[!UICONTROL Products]** tab at the top. All products purchased by your organization are on the left. Click **[!UICONTROL Experience Platform Launch]**, then click **[!UICONTROL New Profile]**.
1. Name this profile 'Data Collection full admin access', then click **[!UICONTROL Done]**.
1. Back on the **[!UICONTROL Product Profiles]** page, click the newly created profile, then click the **[!UICONTROL Permissions]** tab.
1. Click one of the permission line items. If **[!UICONTROL Auto-include]** is available, enable it. If auto-include is not available, click **[!UICONTROL Add all]**. Both options move all permission items to the right column.
1. Click **[!UICONTROL Save]**. Repeat the above step for all permission categories.
1. Once all permission categories are granted to the profile, go back to the Overview page by clicking **[!UICONTROL Overview]** at the top.
1. Under the [!UICONTROL Experience Platform Launch] tile, click **[!UICONTROL Assign Users]**.
1. Enter the email address you would like to give full Analytics access to, and assign them the newly created full admin access profile. Click **[!UICONTROL Save]**.
1. The user now has full access to Experience Platform Data Collection.

## Grant product admin access for Product Profiles

For information about assigning users as product profile admins, see the "Manage product profile admins" section in the article, [Manage product profiles for enterprise users](https://helpx.adobe.com/enterprise/using/manage-product-profiles.html) in the Enterprise user guide.

## Next steps

[Create a Report Suite](/help/admin/c-manage-report-suites/c-new-report-suite/t-create-a-report-suite.md): Have your Analytics admin log in to the tool and create a report suite for data collection

[Create an Analytics tag property](/help/implement/launch/create-analytics-property.md): Have your Data Collection admin log in to the tool and create a property to implement on your site

Before any users can be assigned roles in Adobe Analytics, a user must be assigned as a first admin in Experience Cloud. The first admin can then provision users in the organization with other key roles, as described in this article.

A first admin is the starting point in enabling the rest of the organization to use each Experience Cloud solution. 

After a contract is signed

1. The provisioning team at Adobe prepares for the account to be created. 

1. The first admin receives an email with login credentials before the contract's start date. 

>[!IMPORTANT]
>
>   Ensuring the first admin's contact info is given to Adobe and accurate before the contract is signed is highly recommended.
