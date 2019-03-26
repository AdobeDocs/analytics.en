---
description: List of reasons pathing information might not be recorded and displayed in reporting.
keywords: Analytics Implementation
seo-description: List of reasons pathing information might not be recorded and displayed in reporting.
seo-title: Reasons pathing may not be recorded
solution: Analytics
title: Reasons pathing may not be recorded
topic: Developer and implementation
uuid: 9985b7f7-75ea-4c94-97a3-520f92630989
---

# Reasons pathing may not be recorded

List of reasons pathing information might not be recorded and displayed in reporting.

* Pathing has not been enabled for that prop in that report suite. This enablement is report suite specific. 
* Data is not being passed into the correct prop. 
* Pathing has been enabled and the data is in the prop, but it hasn't shown up in the reports. Though the [!UICONTROL sprop] data may show up within 10 minutes, the pathing data will not show up until the visitor's session has ended. It ends after 30 minutes of inactivity. Analytics then takes another 10 minutes to finish the processing of the path data for final presentation in reports.

If you have checked all of these and the data is still not showing up, check with Customer Care for further debugging. 
