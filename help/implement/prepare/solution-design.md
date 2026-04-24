---
title: Create a solution design document
description: Learn what a solution design document is, and how you can use it in your organization.
feature: Implementation Basics
exl-id: 0b5c5ddd-5f53-4790-a649-1381135dacda
role: Admin, Developer, Leader
TQID: https://experienceleague.adobe.com/OLSxdEz9--Xe8bCRH6-TimsPloUUdesg4-wrBNL3uPU
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
subfeature_v2:
  - id: f1f1a2d4-0976-4881-b091-c2bb8de7ffac
    internal-label: Events
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
  - id: f8a45b24-4be7-4f1b-909b-60d06b483a20
    internal-label: Leader
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: d3cdead0-685a-4489-9250-4bb709942f66
    internal-label: Data collection
---
# Create a solution design document

A solution design document (also known as a solution design reference or business requirements document) is in essence the blueprint of your analytics implementation. It defines criteria identified by stakeholders throughout your organization, and translates them to variables within Adobe Analytics. Without one, organizations have a difficult time coordinating reporting needs and tend to miss collecting important data.

## Prerequisites

[Validate your Analytics implementation and publish to production](../launch/validate-publish-prod.md) - While not directly required, Adobe recommends having a basic implementation in place so critical data is collected while additional business requirements are established and implemented.

## Ownership and location of the design document

* **Determine who in your organization will be responsible for maintaining the solution design document.** This role can either be an individual or a team. Ensure that maintaining the solution design is preserved even through role changes or organization restructures. It is a living document and must be properly maintained.
* **Determine where your solution document will reside.** There is no single best place for solution design documents to reside, but they typically live in a widely accessible internal location. Examples include a shared spreadsheet or a collaborative workspace like SharePoint or an internal wiki. It does not need to be editable to everyone, but it is beneficial for those who can access reporting to at least be able to view it.

## Define business requirements

When determining what data to collect, it is easy to say "everything", however that can quickly become unwieldy to manage, and can even provide less value than collecting more concise amounts of data.

1. **Determine your Key Performance Indicators.** What do you ultimately want visitors to do? The answer to this question varies by industry and vertical, and can be multiple things. Examples include purchases, registrations, or ad clicks.
1. **Figure out the most important data to collect.** Ask business questions that you want specific answers to. Answers to these questions would provide insight on how to improve your KPI's.
1. **Take those questions and determine what your tracking needs are.** Group them into dimensions and metrics.
   * Dimensions are variables that contain text. Examples would include internal search term, product category, or the name of an area a visitor clicked.
   * Metrics are specific events that you want a visitor to do - when they perform an action you want, the number goes up by one. Examples would include submitting an order, subscribing to a newsletter, or submitting a survey response.
1. **Map dimensions and metrics into a page or spreadsheet.** This page or table ultimately becomes your solution design document. Some helpful columns or bullet points to include:
   * Implementation status: Planned, active, inactive, issues, etc. This would inform the viewers of the document the variable's status, if it's been implemented, or if there are issues with data collection.
   * Variable name: For example, "Internal search terms". This value would be what analysts see when working within Analytics.
   * Analytics variable mapped to: Which default or custom Analytics variable you choose to assign values to. Dimensions typically fall under eVars, while metrics fall under events.
   * Logic: A description of how the variable is set, and what determines its value. For example, "Only set on internal search pages. Takes the value of the q query string parameter."
   * Any other notes that you would like to include pertaining to the variable

## Additional resources

Defining a solution design document is a fairly complex project, especially for organizations who have not created one before. If additional assistance is desired, Adobe provides specialized consulting to help get your organization up and running with Adobe Analytics. Contact your Adobe Account Team if you would like to enlist Adobe's professional services. A [Technical pre-implementation questionnaire](assets/technical-pre-implementation-questionnaire.pdf) can be filled out so Adobe knows exactly how to help based on your organization's needs.

There are also several Adobe partners who specialize in helping with the creation of a solution design document, as well as implementing Adobe Analytics on your site.

## Next Steps

Implement the variables in your solution design document.

[Create a data layer](data-layer.md): Translate variables in your design document to JavaScript variables on your site.
