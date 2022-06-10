---
description: Connecting without a password to FTP accounts is only possible using both an SFTP connection and an alternative authentication method. This involves a set of two files (one to reside on the FTP account and the other to reside on your computer) called a public and private key combination.
keywords: ftp;sftp
title: Connect to Adobe via SFTP without a password
feature: FTP Export
exl-id: 7ff9511c-50a2-466f-b5af-6bbd59941ce5
---
# Connect to Adobe via SFTP without a password

Connecting without a password to FTP accounts is only possible using both an SFTP connection and an alternative authentication method. This involves a set of two files (one to reside on the FTP account and the other to reside on your computer) called a public and private key combination.

 This is not any less secure than password authentication. It is another form of authenticating that does not require the user to type in a password each time. When used correctly, these files let that particular computer log in without having to specify a password. This needs to be set up on a computer-by-computer basis. All other connections that don't use these key files still need to specify a password.

An SFTP (Secure File Transfer Protocol) is required by some clients for transmitting sensitive data. An SFTP connection is more secure than a regular FTP connection because it allows encrypted data communication. By default, all Adobe FTP accounts are SFTP ready. An SFTP connection can be opened with a valid username and password by using an SFTP client that connects on port 22 (normal FTP connections that are non-secure use port 21).

When using SFTP, it is possible, under specific conditions, to use private keys to connect to the account without a password. This method lets your computer use key files for authentication instead of usual password authentication. This means that only the computer that holds the private key may connect without a password. All other computers/users still need to use password authentication (unless private keys have been set up on these other computers as well).

**To set up and use private keys for password-less authentication**

1. FTP account created (Adobe).

   An Adobe representative can create an FTP account, if one does not already exist. Contact your Adobe Account Manager or Adobe Customer Care to get an account created.
1. Public/Private key creation (Customer).

   Create a public and private key combination. The private key is a file that is private to your computer/server and resides there. The public key file needs to be uploaded to the Adobe account. When used in this manner you can connect without password authentication. The public key file at Adobe matches to the private key file on your computer/server and authenticates in that manner.

   To create these files, engage your internal network support group to create a key set that is proper for your environment. There are many tools and applications that can be used to create these two files.

   An example of how this can be done in a UNIX shell environment is shown below. This is just one example of how this can be done and serves as a helpful point of reference for communicating requirements to your team or internal network group.

   ```
   // Linux/Unix (bash shell)
   
   // First make sure the ".ssh" directory exists
   
   $ mkdir ~/.ssh
   
   $ cd ~/.ssh
   
   // Now actually generate the key pair
   
   // Usually we will want to create an empty passphrase (just hit "Enter" for both password prompts)
   
   $ ssh-keygen -q -t dsa
   
   Enter file in which to save the key (/home/user/.ssh/id_dsa):
   
   Enter passphrase (empty for no passphrase): ...
   
   Enter same passphrase again: ...
   
   // Rename or copy the public key file to "authorized_keys"
   
   // This "authorized_keys" file is the one that we will upload to the Adobe FTP server in step 3
   
   $ cp id_dsa.pub authorized_keys 
   ```

1. Upload Public key to FTP account (Customer).

   Upload and test the public key. Connect to the Adobe FTP account and create a [!DNL .ssh] directory, if it does not already exist. Upload the [!DNL authorized_keys] file to this [!DNL .ssh] directory. This can be done many different ways (command line, graphical FTP client, and so forth). All that is required is the ability to create a directory and upload a file.

   Here, again, is an example of doing this using a UNIX shell.

   ```
   $ ftp ftp.Adobe.com
   
   OR (depending on hostname provided by Adobe)
   
   $ ftp ftp2.Adobe.com
   
   // Enter username and password for account as prompted
   
   ftp> mkdir .ssh
   
   ftp> cd .ssh
   
   ftp> put authorized_keys
   
   ftp> exit
   
   // Now test the connection by logging in to the server using "sftp" command:
   
   $ sftp username@ftp.omniture.com
   
   OR (depending on hostname provided by Adobe)
   
   $ sftp username@ftp2.omniture.com
   
   // You should immediately receive an sftp prompt without having to enter the password:
   
   sftp>
   ```
