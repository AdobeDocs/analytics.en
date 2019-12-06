---
description: Many Web browsers do not start displaying the contents of a table until the browser has compiled the entire table.
keywords: Analytics Implementation
subtopic: Troubleshooting
title: Tables
topic: Developer and implementation
uuid: f72d7894-38bd-4926-bce4-0c6af7278c63
---

# Tables

Many Web browsers do not start displaying the contents of a table until the browser has compiled the entire table.

If the entire contents of the page are inside one big table, the browser must compile the entire contents of the page before anything is displayed.

Placing the call to the JavaScript library file outside table tags ensures that the call to the Analytics servers does not impact the displaying of the page content.

> [!NOTE] The file should be placed in a legal position for images and must appear between the opening <body> tag and the closing </body> tag.

