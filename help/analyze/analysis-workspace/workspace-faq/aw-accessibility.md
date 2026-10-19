---
description: Learn about the accessibility support features in Analysis Workspace.
title: Accessibility In Analysis Workspace
feature: Workspace Basics
role: User, Admin
exl-id: 2bacbee8-097c-4fc5-8be4-7e4f284db08c
TQID: 'https://experienceleague.adobe.com/qT9P5156x2J9nRupDY-fgf6ArTnhIPvSg88YyKfQ9n4'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
    internal-label: Analysis Workspace
  - id: f73667dc-d296-4875-8975-ac3fdc3adc42
    internal-label: Dashboards
  - id: a421fb65-2c82-457a-921c-28c46b697a39
    internal-label: Analytics basics
subfeature_v2:
  - id: a544b409-2610-410d-a842-474ac1d0d54e
    internal-label: Segment Builder
  - id: b0a1f9d5-5795-42a3-a6d0-bd0e2748fd06
    internal-label: Components
  - id: dcae653e-62c6-4cc8-84e6-ee110b848296
    internal-label: Visualizations
  - id: eb853e43-1634-4181-adf2-a44d64395ec3
    internal-label: Hotkeys
  - id: c457b289-f974-4a67-a5b6-dec3ffa77675
    internal-label: Workspace basics
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: cc72dcf1-72e1-48cc-b434-e7c27d62d67c
    internal-label: Accessibility
---
# Accessibility in Analysis Workspace

Learn about accessibility support in [!UICONTROL Analysis Workspace], the premier analysis tool for Customer Journey Analytics. 

Accessibility refers to making products usable for people with visual, auditory, cognitive, motor, and other disabilities. Examples of accessibility features for software products include: 

* screen reader support, 
* text equivalents for graphics, 
* keyboard shortcuts, 
* change of display colors to high contrast, 
* and more. 

[!UICONTROL Analysis Workspace] provides some tools that make it accessible to use, including:

## Keyboard navigation

Navigation in [!UICONTROL Analysis Workspace] works top down, and from left to right. The following navigational elements facilitate accessibility:

* The **[!UICONTROL Tab]** key enables landmark shortcuts, moving between larger sections within Workspace. In the left panel, **[!UICONTROL Tab]** also enables you to move from one draggable option to the next.
* The ◀︎ and ▶︎ move between individual elements after the **[!UICONTROL Tab]** key has highlighted an element. 
* The **[!UICONTROL F6]** key navigates to the first panel in the project and moves between the visualizations within that panel. Then, it moves to the next panel in the project and repeats. 
* Focus indicators are applied so that sighted keyboard users have a clear indication of which UI element currently has focus. The indicator is a blue border for the panel that has focus. And gray background for the recent selected functionality and the selection within the functionality. In the example, [!UICONTROL Components] and the Page dimension have been selected recently.

    ![Freeform table showing a focus ndicator of a blue border around the Freeform table.](assets/focus-indicator.png)

### Keyboard navigation for the menu bar 

1. Tab until you have reached the menu bar.
1. Use the arrow keys to navigate between menus and menu items.
1. Press **[!UICONTROL Enter]** to open a menu or select a menu item.
1. Use **[!UICONTROL Esc]** to close a menu.

### Keyboard navigation for drag & drop interactions 

[!UICONTROL Analysis Workspace] is a drag and drop user interface. However, users can add components using the keyboard instead:

1. Tab to a component in the left panel.
1. Press **[!UICONTROL Enter]** to select.
1. Use arrow keys to navigate to the area where you want to drop the component.
1. Press **[!UICONTROL Enter]** to place the component.

### Keyboard navigation for table columns {#table-columns}

You can resize and rearrange table columns with the keyboard. The same keys work on macOS and Windows.

#### Resize columns {#resize-columns}

You can resize columns in freeform tables and cohort tables using the column resize separator, which is the boundary between two column headers.

