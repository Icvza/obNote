**user scripts**: run commands on the instance at launch

**user data**: Install updates install sofware download common file

# EC2 instance types
**naming convention**: m5.2xlarge  m: instance family 5: generation 2xlarge: size

## types
- General purpose
- compute optimized
- memory optimized
- accelertated computing
- storage optimized
- HPC optimized
- Instance features
- Measuring instance performance

**Compute optimized**:  Good for compute intensize tasks that require high performance processors ex include: Batch processing workloads, media transcoding, high performance web servers, high performance computing HPC scientific modeling and machine learning deidcaed gaming servers very good CPU performace

## Memory optimized
- Good for fast perofrmace workloads that process large data sts in memory
- High performance relational / non relational databases
- Distributed web scale cache stores
- In memory databases optimized for business intelligence
- Application performaing real time processing of big unstructed data
- R series R stands for ram and then there are the x series and the High memory Z1d

## Storage optimized
- Great for storage intensice tasks that rquire hihg, sequential read and write access to large data sets on local storage
- High frequency online transaction processin oltp systems
- Relation and no sqwl datbasese
- cache for in memory databses like redis
- data warehouse applications
- distribted file systems
- they will start with and i d and h1

# security groups
## Intro notes
- Security groups are the fundamental of network security in AWS
- They will control how the traffic is allowed into or out of the ec2 isntance
- secuirty groups only contain allow rules
- security groups rules can refrance by ip or by security grou
- Security groups act like a firewall on ec2 instances
- They regulare the the access to portts authorized ip rnages control of inbound and outbound traffi1c
- 0.0.0.0 means everything
- one security group has inbound and outbound rules
- can be attached to multuple instance
- locked down to region vpc combp
- live outside the ec2
- it good to maintain one seprate group for ssh acess
- time out is a secruity group issue
- connection reguse is not a secruity gorup isseu
- by default all inbout trffic is blocked and all outbound traffic is authoried
- Refrance other secuirty groups for the same instance
- if they have the right security group they can talk to other instances if they are not autthorixzed in the outboutn rules then they will fail
- classic ports 22 ssh log into a linux instance
- 21 for FTP file transer protocall uplaod files into a file share
- 22 sftp secure stransfel protocall
- 80 Http access unsecured websites
- 443 HTTPS access secured websites
- 3389 RDP remote desktip protocall will let you connect to a windows instance

## SSH
- Based on the type of OS there are diff ways to to connect SSH
- SSH for mac linux and windows greateer than 10
- putty is for all windows types
- ec2 instance connect is web browsert based ui that lets you connect to all the os
- Troubleshooting rewatch try ec2 instance connect if one method works your good to go

## ssh into mac
- over port 22 will access ec2 machine
- PEM file is the key to access the ec2 instance
- ssh ec20user @ the oip adderess that you have
- use the public ip
- chmos 0400 - the pem file 
- never use aws congiure in the instance connect always attache an IAm roll to the instance

# EC2 instance purchasing options
**on demand**: short workloads, predictable pricing pay by second

**Reserved**: 1-3 years long workloads convertiablelreseved instances long worklaods with fexable instance

**savings plans**:  more modern 1-3 years term instead of instance type commeit to dollar amount

**Spot instance**: shrot workloads cheap can lose instance less reliable

**Dedicated host**: no other curstomers will share your hardware

**capcity reservation**: reserve capacity in a specifc az for any duration

## EC2 On Demand
- pay for what you use
- Linux or windows billing per second after the frist minute use 
- biling per hour 
- has the higest cost but no upfront payment
- no long term commitment
- short term un interupted workloads

## EC3 Reserved instance
- up to 72 dicount compared to on demand
- specift insatcne attributes
- reservatio persiod
- upfront or not upfront
- reserved instance scope reginal or zone reseve capcity in availablity zone
- recommended to stedy state uysage applications think databases
- You can buy or sell in threserver instance markeplce

## Convertible reserved instance
- can change the ec2 instance type instance familiy os cope and tenancy what is tenancy
- up to a 66 dicount

## EC2 savings plans
- Get a discoutn based on lont tern usage up to 72% same as reserver instance
- Commit to a certain type of usage 10 hour for 1 or 3 years
- Any usage beyond saving plan is billed at on demand rates
- Locked to instance family and aws region
- flexible across instanze size os and tenecy

## Ec2 spot instance
- can get a discount of up to 90- compared to on-demand
- you can lose the instance if the spot price goes aboce your bid
- great for workloads that are reslient to failure
- barch jobs image processing andany image processin
- Define a max spot proce and get the instance while current spot price is below your max
- the hourly sport will vary
- if it goes over you have a 2 minute grace period you can stop or terminate your instance without beign charged
- spot block: block off a set time duration 1-6 without interuption
- used for batch jobs data analysdid or wokrloads that are resilient to failures.
- Not great for critrical jobs or databases
- pricing
- [object Object]
- [object Object]

## EC2 Dedicated hosts
- A phyical server with EC2 Instnace capacity fully deciated to you use
- Allow you to address compliance requirments and use your exisitng server bound software licensed
- per socket per core per vm software licenses
- on demand resered the most expensice option
-  useful for software that have compicated licensing model BYOL bring your own license
-  or for companied that have strong regulatory or compliance needs

## EC2 Dedicated instances
- Instance running on hardware thats'd dedicated to  you
- May share hardware with other instance in same acoutn
- No control over instance placement
-  what is the diffrence betwen dedicated host and dedicated instan type?
- Dedicated instance is the own hardware dedicated host you get acces to the pycial servert

## ex3 capacity reservation
- Reserve on demand instance capcity in specific az for any duration
- You alwyas have access to the ec2 instance capacity when you need it
- No time commitment
- comine with regional reserved instance and saving plans to befit for it
- You are charged at on demand rate wheather you run instance or not
- short temen un interputed worked with low latency

