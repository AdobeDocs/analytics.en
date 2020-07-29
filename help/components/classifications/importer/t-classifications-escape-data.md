---
description: Steps that describe how to escape classification data in the classification file.
subtopic: Classifications
title: Escape classification data
topic: Admin tools
uuid: 724edcc5-4990-4f24-afbb-9aef301791a7
---

# Escape classification data

Steps that describe how to escape classification data in the classification file.

<!--Meike, please check this page against orginal. It might be missing information. -->

1. Ensure that the classification file format is v2.1.

   If v2.1 is enabled, you will see a line similar to:

   >[!NOTE]
   >
   >To specify a format of v2.1, enable **[!UICONTROL Quoted Output]** when exporting the file on the [!UICONTROL Classification Importer] page ( [!UICONTROL Browser Export] or [!UICONTROL FTP Export]).

1. Surround the field containing special characters in double quotes (`"`).

A double quote character can appear in an escaped cell by replacing it with two double quote characters (`" "`). For example:

```
My String "of data"
```

Escaped would be:

```
"My String ""of data"""
```
