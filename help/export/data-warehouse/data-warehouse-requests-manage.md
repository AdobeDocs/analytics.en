---
description: The Request Manager lets you view, duplicate, and re-prioritize requests.
title: Manage Data Warehouse requests
feature: Data Warehouse
uuid: cdeb764f-56f9-43ec-9228-8ed5a2b58909
exl-id: a399d366-8402-4f4f-9b9f-14b218cd074a
---
# Manage Data Warehouse requests

{{release-limited-testing}}

>[!NOTE]
>
>If your organization does not yet have the new Data Warehouse experience, which will be available soon for all customers, use the information in [Manage Data Warehouse requests (old experience)](#manage-data-warehouse-requests-old-experience) at the bottom of this page.


You can view and manage Data Warehouse requests that you have made. Only administrators can view and manage requests made by other users in the organization where they have administrative rights.

The following sections describe activities you can perform when managing requests. 

## View requests

1. In Adobe Analytics, select [!UICONTROL **Tools**] > [!UICONTROL **Data Warehouse**].

   The Data Warehouse page displays all requests you have made. <!-- just those you have made? -->Data is shown in each column. You can [configure which columns](#configure-columns) are visible.

   <!-- add screenshot of main page -->

<!-- describe columns? -->

1. (Optional) Click the request name to view a dialog that displays the following information: <!-- Check this -->

   * When a request started processing

   * Rate Limited: Your organization has too many Data Warehouse requests running. The request is paused until other data requests complete. 

## Edit requests

Consider the following when editing requests:

* Only requests that are configured to run on a schedule can be edited.

* Not all fields associated with the request can be edited. Fields that can't be edited are dimmed.

To edit a scheduled request: 

1. In Adobe Analytics, select [!UICONTROL **Tools**] > [!UICONTROL **Data Warehouse**].

1. On the Data Warehouse page, select the request that you want to edit.

   ![Manage a request](assets/dw-manage-request.png)

1. Select [!UICONTROL **Edit**]. 

1. Edit the request as desired. Dimmed configuration options cannot be edited.

   For information about each configuration option, see [Create a Data Warehouse request](/help/export/data-warehouse/create-request/t-dw-create-request.md).

1. Select [!UICONTROL **Save changes**].

## View the history of a request

You can view the history of any Data Warehouse requests you have made. 

1. In Adobe Analytics, select [!UICONTROL **Tools**] > [!UICONTROL **Data Warehouse**].

1. On the Data Warehouse page, select the request whose history you want to view.

   ![Manage a request](assets/dw-manage-request.png)

1. Select [!UICONTROL **View history**].

   The [!UICONTROL **View Data Warehouse request**] page displays a list of individual report deliveries that are associated with the request.

   Select the **Configure column** icon ![Configure column icon](assets/configure-column-icon.png) to hide columns or show columns that aren't displayed by default.

   ![Request history page](assets/dw-request-history.png)

   The following columns are available:

   |Column |Description | 
   |---------|----------|
   | [!UICONTROL **Date created**] |The date and time that the report was created.<p>This is displayed in the time zone of the user who initiated the request.</p> | 
   | [!UICONTROL **Date started**] | The date and time that the report started.<p>This is displayed in the time zone of the user who initiated the request.</p> |
   | [!UICONTROL **Date completed**] | The date and time that the report completed.<p>This is displayed in the time zone of the user who initiated the request.</p> |
   | [!UICONTROL **Date updated**] | The date and time that the report was last updated.<p>This is displayed in the time zone of the user who initiated the request.</p> |
   | [!UICONTROL **Status**] | The status of the report delivery. Possible statuses are:<ul><li>[!UICONTROL **Created**]: The report was created but has not yet been processed.</li><li>[!UICONTROL **Pending**]: The report is waiting to be processed.</li><li>[!UICONTROL **Processing**]: The report is currently processing.</li><li>[!UICONTROL **Completed**]: The report completed and is now available.</li><li>[!UICONTROL **Scheduled**]: The report is scheduled but has not yet started.</li><li>[!UICONTROL **Canceled**]: The report was canceled by the user.</li><li>[!UICONTROL **Error - Processing**:] The report encountered an error and couldn't be processed.</li><li>[!UICONTROL **Error - Failure To Send**]: The report generated successfully but could not be delivered. Check the [configuration of your destination](/help/export/data-warehouse/create-request/dw-request-report-destinations.md), then resend the report.</li></ul>. |
   | [!UICONTROL **From**] | The start date of the overall time frame included in the report.<p>This is displayed in the time zone of the report suite.</p> |
   | [!UICONTROL **To**] | The end date of the overall time frame included in the report. <p>This is displayed in the time zone of the report suite.</p> |
   | [!UICONTROL **Legacy request ID**] | The ID that is used to identify a report in the legacy Data Warehouse interface. This ID might be needed when contacting Adobe Customer Care. |
   | [!UICONTROL **Report ID**] | The ID that is used to identify a report in the current Data Warehouse interface. This ID might be needed when contacting Adobe Customer Care. |


1. Select a report delivery, then select any of the following options:
   
   |Option |Function | 
   |---------|----------|
   | [!UICONTROL **Destination details**] | Shows the account and location details associated with the request. This is the account and location that was configured earlier, as described in [Configure a report destination for a Data Warehouse request](/help/export/data-warehouse/create-request/dw-request-report-destinations.md). | 
   | [!UICONTROL **Cancel report**] | Cancels the report. You cannot cancel reports that have a status of [!UICONTROL **Completed**] or [!UICONTROL **Canceled**]. |
   | [!UICONTROL **Rerun report**] | Runs the report again with the data as it was when it was originally sent. You can rerun a report that has any of the following statuses: [!UICONTROL **Canceled**], [!UICONTROL **Completed**], [!UICONTROL **Error - Processing**], or [!UICONTROL **Error - Failure To Send**]. |
   | [!UICONTROL **Resend report**] | Resends the report file that was previously generated. You can resend a report that has any of the following statuses: [!UICONTROL **Completed**] or [!UICONTROL **Error - Failure To Send**]. |

## Copy requests

When you copy a request, all configuration options are copied from the original request. 

1. In Adobe Analytics, select [!UICONTROL **Tools**] > [!UICONTROL **Data Warehouse**].

1. On the Data Warehouse page, select the request that you want to copy.

   ![Manage a request](assets/dw-manage-request.png)

1. Select [!UICONTROL **Copy**].

   The Copy Data Warehouse request page displays. All configuration options are copied from the original request.

1. Update any configuration options associated with the request.

   For information about each configuration option, see [Create a Data Warehouse request](/help/export/data-warehouse/create-request/t-dw-create-request.md).

1. Select [!UICONTROL **Save changes**].   

## Cancel requests

Only requests that are configured to run on a schedule can be canceled.

To cancel a scheduled request:

1. In Adobe Analytics, select [!UICONTROL **Tools**] > [!UICONTROL **Data Warehouse**].

1. On the Data Warehouse page, select the request that you want to edit.

   ![Manage a request](assets/dw-manage-request.png)

1. Select [!UICONTROL **Cancel**].

   The request will no longer run at the scheduled time.

## Configure columns

You can configure what information is displayed for each request by adding or removing columns.

1. Select the **Configure columns** icon in the upper-right of the Data Warehouse page.

   ![Configure columns](assets/dw-configure-columns.png)

   The following columns are available:

   |Available column | Description |
   |---------|----------|
   | Request name | The name of the person who created the request. | 
   | Report suite | The report suite associated with the request. | 
   | Requested by | The user who created the request. | 
   | Request date | The date the request was made. |
   | Status | The following statuses are available:<ul><li><p>**Completed**: The request ran successfully.</p></li><li><p>**Canceled**: The request was canceled by the user.</p></li><li><p>**Scheduled**: The request is configured to run on a schedule.</p></li><!-- Are there other statuses? Failed? --> |

   {style="table-layout:auto"}

1. Ensure that any columns you want to display are selected. Selected columns appear on the Data Warehouse page and display the relevant information.

## Filter and sort requests

1. Select the **Filter** icon in the left rail of the Data Warehouse page.

   ![Filter requests](assets/dw-filter.png)

1. Expand the [!UICONTROL **Report Suites**], [!UICONTROL **Owner**], or [!UICONTROL **Status**] sections, then select how you want to filter the requests.

## Search for requests

1. In the search field at the top of the Data Warehouse page, specify the request name that you want to view. 

   Requests are filtered as you type.

## Manage Data Warehouse requests (old experience)

>[!NOTE]
>
>The following information applies only if your organization does not yet have the new Data Warehouse experience, which will be available soon for all Analytics customers.


The Request Manager lets you view, duplicate, and re-prioritize requests.

In Data Warehouse, select the **[!UICONTROL Request Manager]** tab.

Working in this tab lets you

* View recent report requests by report name, segment applied, requestor, request date and status.
* Duplicate requests. Click **[!UICONTROL Duplicate]** next to the request.

  >[!NOTE]
  >
  >This action duplicates only the request, not the schedule or the delivery details.

* Search for reports by report name or by the login name of the requestor.
* Re-prioritize reports by dragging and dropping them to a new location within the queue.
* To see when a request started processing, click on a scheduled request ID and examine the pop-up that opens.

Click on a job to see individual requests for that job.

* Rate Limited: Your organization has too many Data Warehouse requests running. The request is paused until other data requests complete.