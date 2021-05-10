---
title: Legacy Adobe Experience Cloud Debugger
description: Install the Legacy Adobe Experience Cloud Debugger. This debugger inspects tags for Analytics, Target, Advertising Cloud, Identity Service, and Launch.
exl-id: 8fd07285-f702-4770-81bd-5f856561f4a9
---
# Legacy Adobe Experience Cloud Debugger

>[!IMPORTANT]
>
>This debugging tool is no longer maintained. Adobe recommends instead using the [Adobe Experience Cloud Debugger Chrome Extension](https://docs.adobe.com/content/help/en/debugger/using/experience-cloud-debugger.html).

The [!UICONTROL Legacy Debugger] inspects tags for most Adobe Experience Cloud services. Using the debugger lets you see what data is sent to Adobe on any given page on your site. You can use this information to troubleshoot or validate your organization's implementation.

## Installing the Legacy Debugger

Create a JavaScript bookmarklet to install the debugger.

### Step 1: Copy bookmarklet code

Copy the following code to your clipboard:

```JavaScript
javascript:void(window.open("","stats_debugger","width=800,height=800,location=0,menubar=0,status=1,toolbar=0,resizable=1,scrollbars=1").document.write("<script language=\"JavaScript\" id=dbg src=\"https://www.adobetag.com/d1/digitalpulsedebugger/live/DPD.js\"></"+"script>"+"<script language=\"JavaScript\">window.focus();</script>"));
```

### Step 2: Paste bookmarklet code into a bookmark

Each browser has different ways of handling bookmarks, but the concept is the same. A bookmark is created with the desired name and the bookmarklet code as the URL.

#### Chrome

If you insist on not using the [chrome extension](https://docs.adobe.com/content/help/en/debugger/using/experience-cloud-debugger.html), the legacy debugger bookmarklet can be used instead.

1. Click the three dots in the top right, then go to Bookmarks > Bookmark Manager. You can also press `Ctrl` + `Shift` + `O` (Windows) or `Cmd` + `Shift` + `O` (Mac).
2. In the top right of the bookmark manager, click the three dots, then click 'Add new bookmark'.
3. In the Name field, label it "Adobe Experience Cloud Debugger", and paste the code snippet into the URL field.
4. Use the bookmark manager to place your new bookmarklet in the desired location.

#### Firefox

1. Click the three lines in the top right, then go to Library > Bookmarks > Show All Bookmarks. You can also press `Ctrl` + `Shift` + `B` (Windows) or `Cmd` + `Shift` + `B` (Mac).
2. Click Organize > New Bookmark.
3. In the Name field, label it "Adobe Experience Cloud Debugger", and paste the code snippet into the Location field. The Tags and Keyword fields are not required.
4. Use the library window to place your new bookmarklet in the desired location.

#### Edge

Edge does not have the ability to manually create a bookmarklet, but a bookmark URL can be edited into a bookmarklet.

1. Click the star icon on the right side of the URL field to bookmark the current page.
2. Name the bookmark "Adobe Experience Cloud Debugger", and save it in the desired location.
3. Click the star icon with lines to open the Favorites bar.
4. Right click the newly created bookmark, the select 'Edit URL'.
5. Paste the code snippet in the text field, then hit Enter.

#### Safari

Safari does not have the ability to manually create a bookmarklet, but a bookmark URL can be edited into a bookmarklet.

1. Click the Share icon in the top right, which opens a bookmark modal window.
2. Name the bookmark "Adobe Experience Cloud Debugger", and save it in the desired location.
3. Click Bookmarks > Edit Bookmarks, and locate the newly created bookmark.
4. Right click > Edit Address, then paste the code snippet into text field.

## Using the legacy debugger

Navigate to the desired page on your site, then click the bookmarklet. A pop-up window appears, showing data sent to Adobe.

>[!NOTE]
>
>Certain ad-blocking plug-ins and pop-up blockers can interfere with the loading of the debugger window. Check for blocked pop-ups in your browser, and allow them so the debugger can work correctly.

The debugger has several options available, all of which customize how data is displayed. None of these options affect data collection.

* **Displayed Experience Cloud products:** Shows or hides image requests for each respective Experience Cloud product.
* **URL Decode:** URL decodes the image request to match what is displayed in reporting. Adobe recommends leaving this box checked.
* **Auto Refresh:** Automatically refreshes the pop-up every few seconds to check for more image requests on the page. If you need to copy/paste content in the debugger, disable auto-refresh so your selection stays.
* **Friendly Format:** Toggles the display format between helpful labels and raw query strings in an image request. See [Data collection query parameters](query-parameters.md) for more information.

To save default display options for the debugger, right click the 'Adobe Debugger' link in the top right corner, then copy the link address. Edit your current debugger bookmarklet and paste the updated code snippet into the URL field.
