---
description: If an error occurs, an error is reported in the Job Status column.
keywords: Data Feed;job;troubleshooting;error;ftp;chdir;connect;login;put
solution: Analytics
title: Troubleshoot jobs
uuid: 8fbb914e-03db-434e-b4d3-8594144ff2b7
---

# Troubleshoot jobs

If you are having issues getting a data feed to appear on your FTP site, use this page to understand why.

## Error codes

If an error occurs, an error is reported in the Job Status column.

### FTP chdir Error

The feed cannot navigate or write to the folder specified. Make sure that the destination folder exists on the FTP site, and that the credentials provided have the correct read/write permissions to that folder.

### FTP Connect Error

The feed cannot connect to the FTP destination. Make sure that the FTP destination is correct and valid.

### FTP Error

A generic error where the feed ultimately cannot write the file to the FTP site. This error can potentially come from the FTP server's disk being full or quota exceeded. The error can also originate from a network or destination server failure.

### FTP Login Error

The feed cannot log in using the credentials provided. Make sure that the FTP username and password are correct.

### FTP Put Error

The feed cannot write files to the FTP site. Make sure that the FTP login has the correct permissions to both read and write data on your FTP site. This error can also potentially come from a full disk or exceeded disk quota on the FTP server.

## Steps to troubleshoot

Log in to your FTP site and upload any file to it. In most cases, you can determine the point of failure using these steps.

1. Log in to your FTP site using File Explorer (Windows) or Finder (Mac). Make sure you use FTP protocol (`ftp://`). If you are unable to reach the FTP site, you can work with the owner of the FTP site to determine the correct destination.
  
   ![File Explorer](assets/file_explorer.png)

2. A popup asking for a username and password appears. Enter your authentication credentials. If the credentials are accepted, the window shows the current contents on the FTP site. If the credentials are not accepted, you can work with the FTP owner to make sure that the username and password are correct.
3. Upload a file to the FTP site by dragging it into the authenticated window. Any image or text document is adequate. If you get an error attempting to place a file onto the FTP site, work with the FTP owner to verify there is enough disk space and that the username has write permissions to the FTP site.
4. Once you have confirmed that the file is on the FTP site, you can delete the file uploaded in the previous step.
5. If all of the above steps work and you still get an FTP error, have a customer support delegate contact Customer Care.
