---
description: The Server Files Manager enables you to remotely administer and manage Data Workbench server computers from any authorized Data Workbench by providing access to all of the directories and files in the product’s installation directory, including configuration and look-up files.
seo-description: The Server Files Manager enables you to remotely administer and manage Data Workbench server computers from any authorized Data Workbench by providing access to all of the directories and files in the product’s installation directory, including configuration and look-up files.
seo-title: Server Files Manager
solution: Analytics
title: Server Files Manager
topic: Data workbench
uuid: d8b6fefd-cbcf-417d-a236-a7357d1361c0
index: y
internal: n
snippet: y
---

# Server Files Manager

The Server Files Manager enables you to remotely administer and manage Data Workbench server computers from any authorized Data Workbench by providing access to all of the directories and files in the product’s installation directory, including configuration and look-up files.

You can access the [!UICONTROL Server Files Manager] using the [!UICONTROL Admin] menu as well as by right-clicking the node of the Data Workbench server computer in the [!UICONTROL Servers Manager] and clicking **[!UICONTROL Server Files]**.

![](assets/vis_FileManager.png)

>[!NOTE]
>
>You can create new server files managers that display selected directories. See [Creating New Server Files Managers](../../data-workbench-client/c-intf-anlys-ftrs/c-cstm-prof-files-mgrs/c-new-svr-files-mgrs.md#concept_6E8F63273109443699A8F61B1A2EA816).

The left column of [!UICONTROL Server Files Manager] lists file and folder names. The check marks in the center and right columns indicate where in the file structure these directories and files reside.

If a file resides in the product’s installation directory, the *server name* (for example, Data Workbench server) column contains a check mark. If a file resides on the Data Workbench user’s computer in the *Data Workbench installation directory*\Temp directory, the [!UICONTROL Temp] column contains a check mark. The color of the check marks indicates whether the files that reside in different locations were modified at the same time.

* A red check mark in the server name column indicates that the folder or file resides on the Data Workbench server computer. 
* A red check mark in the [!UICONTROL Temp] column indicates that the local copy of the file or folder has the same Modified date and time as the file or folder on the Data Workbench server computer. 
* A white check mark in the [!UICONTROL Temp] column indicates that the file or folder in the *Data Workbench installation directory*\Temp directory has a different Modified date and time than the file or folder on the Data Workbench server computer.

The following graphic shows the [!UICONTROL Server Files Manager] with both red and white check marks:

![](assets/vis_FileManager_RedWhiteChecks.png)

**To manage directories and files using the [!UICONTROL Server Files Manager]**

You can use the [!UICONTROL Server Files Manager] to manipulate directories and files on a Data Workbench server computer.

The following table lists the tasks that can be completed using the [!UICONTROL Server Files Manager]:

<table id="table_D217AE5A878542EC8B604812A61819C3"> 
 <thead> 
  <tr valign="top"> 
   <th colname="col1" class="entry"> To perform this task... </th> 
   <th colname="col2" class="entry"> Do this... </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr valign="top"> 
   <td colname="col1"> <p>To see the files within any directory </p> </td> 
   <td colname="col2"> <p>Click the directory name to view its contents. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>To hide the content of a directory </p> </td> 
   <td colname="col2"> <p>Click the directory name. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>To see details about a directory </p> </td> 
   <td colname="col2"> <p>Right-click the cell next to the directory in either the server name or <span class="wintitle"> Temp</span> column. You see the following information: </p> 
    <ul id="ul_2DA5C8D0E95F4BCC8F7E25D05F00EB02"> 
     <li id="li_3FDECC14D62543B183C3509C338DF432">Path. The path of the directory. </li> 
     <li id="li_9CF3989FD9E2427995F070E043FAD02C">Dir. The name of the directory. </li> 
     <li id="li_68AAA11907404D0BBF407ECD7CA2E467">From. The location of the directory, Remote or Temp. </li> 
     <li id="li_CB4AEEC89E424868B758465EC0B701B5">Date (Temp column only). Creation date or the date of the last revision to the local copy. </li> 
    </ul> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>To see details about a file </p> </td> 
   <td colname="col2"> <p>Right-click the check mark next to the file in either the server name or <span class="wintitle"> Temp</span> column. You see the following information: </p> <p> 
     <ul id="ul_C4E6CB86D1774D739B5ECF48AF8DB628"> 
      <li id="li_7A6D39CF8C064FDDAB87F8D4E50FA832">Path. The path of the file. </li> 
      <li id="li_9C735B6F0A2541F1992B845359C3685A">File. The name of the file. </li> 
      <li id="li_3EB903E4F4C44A6093732C588F0125EF">From. The location of the directory, Remote or Temp. </li> 
      <li id="li_C1FED4F98F854D5892DBAD9F9E1D47B8">Date. Date of the last revision to the file. </li> 
      <li id="li_7477C727C62F4406BB2026063E41F2AE">Size. The size of the file. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>To download a directory to your local computer </p> </td> 
   <td colname="col2"> <p>Right-click the check mark in the <i>server name</i> column for this directory and click <span class="uicontrol"> Make Directory Local</span>. A check mark for the directory appears in the <span class="wintitle"> Temp</span> column. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>To download a file to your local computer </p> </td> 
   <td colname="col2"> <p>Right-click the check mark in the <i>server name</i> column for this file and click <span class="uicontrol"> Make Local</span>. A check mark for the file appears in the <span class="wintitle"> Temp</span> column. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>To download the last portion of a log file to your local computer </p> </td> 
   <td colname="col2"> <p>To avoid having to download an entire log file (especially when you know that the error message is close to the end of the file), right-click the check mark in the server name column for the file, click <span class="uicontrol"> Tail</span>, and select the size of the portion you want to download. A check mark for the file appears in the <span class="wintitle"> Temp</span> column. The local file contains only the amount of data that you specified, starting from the end of the file. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>To open a directory </p> </td> 
   <td colname="col2"> <p>Right-click the check mark for the directory in the <span class="wintitle"> Temp</span> column and click <span class="uicontrol"> Open</span> &gt; <span class="uicontrol"> folder</span>. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>To open a file </p> </td> 
   <td colname="col2"> <p>Right-click the check mark for the file in the <span class="wintitle"> Temp</span> column, click <span class="uicontrol"> Open</span>, then click in <span class="uicontrol"> Data Workbench</span>, <span class="uicontrol"> in Notepad</span>, or <span class="uicontrol"> folder</span>. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>Save a local copy of a directory to the Data Workbench server </p> </td> 
   <td colname="col2"> <p>Right-click the check mark for the directory in the <span class="wintitle"> Temp</span> column and click <span class="uicontrol"> Save Directory to</span> &gt; <i>&lt;<span class="uicontrol"> profile name</span>&gt;</i>. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>Save a local copy of a file to the Data Workbench server </p> </td> 
   <td colname="col2"> <p>Right-click the check mark for the file in the <span class="wintitle"> Temp</span> column and click <span class="uicontrol"> Save to</span> &gt; <i>&lt;<span class="uicontrol"> profile name</span>&gt;</i>. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>Remove a local copy of a directory or file </p> </td> 
   <td colname="col2"> <p>Right-click the check mark for the directory or file in the <span class="wintitle"> Temp</span> column and click <span class="uicontrol"> Remove</span>. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>Copy and paste a file as an email attachment in Microsoft Outlook </p> </td> 
   <td colname="col2"> <p>Right-click the check mark for the file in the <span class="wintitle"> Temp</span> column and click <span class="uicontrol"> Copy</span>. In the body of your email, press Ctrl+v to attach the file. </p> </td> 
  </tr> 
 </tbody> 
</table>

