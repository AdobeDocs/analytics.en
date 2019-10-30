---
title: Troubleshoot sessions in Adobe Analytics
description: Learn how resolve issues around being logged out of Adobe Analytics.
seo-title: Troubleshoot sessions in Adobe Analytics
seo-description: Learn how resolve issues around being logged out of Adobe Analytics.
---

# Troubleshoot sessions in Adobe Analytics

This page is about troubleshooting sessions, meaning you are able to successfully log in but have issues staying logged in. If you are having issues logging in to Adobe Analytics, see [Troubleshoot logging in to Adobe Analytics](troubleshoot-login.md).

Almost all session-based issues originate from an organization's customized corporate network. If you are able to login to Adobe Analytics but have trouble staying logged in, use this article to help determine the cause.

## Determine if the issue is due to your organization's network

Many organizations deploy additional network features to enhance security, such as proxy servers or firewalls. These customizations can sometimes interfere with the ability to retain an active session in Adobe Analytics.

To determine if the corporate network you're connected to is causing issues with using Adobe Analytics, use your Experience Cloud login credentials on a device outside of your corporate network. Examples of devices can be through your home network or a mobile device's data plan. If you are able to successfully move from page to page without being logged out, your organization's network is likely the reason why you get logged out of Adobe Analytics.

## Issues due to proxy

Adobe uses an authorization header when making requests to Adobe. Some proxies, such as Bluecoat (now owned by Symantec), strip critical authorization header information used by Adobe Analytics. When Adobe does not see the authorization header, the session expires.

To resolve this issue, Adobe recommends working with your organization's IT team to allow the authorization header through your organization's proxy.

> [!NOTE] Although members of the Analytics community have found the following links helpful, they are not owned by Adobe. Take this note into consideration when viewing their content.

Information on Symantec proxies and authentication headers can be found here:

* [Configure Upstream Proxy Authentication in a Proxy Chain Deployment on a ProxySG or ASG Appliance](https://support.symantec.com/en_US/article.TECH246122.html)
* [Allow ProxySG to always forward server authorization upstream](https://support.symantec.com/en_US/article.TECH244708.html)
