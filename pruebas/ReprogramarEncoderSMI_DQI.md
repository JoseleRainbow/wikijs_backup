---
title: ReprogramarEncoderSMI_DQIge
description: 
published: true
date: 2022-01-19T09:04:49.331Z
tags: 
editor: markdown
dateCreated: 2022-01-19T08:57:49.204Z
---

# **SIMOTICS S: Programming a new / deleted DRIVE-CLiQ encoder**

This FAQ describes how to write motor data in a new or deleted DQI encoder.

> **Question:**  
> How can I reprogram an empty or deleted DRIVE-CLiQ encoder (G2) if no direct encoder replacement was performed?

> **Answer:**  
> In case of direct encoder replacement at the system on site, please proceed according to FAQ [89859023](https://support.industry.siemens.com/cs/document/89859023/simotics-s-brief-instructions-%e2%80%93-replacing-an-drive-cliq-encoder-(generation-2)?lc=en-de) 

> **1\. Unambiguous identification of the encoder to be written:**

-   [ ] ·         Insert the encoder in a free DRIVE-CLiQ port of the SINAMICS S120 drive system.
-   [ ] ·         This is now assigned a component number larger than 200. The component number must be identified, for example, 201.

> **2\. Download the electronic motor data**

·         You can download the electronic nameplate by entering the complete motor series number under  [www.siemens.com/simotics/download](http://www.siemens.com/simotics/download). You will obtain one or two.bin files.

> **3\. Store motor files on the CF card**

·         Create a folder in: user/sinamics/data/smi\_data\_man.

·         Then create a subfolder which corresponds to the component numner, for example, user/sinamics/data/smi\_data\_man/c201  (note lower cases!).

·         Store the downloaded file(s) in this folder.

> **4\. Writing the encoder:**

·         Set the passwort level required:  
          SINAMICS: Expert || SINUMERIK: manufacturer.

·         Enter the encoder component number, e.g. 201, in the drive parameter p4690.

·         Select in p4691: \[2\] “Load SMI data“ to write data to the encoder.

·         p4691 then changes to \[9\] “SMI data loaded and POWER ON required for component“.

> **5\. Power OFF/ON**

·        POWER OFF / ON the system. The encoder is now programmed and can be inserted where it has been originally used.  
  
 

> **6. Check the data in the DQ encoder**

-   Set p0300 = 10100 to read out the electronic motor rating plate and check the values.