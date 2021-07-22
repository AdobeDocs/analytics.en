---
title: Adobe Analytics First Admin Guide
description: Understand how to get started with Adobe Analytics, general role types, and logging in to the UI.
exl-id: fbbbd335-0d22-473e-adef-f92f8eab7bf0
---
# Adobe Analytics First Admin Guide

A first admin is the starting point in enabling the rest of the organization to use each Experience Cloud solution. Once a contract has been signed, a provisioning team at Adobe prepares for the account to be created. The first admin receives an email with login credentials before the contract's start date. Ensuring the first admin's contact info is given to Adobe and accurate before the contract is signed is highly recommended.

## Key roles in using the Experience Cloud

If your organization has purchased Adobe Analytics, there are several key roles to consider:

* **Adobe Analytics admins:** These users have full access to everything in Adobe Analytics, including report suite settings and user permissions. Depending on how your organization is structured, different people or teams can be responsible for different facets of Analytics administration. For example, one person is responsible for the designation of what variables to use in an implementation. Another person can be responsible for enabling users to correctly pull reports by ensuring everyone has the correct permissions. Identify at least one user who can be responsible for Analytics report suite settings and user permissions, and they can invite other Analytics admins from there.
* **Adobe Experience Platform Launch admins:** These users have full access to everything in the Data Collection UI (formerly called Experience Platform Launch), including publishing permissions, creating containers, and user permissions. These users are not necessarily programmers, but having at least a beginner's knowledge of HTML, CSS, and JavaScript is beneficial. They are responsible for working with your organization's website owners to get the Experience Platform tags implemented on your site. Identify at least one user who is responsible for your organization's implementation, and they can invite other Experience Platform Launch admins from there.
* **Support delegates**: Also known as supported users, they have no additional privileges in the Analytics interface. Instead, they receive additional privileges when communicating with Adobe Customer Care. These users are almost always Analytics admins as well, as it helps Customer Care troubleshoot issues with them. Identify at least one Analytics admin who is responsible for facilitating interactions between end users and Adobe Customer Care.
* **Website owners:** These individuals or teams are responsible for the coding and development of your website. They do not require accounts, but they want to work with Experience Platform Launch admins to get the Experience Platform Launch code and implement it on your website.
* **End users:** these users typically view reports and seek answers to business questions. Analytics admins grant these users permissions to work in the product.

As a first admin, your role can overlap in one or more of these roles. As long as each of these basic responsibilities are covered, you can grant permissions to get others in your organization up and running.

## Granting product admin access for Analytics

System-level admins do not have direct access to products, however they can give themselves access by adding themselves as a product-level admin. If you want to give yourself or others access to Adobe Analytics, you can follow these steps.

1. Log in to the [Admin Console](https://adminconsole.adobe.com/) with your Adobe ID credentials.
1. Click the Products tab at the top. All products purchased by your organization are on the left. Click Adobe Analytics, then click the New Profile button.
1. Name this profile 'Analytics full admin access', then click Done.
1. Back on the Product Profiles page, click the newly created profile, then click the Permissions tab.
1. Click one of the permission line items. If Auto-include is available, enable it. If auto-include is not available, click Add all. Both options move all permission items to the right column.
1. Click save. Repeat the above step for all permission categories.
1. Once all permission categories are granted to the profile, go back to the Overview page by clicking Overview at the top.
1. Under the Adobe Analytics tile, click 'Assign Users'.
1. Enter the email address you would like to give full Analytics access to, and assign them the newly created full admin access profile. Click Save.
1. The user now has full access to Adobe Analytics.

## Granting product admin access for Data Collection in Experience Platform (formerly called Launch)

Product admin access for tags in Experience Platform is nearly identical to granting product admin access for Analytics.

1. Log in to the Admin Console with your Adobe ID credentials.
1. Click the Products tab at the top. All products purchased by your organization are on the left. Click Experience Platform Launch by Adobe, then click the New Profile button.
1. Name this profile 'Experience Platform Launch full admin access', then click Done.
1. Back on the Product Profiles page, click the newly created profile, then click the Permissions tab.
1. Click one of the permission line items. If Auto-include is available, enable it. If auto-include is not available, click Add all. Both options move all permission items to the right column.
1. Click save. Repeat the above step for all permission categories.
1. Once all permission categories are granted to the profile, go back to the Overview page by clicking Overview at the top.
1. Under the Experience Platform Launch by Adobe tile, click 'Assign Users'.
1. Enter the email address you would like to give full Analytics access to, and assign them the newly created full admin access profile. Click Save.
1. The user now has full access to Experience Platform Launch.

## Next Steps

[Create a Report Suite](/help/admin/c-manage-report-suites/c-new-report-suite/t-create-a-report-suite.md): Have your Analytics admin login to the tool and create a report suite for data collection

[Create a property in Experience Platform Launch](/help/implement/launch/create-analytics-property.md): Have your Experience Platform Launch admin login to the tool and create a property to implement on your site
