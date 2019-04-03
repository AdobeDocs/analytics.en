---
description: Instructions on how to run Ad Hoc Analysis with Java 11.
seo-description: Instructions on how to run Ad Hoc Analysis with Java 11.
seo-title: Ad Hoc Analysis and Java 11
title: Run Ad Hoc Analysis with Java 11
---

# Run Ad Hoc Analysis with Java 11

Running Ad Hoc Analysis with Java 11 is slightly different than running it with Java 8. Before proceeding, check with your IT team to understand which version of Java you have installed. If your organization is using Java 11, follow the installation instructions below.

## Install Ad Hoc Analysis for Java 11

1. Go to **[!UICONTROL Analytics > Tools > Ad Hoc Analysis]**.
1. Click **[!UICONTROL Ad Hoc Analysis (Java 11)]**. This downloads a zip file.
1. Unzip the downloaded file.
1. **Select the .bat (PC) or .sh (Mac) file**. Select the appropriate data center file by looking at the number following “sc” in the Adobe Analytics URL. (3 = LON, 4 = SIN, 5 = PNW) If you use a PC, verify whether you are running a 32-bit or a 64-bit Windows operating system by going to ‘About your PC’. Then select the appropriate .bat file.
1. **Run the selected file**. For PC: Doubleclick the .bat file. For Mac: Right-click the .sh file, then select **[!UICONTROL Open With > Other... > Utilities > (Enable all applications) > select Terminal > Open]**.
1. Log in to Ad Hoc Analysis. 

>[!Note]
>
> Federated and Enterprise ID authentication methods are not supported in the Java 11 version of Ad Hoc Analysis.

## Unsupported Features in Ad Hoc Analysis (Java 11)

There are a few known limitations in the Java 11 version compatible with Ad Hoc Analysis:

* Federated & Enterprise ID authentication methods are not supported.
* Linux operating systems are not supported.
* When using a Mac, do not use the Mac application menu (including cmd + Q). This may cause Ad Hoc Analysis to close without warning. Instead, use the menu inside Ad Hoc Analysis.

## FAQ

**Q: I get a “Cannot find \bin\javaw” error (example below) - what should I do?**

![](/help/analyze/ad-hoc-analysis/assets/error-java.png)

A: If you get this error, work with your IT team to set the JAVA_HOME environment variable which is required to run Ad Hoc Analysis in Java 11. 