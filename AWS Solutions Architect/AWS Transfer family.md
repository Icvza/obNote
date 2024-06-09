---
id: AWS Transfer family
aliases: []
tags: []
---

#### Overview

- the idea is that you want to send data in and out of amazon s3 or  efs buy you don't want to use the 
- amazon efs using the ftp pt 
- supported pt
  - ftp 
  - ftps 
  - sftp 
- managed infra scalabel reliable and HA 
- pay per provisioend endpoint per hour and fee data transfer 
- integrates with auth systems like active directory ldap okta amazon cognito custom,

### Data sync
- move large amount od data to and from places
- on prem to cloud or other cloud to aws needs agent 
- aws to aws no agent needed 
- sync data to s3  efs fsx all of them 
- replication task can be schduled hourly daily weekly
- file perms and metdata are preserved 
- one datsycn agent can use up 10 gbs persecond you can setup and bandwidth limit~
