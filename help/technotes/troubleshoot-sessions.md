---
title: Troubleshoot sessions in Adobe Analytics
description: Learn how resolve issues around being logged out of Adobe Analytics.
feature: Analytics Basics
exl-id: 191250ef-8313-47be-9717-046cce870998
TQID: https://experienceleague.adobe.com/b8dTBhP3a6FZSmABKtQKTp9XkmYIjfS5--Vbzl6xRGE
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: a421fb65-2c82-457a-921c-28c46b697a39
    internal-label: Analytics basics
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: c1579802-ddd4-4214-8a91-97b2066abe11
    internal-label: Troubleshooting
  - id: d095671a-1355-40aa-8b5f-06c33c68080b
    internal-label: Security
---
# Troubleshoot sessions in Adobe Analytics

This page is about troubleshooting sessions, meaning you are able to successfully log in but have issues staying logged in. If you are having issues logging in to Adobe Analytics, see [Troubleshoot logging in to Adobe Analytics](troubleshoot-login.md).

Almost all session-based issues originate from an organization's customized corporate network. If you are able to login to Adobe Analytics but have trouble staying logged in, use this article to help determine the cause.

## Determine if the issue is due to your organization's network {#network}

Many organizations deploy additional network features to enhance security, such as proxy servers or firewalls. These customizations can sometimes interfere with the ability to retain an active session in Adobe Analytics.

To determine if the corporate network you're connected to is causing issues with using Adobe Analytics, use your CX Enterprise login credentials on a device outside of your corporate network. Examples of devices can be through your home network or a mobile device's data plan. If you are able to successfully move from page to page without being logged out, your organization's network is likely the reason why you get logged out of Adobe Analytics.

## Issues due to proxy {#proxy}

Adobe uses an authorization header when making requests to Adobe. Some proxies, such as Edge Secure Web Gateway (formerly Bluecoat), strip critical authorization header information used by Adobe Analytics. When Adobe does not see the authorization header, the session expires.

To resolve this issue, Adobe recommends working with your organization's IT team to allow the authorization header through your organization's proxy.

>[!NOTE]
>
>Although members of the Analytics community have found the following links helpful, they are not owned by Adobe. Take this note into consideration when viewing their content.

Information on proxies and authentication headers can be found here:

* [Configure Upstream Proxy Authentication in a Proxy Chain Deployment on a ProxySG or ASG Appliance](https://techdocs.broadcom.com/us/en/symantec-security-software/web-and-network-security/edge-swg/7-3/authentication_co.html)
* [How to forward user credentials to a server behind the ProxySG appliance](https://knowledge.broadcom.com/external/article/165859/how-to-forward-user-credentials-to-a-ser.html)
