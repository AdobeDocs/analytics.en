---
description: Implementation process steps.
keywords: Analytics Implementation
title: Implementation acceptance
topic: Developer and implementation
uuid: 6f7ec56e-9e4f-4dc8-b534-92b1580b5b47
---

# Implementation acceptance

Implementation process steps.

The following steps outline the implementation process.

1. The Adobe Consultant gathers report requirements and creates a data collection plan based on those requirements.

   The data collection plan includes variable definitions, required VISTA rules and custom JavaScript, data correlation, and all settings for each report suite. The client completes the Implementation Questionnaire.
1. Technical resources on the client-side implement the code, site-specific JavaScript, and server-side variables.
1. The Adobe Consultant addresses technical issues during the implementation and assists in devising solutions as required.
1. Technical resources on the client-side unit test the implementation.

   Testers log in to [!DNL Analytics] and verifying all variables ( *`page name`*, *`channel`*, *`server`*, *`events`*, *`campaign`*, econversion variables, custom traffic variables, *`products`*, and all other variables).
1. The client notifies Adobe that the implementation is complete.

   The client provides a validation sample (data sample) to the Adobe Consultant to validate data accuracy. (VISTA-generated report suites are validated by comparing appropriate metrics. A client-Adobe agreement of the metrics to be validated for such report suites shall be made in advance, at the time of the VISTA rule creation.) 
1. The client faxes (or signs online) an Implementation Acceptance and Agreement for the appropriate site(s).
1. After the acceptance has been received, the Adobe Consultant enables the Adobe Best Practices - Implementation Verification certification within the interface.
1. Optionally, the client can contract with Adobe for monitoring services for key pages of the implemented site (generally, these are the primary templates, home page, and critical entry pages).

   This monitoring software is described in a separate document, but tracks pages by loading and executing the page, then comparing the image request to a baseline stored in a database. If any differences are detected, the software notifies specified Adobe (AM/IE) and client personnel via email.

The following items help to ensure a successful implementation:

* A best practices document, which is client-facing and explains the processes in detail.
* The validation document that the customer uses to unit test the implementation.
* An Implementation Acceptance and Agreement form for the client to sign.
* A monitoring application that continuously validates the tags.
* A relationship with Accenture to help with implementation testing.
* Utilities and/or tools for comparison of page views and/or orders. Those comparisons can get fairly difficult.
* A method or process to quickly obtain the debug log for a given day, by report suite ID.

