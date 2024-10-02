---
description: Learn about how to use the Reporting Activity Manager to diagnose and fix capacity issues during peak reporting times.
title: Cancel reporting requests in the Reporting Activity Manager
feature: Admin Tools
exl-id: 37a2fa8f-7804-4220-a508-ec66996b3801
role: Admin
---
# Cancel reporting requests in the Reporting Activity Manager

The [!UICONTROL Reporting Activity Manager] enables administrators to quickly diagnose and cancel reporting requests in order to fix reporting capacity issues during peak reporting times.

Consider the following when cancelling reporting requests:

* You can cancel specific requests, cancel all requests from a specific user, or cancel all requests related to a specific project.

  When you cancel a request, the action is recorded in the [Logs](/help/admin/admin/logs.md). The [!UICONTROL **Event Type**] column displays as [!UICONTROL **Admin Action**], and a description of the cancellation is available in the [!UICONTROL **Event**] column.

* When you cancel requests, you can also choose to restrict subsequent requests for a given time period.

  When you restrict a subsequent request, the action is recorded in the [Logs](/help/admin/admin/logs.md). The [!UICONTROL **Event Type**] column displays as [!UICONTROL **Admin Action**], and a description of the restriction is available in the [!UICONTROL **Event**] column.

* You cannot cancel a request if the [!UICONTROL **User**] column of a request shows as [!UICONTROL **Unrecognized**]. When this occurs, it means that the user is in a login company where you do not have administrative permissions.

For more information about Reporting Activity manager, including key benefits and permission requirements, see [Reporting Activity Manager overview](/help/admin/admin/reporting-activity-manager/reporting-activity-overview.md).

## Cancel specific requests

You can cancel individual requests that are consuming a large amount of reporting capacity.

1. In Adobe Analytics, go to **[!UICONTROL Admin]** > **[!UICONTROL Reporting Activity Manager]**.

1. Select the report suite where you want to cancel reporting requests. <!--double-check this step-->

   For more information about the data available on this page, see [View reporting activity in the Reporting Activity Manager](/help/admin/admin/reporting-activity-manager/reporting-activity.md).

1. Select the [!UICONTROL **Requests**] tab, then select one or more requests.

   <!-- add screenshot -->

1. Select [!UICONTROL **Cancel requests**].

   The [!UICONTROL **Cancel _x_ report requests**] dialog box displays.

1. The Cancellation message field shows the message that displays to users when their requests are cancelled. A default message is provided. You can update the default message to provide additional details.

1. (Optional) To restrict future requests for a given time period:

   1. Enable the option to [!UICONTROL **Restrict subsequent requests**]
   
      ![Restrict subsequent requests](assets/restrict-subsequent-requests.png)
   
   1. Choose from the following options:

      |Option | Function | 
      |---------|----------|
      | [!UICONTROL **User & project**] | Users associated with the selected requests will be temporarily restricted from running reporting requests for the associated projects. |
      | [!UICONTROL **User**] | Users associated with the selected requests will be temporarily restricted from making any reporting requests. | 
      | [!UICONTROL **Project**] | Projects associated with the selected requests will be temporarily restricted from all reporting requests. |
      | [!UICONTROL **Restricted for**] | Choose for how long requests will be restricted. You can choose 1 minute (default), 5 minutes, 10 minutes, 15 minutes, or 30 minutes. <!-- double-check this --><p>You cannot remove a restriction early after it is set.</p>  | 

      {style="table-layout:auto"}

