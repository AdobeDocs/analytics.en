---
description: Configure users and learn about data sampling.
title: Administration
uuid: 12f90223-139f-4a8d-bfd3-5cd9af7489d2
---

# Administration

Configure users and learn about data sampling.

For [!DNL Admin Console] help, see the [Analytics Reference](https://marketing.adobe.com/resources/help/en_US/reference/index.html).

## User Licenses {#concept_C1440741C77C471EB38A243B013EA620}

Before a user can log in, the user must be granted a user license. User licenses are concurrent-use licenses. Users can share user licenses, but the number of users at any given time is limited to the number of user licenses purchased.

<!-- 

c_user_license.html

 -->

When the number of logged-in users exceeds the number of available licenses, a dialog box notifies the user that all available licenses are in use. The user's position in the queue is shown along with a link to recheck the queue position. When a license becomes available, the user is notified with an email and a pop-up dialog box indicating that ad hoc analysis is available for access. The user then has 15 minutes to respond before losing the position in the queue.

## Grant User Licenses {#task_22AE669703EC48BA9685414538D8B1FA}

Steps that describe how local Reports and Analytics administrators can grant user licenses via the permissions system.

<!-- 

t_user_licenses.xml

 -->

1. Log in to the [!DNL Experience Cloud].
1. Click **[!UICONTROL Admin]** > **[!UICONTROL User Management]**.
1. Click **[!UICONTROL Edit Groups]**.

   If your company has purchased user licenses, the [!UICONTROL Ad Hoc Analysis License Users] group appears in the [!UICONTROL Group Name] column. The number of available licenses for user logins is also shown.

1. Click **[!UICONTROL Edit]**.
1. Under [!UICONTROL Assign User Logins], select the users you want to add to the group, then click **[!UICONTROL Add.]**
1. Click **[!UICONTROL Save Group]**.

   The licensing system does not limit the number of users that are added to a group. There is limited concurrent usage to the number of user licenses purchased.

## Manage User Sessions {#task_868C3DD9CB3F45D19B98EEF60F5E0B32}

Steps that describe how an administrator can terminate a user's session. This feature does not prevent a terminated user from logging in again.

<!-- 

t_managing_users.xml

 -->

1. Click **[!UICONTROL Adobe Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL User Management]**, then click **[!UICONTROL Manage Users]**.
1. Locate the user, then click **[!UICONTROL Terminate.]**

   On the [!UICONTROL Active Ad Hoc Analysis Sessions] page, the user who has been idle the longest displays at the top of list.

## Permissions {#concept_A7F2A7600BFF47C38D7C980E08D395B8}

<!-- 

c_permissions.xml

 -->

You set up access to report suites in the [!DNL Administration Console]. You can configure permission at the report suite level. For example, if you have multiple report suites enabled, but you do not want to grant all users access to all report suites, you can create groups with specific report suites, and then assign those users to the applicable group.

## Add a User to the All Report Access Group {#task_E821BF3B4FDB434D844A98AAB15487A9}

Steps that describe how to grant non-admin users access to all report suites.

<!-- 

t_permissions.xml

 -->

1. Log in to the **[!UICONTROL Experience Cloud]**.
1. Click **[!UICONTROL Adobe Analytics > Admin]** > **[!UICONTROL User Management]** > **[!UICONTROL Edit Groups]**.
1. Click **[!UICONTROL All Report Access]**.
1. In [!UICONTROL Available Users], select the user, then click **[!UICONTROL Add.]**
1. Click **[!UICONTROL Save Group]**.

## Create Permission Groups {#task_65A4C2E58B13475B9B2606CEB93B7CBD}

Create permission groups for non-admin users for specific report suites.

<!-- 

t_permission_groups.xml

 -->

1. Log in to the **[!UICONTROL Experience Cloud]**.
1. Click **[!UICONTROL Adobe Analytics > Admin]** > **[!UICONTROL User Management]** > **[!UICONTROL Edit Groups]**.
1. Create a permissions group for non-admin users that includes the ad hoc analysis-activated report suites that you want accessible to users.

   The report suites available to the user are displayed in the [!UICONTROL Report Cloud] menu when you create a new project.

## Set Up Proxy Policies in Java {#task_3B03F58519544025B55CF54FACF8F4F5}

Steps that describe how to set up proxy policies if you receive a server connection error.

<!-- 

t_proxy_policies.xml

 -->

Ad Hoc Analysis uses HTTP to communicate with the server. It is subject to the same proxy policies as other HTTP traffic.

1. In the [!DNL Windows Control Panel], launch the [!UICONTROL Java Control Panel].
1. On the **[!UICONTROL General]** tab, click **[!UICONTROL Network Settings]**.
1. Select **[!UICONTROL Use browser settings]**, or manually configure the proxy settings.
1. Click **[!UICONTROL OK]**, then click **[!UICONTROL OK]** on the [!UICONTROL Java Control Panel].

## How Data is Sampled {#concept_8433CFD38E0243849E92DF4F1E743AC3}

Samples of visitor data is taken to produce meaningful, accurate reporting. The date range is used as the data slice for a loaded project. A slice typically represents the current month, plus the previous two months.

<!-- 

c_overview_data_sampling.xml

 -->

For optimal processing, ad hoc analysis uses roughly 750 million as the maximum hits per slice. (Hits = page views + events.)

To arrive at the projected sample rate, the projected hits are calculated per data set, then divided by 750 million, as shown here:

* (Avg. daily hits x number of days in the slice) / 750 million

For example, if you have 10 million hits a day, with a data slice of 90 days:

* (10,000,000 x 90) / 750,000,000 = 1.2

So to keep the number of hits for this 90 day slice below 750,000,000, the data could be sampled at 1.2:1, but because samples on whole numbers are used, the sample rate is 2:1.

As another example, if you have 10 million hits a day, with a data slice for 365 days:

* (10,000,000 x 365) / 750,000,000 = 4.8

So to keep the number of hits for this 365 day slice below 750,000,000, the data could be sampled at 4.8:1. Using whole numbers, the sample rate is 5:1.
