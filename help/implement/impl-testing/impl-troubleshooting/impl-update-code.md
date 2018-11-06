---
description: Adobe offers some best practices for updating your Analytics code.
keywords: Analytics Implementation
seo-description: Adobe offers some best practices for updating your Analytics code.
seo-title: Replacing your Analytics code
solution: Analytics
subtopic: Troubleshooting
title: Replacing your Analytics code
topic: Developer and implementation
uuid: d3ea6585-199f-4dbe-9ee8-15b204689f2f
index: y
internal: n
snippet: y
---

# Replacing your Analytics code

Adobe offers some best practices for updating your Analytics code.

Frequently, customers use the Adobe [!UICONTROL Code Manager] to replace their code with the most recent version. This practice is good to follow as long as you keep certain things in mind.

## Using the Incorrect Data Collection Server ID {#section_1726CEB1ABEC408492569B06664410C8}

Occasionally, generic [!DNL s_code.js] files that have not been generated from Adobe Code Manager are sent to those implementing the code on your site. As a result, the incorrect data collection server ID (as shown in the [!UICONTROL s.dc] variable) for the account is used. It is best to generate new code directly from the [!UICONTROL Code Manager] for a specific report suite, rather than reusing code from a different report suite. This is the best way to make sure the [!UICONTROL s.dc] variable is populated correctly.

## Plug-ins {#section_53650E52D6A54A4795F95E491E7548D1}

Some customers implement plug-ins to enhance their Adobe experience. When you replace your code, do not forget that you have plug-ins as part of that code. The code created in the [!UICONTROL Code Manager] does not have any plug-in code with it, so all plug-ins need to migrate manually to the newer code base. Make a copy of your existing code just in case something happens, and you need to revert to your previous code. 
