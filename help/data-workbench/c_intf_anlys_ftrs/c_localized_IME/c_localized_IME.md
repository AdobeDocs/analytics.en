---
description: Data workbench now supports the Input Method Editor (IME) as a secondary text entry process for international languages.
seo-description: Data workbench now supports the Input Method Editor (IME) as a secondary text entry process for international languages.
seo-title: Configure the IME for localized input
solution: Analytics
title: Configure the IME for localized input
topic: Data workbench
uuid: 8873c5d9-f816-4231-a134-ead0ef8bea47
index: y
internal: n
snippet: y
---

# Configure the IME for localized input

Data workbench now supports the Input Method Editor (IME) as a secondary text entry process for international languages.

IMEs allow you to enter international characters using a variety of methods suited for your local language. Data workbench provides an input dialog box you to use your system IME, including the [Google Input Tool for Windows](http://www.google.com/inputtools/windows/) and the [Windows IME](http://windows.microsoft.com/en-us/windows-8/input-method-editors-windows-8).

>[!NOTE]
>
>For Data Workbench 6.1 release, only the virtual Chinese keyboard called [!DNL Pinyin IME] will be supported. Inputting other languages through the IME could result in unexpected behavior.

## Use an IME {#section_5F008D75A7B24119AB6AEBC55454F927}

To use the floating IME text input feature:

1. Click **[!UICONTROL Alt + Space]** for any text input area. 
1. Enter values using your system's IME. 
1. Close the input dialog by selecting the **[!UICONTROL Enter]** key or clicking the **[!UICONTROL OK]** button.

   The dialog will disappear and the characters will then appear in the selected field.

**Update the Insight.cfg file** 
To employ the IME, you must update the [!DNL Insight.cfg] file with this setting:

```
Update Software = bool: true
```

If this setting does not exist in the configuration file, then pressing **[!UICONTROL Alt + Space]** will not engage the IME feature.

**Starting Data Workbench in another language:** To better support localized assets like a splash screen and to support multiple languages in the future, Data Workbench requires command-line arguments identifying the language to load. The default language is English, prompting the Insight.exe to look for for the "en-us.zbin" file in the [!DNL Base/Localization] folder when launched.

However, starting Data Workbench in Chinese requires you to invoke [!DNL Insight.exe] with the "-zh-cn" argument:

```
Insight.exe -zh-cn
```

(These command line arguments are not case sensitive.)

**Shortcuts for languages**. Shortcuts will be provided that link to the [!DNL Insight.exe] and automatically pass in the correct command-line argument for a desired language. 