1. Select [!UICONTROL **Continue with cancellation**].

   A notification is displayed in Analysis Workspace, informing users that the request has been cancelled. For more information about how this appears in Analysis Workspace, see [Experience when users access a cancelled report](#experience-when-users-access-a-cancelled-report).

## Cancel requests by user

You can cancel all requests that are associated with one or more users.

1. In Adobe Analytics, go to **[!UICONTROL Admin]** > **[!UICONTROL Reporting Activity Manager]**.

1. Select the report suite where you want to cancel reporting requests. <!--double-check this step-->

   For more information about the data available on this page, see [View reporting activity in the Reporting Activity Manager](/help/admin/admin/reporting-activity-manager/reporting-activity.md).

1. Select the [!UICONTROL **Users**] tab, then select one or more users.

   <!-- add screenshot -->

1. Select [!UICONTROL **Cancel requests**].

   The [!UICONTROL **Cancel _x_ report requests from x users**] dialog box displays.

1. The Cancellation message field shows the message that displays to users when their requests are cancelled. A default message is provided. You can update the default message to provide additional details.

1. (Optional) To restrict future requests for a given time period:

   1. Enable the option to [!UICONTROL **Restrict subsequent requests**].
   
      ![Restrict subsequent requests by user](assets/restrict-subsequent-requests-user.png)
   
   1. Choose from the following options:

      |Option | Function | 
      |---------|----------|
      | [!UICONTROL **User & project**] | Selected users will be temporarily restricted from making any reporting requests for the associated projects. |
      | [!UICONTROL **User**] | Selected users will be temporarily restricted from making any reporting requests. | 
      | [!UICONTROL **Project**] | Projects associated with the selected users will be restricted from any reporting requests made by any user. |
      | [!UICONTROL **Restricted for**] | Choose for how long requests will be restricted. You can choose 1 minute (default), 5 minutes, 10 minutes, 15 minutes, or 30 minutes. <!--double-check this--> <p>You cannot remove a restriction early after it is set.</p>  | 

      {style="table-layout:auto"}

1. Select [!UICONTROL **Continue with cancellation**].

   A notification is displayed in Analysis Workspace, informing users that the request has been cancelled. For more information about how this appears in Analysis Workspace, see [Experience when users access a cancelled report](#experience-when-users-access-a-cancelled-report).

## Cancel requests by project

You can cancel all requests that are associated with one or more projects.

1. In Adobe Analytics, go to **[!UICONTROL Admin]** > **[!UICONTROL Reporting Activity Manager]**.

1. Select the report suite where you want to cancel reporting requests. <!--double-check this step-->

   For more information about the data available on this page, see [View reporting activity in the Reporting Activity Manager](/help/admin/admin/reporting-activity-manager/reporting-activity.md).

1. Select the [!UICONTROL **Projects**] tab, then select one or more projects.

   <!-- add screenshot -->

1. Select [!UICONTROL **Cancel requests**].

   The [!UICONTROL **Cancel _x_ report requests from x projects**] dialog box displays.

1. The Cancellation message field shows the message that displays to users when their requests are cancelled. A default message is provided. You can update the default message to provide additional details.

1. (Optional) To restrict future requests for a given time period:

   1. Enable the option to [!UICONTROL **Restrict subsequent requests**].
   
      ![Restrict subsequent requests by project](assets/restrict-subsequent-requests-project.png)
   
   1. Choose from the following options:

      |Option | Function | 
      |---------|----------|
      | [!UICONTROL **User & project**] | Selected projects will be temporarily restricted from any reporting requests made by the associated users. |
      | [!UICONTROL **User**] | Users associated with the selected projects will be restricted from making any reporting requests. | 
      | [!UICONTROL **Project**] | Selected projects will be temporarily restricted from any reporting requests made by any user. |
      | [!UICONTROL **Restricted for**] | Choose for how long requests will be restricted. You can choose 1 minute (default), 5 minutes, 10 minutes, 15 minutes, or 30 minutes. <!--double-check this--> <p>You cannot remove a restriction early after it is set.</p>  | 

      {style="table-layout:auto"}

1. Select [!UICONTROL **Continue with cancellation**].

   A notification is displayed in Analysis Workspace, informing users that the request has been cancelled. For more information about how this appears in Analysis Workspace, see [Experience when users access a cancelled report](#experience-when-users-access-a-cancelled-report).

## Cancel requests by application

You can cancel all requests that are associated with one or more applications. When canceling requests associated with an application, you can choose to further restrict requests associated with that application for a given time period.

Applications include the following: 

* Analysis Workspace UI
* Workspace scheduled projects
* Report Builder
* Builder UIs: Segment, Calculated Metrics, Annotations, Audiences, etc.
* API calls from 1.4 or 2.0 API
* Alerts
* Share with anyone links
* Any other application that queries the Analytics reporting engine

To cancel requests by application:

1. In Adobe Analytics, go to **[!UICONTROL Admin]** > **[!UICONTROL Reporting Activity Manager]**.

1. Select the connection where you want to cancel reporting requests. <!--double-check this step-->

   For more information about the data available on this page, see [View reporting activity in the Reporting Activity Manager](/help/admin/admin/reporting-activity-manager/reporting-activity.md).

1. Select the [!UICONTROL **Applications**] tab, then select one or more applications.

   <!-- add screenshot -->

1. Select [!UICONTROL **Cancel requests**].

   The [!UICONTROL **Cancel _x_ report requests from x projects**] dialog box displays.

1. The Cancellation message field shows the message that displays to users when their requests are cancelled. A default message is provided. You can update the default message to provide additional details.

1. (Optional) To restrict future requests for a given time period:

   1. Enable the option to [!UICONTROL **Restrict subsequent requests**]
   
      ![Restrict subsequent requests by application](assets/restrict-subsequent-requests-application.png)
   
   1. Choose from the following options:

      |Option | Function | 
      |---------|----------|
      | [!UICONTROL **User & project**] | Selected applications will be temporarily restricted from any reporting requests made by the associated users and projects.<p>This is the least restrictive option.</p> |
      | [!UICONTROL **User**] | Users associated with the selected applications will be restricted from making any reporting requests. | 
      | [!UICONTROL **Project**] | Projects associated with the selected applications will be restricted from any reporting requests made by any user. |
      | [!UICONTROL **Restricted for**] | Choose for how long requests will be restricted. You can choose 1 minute (default), 5 minutes, 10 minutes, 15 minutes, or 30 minutes. <!--double-check this--> <p>You cannot remove a restriction early after it is set.</p>  | 

      {style="table-layout:auto"}

1. Select [!UICONTROL **Continue with cancellation**].

   A notification is displayed in the application (such as in Analysis Workspace), informing users that the request has been cancelled. For more information about how this appears in Analysis Workspace, see [Experience when users access a cancelled report](#experience-when-users-access-a-cancelled-report).

## Experience when users access a cancelled report

In Analysis Workspace, users see the following messages when they attempt to access a report or visualization that is affected by a cancellation:

### Message on the project

When users attempt to access a project that is affected by a cancellation, they see a message informing them that the report is temporarily restricted:

![Project cancellation message](assets/workspace-canceled-report.png)

### Message on the visualization

When users attempt to access a visualization that is affected by a cancellation, they see a message informing them that data processing for the report is temporarily restricted:

![Visualization cancellation message](assets/workspace-cancelled-visualization.png)
