---
title: Supported HTTPS encryption algorithms
description: On June 23, 2022 we will remove support for TLS 1.2 ciphers that utilize SHA1 or CBC for customers with cipher security level set to “High”.
feature: Regional Data Collection
exl-id: f1cbb0cb-fd65-4f22-8594-0d97b6906698
---
# Supported HTTPS encryption algorithms

Adobe offers two cipher security levels to meet varying customer needs for security on first-party data collection. These levels determine which encryption algorithms are supported for HTTPS connections with our servers. Customers default to ‘Standard’, which supports only modern encryption algorithms. ‘High’ supports a smaller list of encryption algorithms for customers who are more concerned about these connections. For both security levels, Adobe regularly updates the set of supported algorithms based on current security practices. If you would like to change your cipher security settings, please contact Customer Care.
 
On June 23, 2022 we will remove support for TLS 1.2 ciphers that utilize SHA1 or CBC for customers with cipher security level set to “High”.  This change will impact secure data collection for end users on older operating systems.  

The following TLS 1.2 ciphers will no longer be supported: 
 
* TLS_ECDHE_ECDSA_WITH_AES_128_CBC_SHA 
* TLS_ECDHE_ECDSA_WITH_AES_256_CBC_SHA 
* TLS_ECDHE_RSA_WITH_AES_128_CBC_SHA 
* TLS_ECDHE_RSA_WITH_AES_256_CBC_SHA 
* TLS_RSA_WITH_AES_128_CBC_SHA 
* TLS_RSA_WITH_AES_256_CBC_SHA 
* TLS_RSA_WITH_AES_128_GCM_SHA256 
* TLS_RSA_WITH_AES_256_GCM_SHA384 
 
The following clients are known to be impacted by this change because they lack support for current encryption standards: 
 
* Windows 8.1 and earlier (last updated in 2018) 
* Windows Phone 8.1 and earlier (last updated in 2016) 
* OS X 10.10 and earlier (last updated in 2017) 
* iOS 8.4 and earlier (last updated in 2015) 
 
Android devices are not impacted by this change. 
 
Customers with cipher security level set to “Standard” are not impacted by this change.
