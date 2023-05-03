---
title: Supported HTTPS encryption algorithms
description: TLS cipher security settings and certificate types.
feature: Regional Data Collection
exl-id: f1cbb0cb-fd65-4f22-8594-0d97b6906698
---
# Supported HTTPS encryption algorithms

## Cipher Security Levels

Adobe offers two cipher security levels to meet varying customer needs for security on first-party data collection. These levels determine which encryption algorithms are supported for HTTPS connections with our servers. Adobe regularly reviews and updates the set of supported algorithms based on current security practices. If you would like to change your cipher security settings, please contact Customer Care.
 
'Standard' cipher security level requires TLS 1.2 or newer and at least 128-bit encryption.  This is the default setting.  It is designed to provide the widest device compatibilty while maintaing secure encryption.

'High' cipher security level requires TLS 1.2 or newer and removes support for weaker ciphers.  It is designed for customers who desire the strongest encryption and are not concerned about support for older devices.

The following clients are known to be unable to connect with cipher security set to "High".
 
* Windows 8.1 and earlier (last updated in 2018) 
* Windows Phone 8.1 and earlier (last updated in 2016) 
* OS X 10.10 and earlier (last updated in 2017) 
* iOS 8.4 and earlier (last updated in 2015) 
 
## Supported HTTPS certificate types

Adobe supports both RSA and ECC certificate types to meet varying customer needs.  RSA certificates are more widely supported for clients, but ECC certificates use less processing on both the server and client side.  For Adobe Managed certificates, both RSA and ECC are provided.  For customer managed certificates, both RSA and ECC are recommended but customers have the option to provide either or both certificate types.  Modern clients support both RSA and ECC.  The following clients are known to only support RSA certificates:

* Windows Vista and earlier (last updated in 2012)
* Windows Phone 8.0 and earlier (last updated in 2014)
* OS X 10.8 and earlier (last updated in 2013)
* iOS 5.1 and earlier (last updated in 2012)
* Android 4.3 and earlier (last updated in 2013)
