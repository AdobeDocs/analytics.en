---
description: Explains the new continuous feature release strategy for Adobe Analytics
title: Adobe Analytics feature releases
exl-id: 1e403bef-4aab-4a9a-a358-62449ce801ff
---
# Adobe Analytics feature releases

Historically, Adobe Analytics feature releases followed a fixed monthly schedule. Beginning in April 2020, Adobe Analytics moved to a continuous delivery model which allows for a more scalable, phased approach to feature deployment.

## Release strategy

[!UICONTROL Analysis Workspace] uses feature flags (also known as "toggles") to control the visibility of new features, allowing for controlled scale testing prior to full release. This release strategy includes the following phases:

* **Release to Production (RTP)**: Code is released to production, with feature visibility turned off in Analysis Workspace. **Note**: At RTP, the feature may be available in the 2.0 Analytics API.

* **Limited Testing**: A phased release begins with testing by internal Adobe users. The release is then scaled from 0% to 100% availability over the course of a couple months. Phased rollout happens at the Experience Cloud Organization level, so all entitled users in an organization receive the same experience.

* **General Availability (GA)**: The feature is available to 100% of entitled Experience Cloud organizations, and feature release is complete.

With each feature release, the timeline from RTP to GA may vary. The goal is to keep releases short, so that within 2 months of release start (RTP), a feature will be GA.

## Feature flags

Feature flags are used to control the visibility of new features during release. Adobe recommends adding app.launchdarkly.com to your firewall's [allowed list](https://docs.adobe.com/content/help/en/analytics/technotes/ip-addresses.html) for an optimal experience during release. Shortly after GA is reached, the flag is removed. 

You can view your active feature flags at any time under **Help > About Workspace > Active feature flags**.

## Benefits

Phased releases enable Adobe to better scale the software deployment process and ensure features are fully hardened before General Availability. It also allows features to be released as soon as they are available, rather than adhering to a fixed monthly release window.

## FAQs

|Question|Answer|
|---|---|
|Can I request early access to a feature?|No. Early access will not be granted.<br>If you want to test early Analytics concepts, we encourage you to try [Adobe Analytics Labs](https://docs.adobe.com/content/help/en/analytics/analyze/tech-previews/overview.html) to provide feedback on our industry-leading innovations.|
|Does this release strategy affect my access to features?|No. Once a feature has reached GA, you will have access to the feature if it is included in your Analytics package.<br>You can view details of your Analytics package under [!UICONTROL Admin] > [!UICONTROL All admin] > [!UICONTROL Company settings] > [Feature Access Levels](https://docs.adobe.com/content/help/en/analytics/admin/company-settings/feature-access-levels.html).|
