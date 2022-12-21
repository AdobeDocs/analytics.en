---
title: How to set user preferences in Analysis Workspace
description: You can set general and project preferences for users, as well as a dark theme preference.
feature: Workspace Basics
role: User, Admin
exl-id: f32e3061-f396-4730-96e1-d251b00e32f0
---
# User preferences

The [!UICONTROL Components] > [!UICONTROL User preferences] page lets you manage settings for Analysis Workspace and its related components at the user-level. User preferences apply to all *new* projects or panels.

![User preferences](assets/user-preferences.png)

Here is a short video on user preferences:

>[!VIDEO](https://video.tv.adobe.com/v/332600/?quality=12)

## General preferences

General preferences apply to your Adobe Analytics experience in the browser.

| Preference | Options |
| --- | --- |
| Landing page | <ul><li>Project list (default)</li><li>Blank project</li><li>Specific project selected from a list</li></ul> |
| Tips | <ul><li>Enabled (default)</li><li>Disabled</li></ul> |

## Project preferences

Project preferences apply to new projects and new panels created in Analysis Workspace. Certain preferences can also be managed on a per-project basis under [!UICONTROL Workspace] > [!UICONTROL Project] > [!UICONTROL Project info & settings].

| Section | Preference | Options |
| --- | --- | --- |
| **Display** | | |
|  | [View density](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/build-workspace-project/view-density.html) | <ul><li>Compact</li><li>Comfortable</li><li>Expanded (default)</li></ul> |
| | [Color palette](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/build-workspace-project/color-palettes.html) | <ul><li>Adobe-provided palettes (default)</li><li>Custom-defined palettes</li></ul> |
| **Data** | | |
|  | [Report suites](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/panels/panels.html?#report-suite) | <ul><li>Most recent (default)</li><li>Specific report suite selected from a list</li></ul> |
|  | [Calendar](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/panels/panels.html?#calendar) | Select from a list of: <ul><li>Adobe-provided ranges (default is This Month)</li><li>Custom-defined ranges</li></ul> |
|  | [Panel Type](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/panels/panels.html) | <ul><li>Freeform (default)</li><li>Blank</li><li>Quick Insights</li></ul> |
|  | Number format | <ul><li>1,000.00 (default)</li><li>1.000,00</li><li>1 000,00</li></ul> |
|  | CSV separator character | <ul><li>Comma (default)</li><li>Semicolon</li><li>Colon</li><li>Pipe</li><li>Period</li><li>Space</li><li>Tab</li></ul> |
|  | Freeform table | <ul><li>Show anomalies </li><li>Show sparklines</li><li>Show annotations</li></ul> |

## Company preferences

You can update company preferences that apply to all users and projects within your organization. For information about how to access these preferences, see [Update preferences](#update-preferences). 

| Section | Preference | Options |
| --- | --- | --- |
| **Reports tab** | | |
|  | Hide Reports Tab | Hides the Reports tab for all users in your organization. |
| **Public link** <!-- Double check the names of all these settings for what they are actually called --> | | |
| | Disable public link creation | Deactivates all currently active public links and removes the "Share public link" option from the Share menu. <p>If public links are diabled and then re-enable it, all previously deactivated links are not automatically reactivated. In this case, users must manually reactivate them from the Share project dialog box.</p> |
| | Impose SSO | Deactivates all currently active public links that don't have SSO enabled and requires SSO for all future public links. <p>If this option is enabled and then later disabled, all previously deactivated links are not automatically reactivated. In this case, users must manually reactivate them from the Share project dialog box.</p> <p>This option is available only if SSO is implemented in your organization. For information about how system administrators can enable SSO for your organization, see [Set up identity and Single Sign-On](https://helpx.adobe.com/enterprise/using/set-up-identity.html){target=_blank}.</p>  |
| | Show SSO-only options | ???? <!-- this needs updating --> <p>Will display if the org is set up with SSO. If they're not, both options are removed. If they do have SSO, then the admin needs to get in touch with the system admin and confirm whether they have any kind of auto-account creation implemented in the console. Even if they don't, if they want public link access to be restricted to users in the admin console that do not have access to Adobe Analytics, … It's up to the admin whether they want this option to show up in the analytics UI. If they hide it and show it again, nothing happens.</p>  |
| | Password protection | Deactivates all currently active public links that don't have password protection enabled and requires password protection for all future public links. <p>If this option is enabled and then later disabled, all previously deactivated links are not automatically reactivated. In this case, users must manually reactivate them from the Share project dialog box.</p> |

## [!UICONTROL Dark theme]

If you prefer to have a dark background for your Adobe Analytics user interface, you can toggle to [!UICONTROL Dark theme].

1. Click the Experience Cloud user icon at the top right.

   ![dark-theme](assets/dark-theme.png)

1. Move the **[!UICONTROL Dark theme]** toggle to the right.