1. Press **[!UICONTROL Tab]** until a column resize separator has focus.

   Instructions for resizing display while the separator has focus. Screen readers announce these instructions and the current width of the column as a percentage.

1. Use the following keys to resize the column. A column can't be resized beyond its minimum or maximum width.

   | Key | Action |
   | --- | --- |
   | **[!UICONTROL Left Arrow]** | Narrow the column to the left of the separator by 10 pixels. |
   | **[!UICONTROL Right Arrow]** | Widen the column to the left of the separator by 10 pixels. |
   | **[!UICONTROL Enter]** | Reset the column width. |

#### Rearrange columns {#rearrange-columns}

In a freeform table that you can edit, you can move a column left or right using the **[!UICONTROL Rearrange]** menu in the column header.

1. Press **[!UICONTROL Tab]** until the **[!UICONTROL Rearrange]** button in the column header has focus.
1. Press **[!UICONTROL Enter]**, **[!UICONTROL Space]**, or **[!UICONTROL Down Arrow]** to open the menu.
1. Select **[!UICONTROL Move column left]** or **[!UICONTROL Move column right]**.

   To close the menu without moving the column, press **[!UICONTROL Esc]**. Focus returns to the **[!UICONTROL Rearrange]** button.

   After you move a column, screen readers announce the column name and its new position within its group.

Consider the following when rearranging columns with the keyboard:

* A column moves only within its group of sibling columns, which are the columns at the same level under the same parent header. You can't use the keyboard to move a column into a different group or to copy a column.
* When you move a parent header, its nested columns and filters move with it.
* **[!UICONTROL Move column left]** is disabled for the first column in a group. **[!UICONTROL Move column right]** is disabled for the last column in a group.
* The **[!UICONTROL Rearrange]** button is available only for columns that you can also rearrange by dragging. It isn't available for:
  * Read-only tables or tables with interactions disabled.
  * Date columns in cohort tables.

### Keyboard shortcuts (hotkeys) 

[!UICONTROL Analysis Workspace] offers a rich set of [keyboard shortcuts (hotkeys)](/help/analyze/analysis-workspace/build-workspace-project/fa-shortcut-keys.md) for a more seamless workflow. 

## Support for screen readers and screen magnifiers

A screen reader reads text that appears on the computer screen. It also reads non-textual information, such as button labels or image descriptions in the application.  

## Color palettes & contrast  

[!UICONTROL Analysis Workspace] strives for WCAG 2.1 AA conformance, including requirements for color contrast. 

In addition, users can set their own preferred color palette for a project under **[!UICONTROL Project]** > **[!UICONTROL Project settings]** > [Project color palette](/help/analyze/analysis-workspace/build-workspace-project/color-palettes.md). 

## Required validation

When building a component or a visualization or a panel, required fields are validated when you save. If a required field does not pass validation, it is outlined in red with an error icon. A written description explains what needs to be fixed.  

![Segment Builder and error validation indicator.](assets/error-validation.png)

## Support for operating system accessibility features  

Analysis Workspace supports built-in Windows and macOS accessibility features like high-contrast mode, sticky keys, and slow keys/filter keys. It also provides information about the user interface to the operating system to enable interaction with assistive technologies, including screen readers such as VoiceOver for macOS and NVDA on Windows.


<!--

# Accessibility in Analysis Workspace

Learn about accessibility support in [!UICONTROL Analysis Workspace], the premier analysis tool for Adobe Analytics. 

Accessibility refers to making products usable for people with visual, auditory, cognitive, motor, and other disabilities. Examples of accessibility features for software products include screen reader support, text equivalents for graphics, keyboard shortcuts, change of display colors to high contrast, and so on. 

[!UICONTROL Analysis Workspace] provides some tools that make it accessible to use, including:

## Navigate [!UICONTROL Workspace] using the keyboard

Navigation in [!UICONTROL Analysis Workspace] works top > down, and left > right. The following navigational elements facilitate accessibility:

* The `Tab` key enables landmark shortcuts, moving between larger sections within Workspace. In the left rail, `Tab` also enables you to move from one draggable option to the next.
* The `left/right arrows` move between individual elements after `Tab` has highlighted it. 
* The `F6` navigates to the first panel in the project and  moves between the visualizations within that panel. Then, it moves to the next panel in the project and repeats. 
* We apply focus indicators so that sighted keyboard users have a clear indication of which UI element currently has focus. The indicator is a blue border around the selected element.

    ![Focus Indicator](assets/focus-indicator.png)

### Keyboard navigation for the menu bar 

1. Tab until you have reached the menu bar.
1. Use left/right arrow keys to navigate to the menu you want.
1. Press `Enter` to select the menu and show its options.
1. Use up/down arrow keys to navigate to the menu option you want.
1. Press `Enter` to select the option.

### Keyboard navigation for drag & drop interactions 

[!UICONTROL Analysis Workspace] is a drag & drop user interface. However, users can add components using the keyboard instead:

1. Tab to a component in the left rail.
1. Press `Enter` to select.
1. Use arrow keys to navigate to the area where you want to drop the component.
1. Press `Enter` to place the component.

### Keyboard shortcuts (hotkeys) 

[!UICONTROL Analysis Workspace] offers a rich set of [keyboard shortcuts](/help/analyze/analysis-workspace/build-workspace-project/fa-shortcut-keys.md) for a more seamless workflow. Some common shortcuts for navigation, analysis creation, and insight democratization are listed below. 

#### Navigation

| Shortcut | Action |
| --- | --- |
| `[Alt + Shift + 1 / 2 / 3]` | Jump to different rails: [!UICONTROL Panels], [!UICONTROL Visualizations], or [!UICONTROL Components] |
| `[Alt + Left / Right]` | Navigate between panels |
| `[Alt + M]` | Collapse/expand all panels |
| `[Alt + Ctrl + M]` | Collapse/expand active panel |
| `[Ctrl + /]` | Search left rail |

#### Analysis creation

| Shortcut | Action |
| --- | --- |
| `[Alt + 1]` | New freeform table |
| `[Ctrl + Shift + C]` | New calculated metric |
| `[Ctrl + Shift + D]` | New date range |
| `[Ctrl + Shift + E]` | New segment |
| `[Ctrl + Z]` | Undo |
| `[Component drag + Shift]` | Create a drop-down filter |

#### Democratization

| Shortcut | Action |
| --- | --- |
| `[Ctrl + S]` | Save |
| `[Ctrl + Shift + G]` | Curate |
| `[Ctrl + G]` | Share |
| `[Alt + Shift + S]` | Schedule |
| `[Alt + L]` | Get link to project |
| `[Ctrl + Shift + B]` | Download PDF |

## Support for screen readers and screen magnifiers

A screen reader reads text that appears on the computer screen. It also reads non-textual information, such as button labels or image descriptions in the application, provided in accessibility tags or attributes.  

## Color palettes & contrast  

[!UICONTROL Analysis Workspace] strives for WCAG 2.1 AA conformance, including requirements for color contrast. 

In addition, users can set their own preferred color palette for a project under **[!UICONTROL Project]** > **[!UICONTROL Project settings]** > [Project color palette](/help/analyze/analysis-workspace/build-workspace-project/color-palettes.md). 

## Required field validation in component builders 

When building a component, required fields are validated when you save. If a required field does not pass validation, it will be outlined in red with an error icon. A written description appears of the issue that needs to be fixed.  

Once a component is fully validated, pressing `Save` closes the builder. 

![Error validation](assets/error-validation.png)

## Support for operating system accessibility features  

Analysis Workspace supports built-in MS Windows and macOS accessibility features like high-contrast mode, sticky keys, and slow keys/filter keys. It also provides information about the user interface to the operating system to enable interaction with assistive technologies, including screen readers such as VoiceOver for macOS and NVDA on Windows.

-->