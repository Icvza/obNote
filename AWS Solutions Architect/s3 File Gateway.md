---
id: s3 File Gateway
aliases: []
tags: []
---

### Overview

- You can use any type of s3 bucket excluding glacier
  - s3 standard
  - s3 stardard ia
  - s3 one zone ia 
  - s3 intelligent tiering

- when you create the s3 file gateway you will then get to chose to use the nfs or the smb protocol
- s3file gateway will translate the requests into s3 https reqyests
- You can then use the lifecylve polices on the s3 to send them over to glacier to have them archived

- Configured s3 buckets are accessible using the nfs and smb protocol
- most recently used data is chaced in the dile gateway 
- creat i am role for reach file gateway
- If you are going to use the smb protocolyou are going to use integration wiht active directory for user authentication 
- Amazon FSx file gateway
  - native avvess to fsx for windows file server
  - why would you go through the trouble of creating an fxs file gateway
    - Local cache for freqyently accessed data
  - window native compatability useful for group file share and directortys
-Volume gateway
  - Block sotrage usiing iscsi pt backed by s3file
  - backed up by ebs snapchots which can help restore on premises volumes
  - cached volumes low latency access to most recent data
  - stored volumes entire dataset is on premp scheduled backups to s3

- tape getway
  - some companies have backup process using physical tapes
  - with tape gatway but the taes will be backed up to the cloud 
  - Virtual tape library backed by s3 and galcier 
  - backup data using ecisting tape bsed processes and iscsi interface
  - works with leading backup software vendors

- sotage gateway has to be installe in the data center
- Hardware appplicance 
- Otherwise you can use a storage gateway hardware appliance 
- Once you install it then you can set it up as a file gateway
- helpful for daily nfs backup ain small data centeres
- 

