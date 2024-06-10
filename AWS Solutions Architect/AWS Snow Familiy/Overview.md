### What is AWS Snow Family?

- There are two primary purposes. Highly secure, Portable devices to collect and process data at the edge and migrate data into and out of AWS
	- Edge Computing:
		- Snowcone, Snowball Edge 
	- Data migration: 
		- Snowcone, Snowball Edge Snowmobile

- - -
### Data Migrations
Offline devices to perform data migrations 
#### Why? (Limitations on using network migrations):
- Limited connectivity 
- Limited bandwidth
- High network cost
- Shared bandwidth (can't maximize the line)
- Connections stability
- - -
### Snowball Edge
Use case:
 Large data cloud migrations, DC decommission, disaster recovery
- Physical data transport solution: move TBs or PBs of data in or out of AWS
- Alternative to moving data over the network (and paying network fees)
- Pay per data transfer jobs
- Interface provides block storage and Amazon S3-compatible object storage. 

Return Method: 
- It can be sent back to AWS offline
##### Snowball Edge Optimized
- 80 TB of HDD capacity for block volume and S3-compatible object storage 
##### Snowball Compute Optimized
- 42 TB of HDD or 28 TB NVMe capacity for block volume and S3-compatible object storage 
- - -
### Snowcone & Snowcone SSD
Use case: Used where Snowball does not fit (space-constrained environment)
- Small portable computing anywhere, rugged & secure, withstands harsh environments.
- Lightweight 4.5lbs 2.1 kg
- Device used for edge computing storage and data transfer 
- You must provide your batteries and cables 

Return Method: 
- It can be sent back to AWS offline.
- Or connect it to the internet and use AWS DataSync to send data.
##### Snowcone 
- 8TB of HDD Storage 
##### Snowcone SSD
- 14TB of SSD Storage 
- - - 
#### Snowmobile
Use Case:
	You need to transfer ALOT of data.

- It's a physical truck. 
- Transfer Exabytes of data (1eb = 1,0000 pb = 1,000,000 TB's)
- Each snowmobile will have 100pb of capacity (use multiple in parallel)
- High security: temperature-controlled GPS 24/7 video surveillance 
- Better than Snowball if you transfer more than 10pb
- - - 
#### Usage 
- Request snowball device from the AWS console for delivery
- Install the snowball client / AWS ops hub on your servers.
- Connect the snowball to your servers and copy files using the client 
- Ship back the device when you  are done 
- Data will be loaded into an s3 bucket. 
- Snowball is completely wiped
- - -  
#### Edge Computing
Use cases: 
- Preprocess data
- Machine learning at the edge
- Transcoding media streams

Why?: Process data while it's being created on an edge location
- These locations may have:
	- limited / no internet access 
	- limited / no easy access to computing power

Eventually (if need be) we can ship back the device to AWS (for transferring data for example)

We set up a Snowball Edge / Snowcone device to do edge computing
- - -
#### Snowcone and Snowcone SSD (smaller)
- 2 CPU 4GB of memory, wired or wireless access
- USB-C-power to power or option battery

#### Snowball edge - compute-optimized
- 104 vCPU 416gib ram
- optional GPU for video processing or machine learning 
- 28tb name or 43 tb hdd 
- Storage clustering is available to increase storage 

#### Snowball edge storage optimized
- Up to 40 vcpus 80GB ram 80TB storage 

Long-term deployment options 1 and 3 years discounted pricing 
- - - 
#### Ops hub
Historically you needed the CLI to interact with the snow devices
Today you can use AWS OpsHub a software you install on your computer to manage your snow family device 

Unlocking and configuring single or clusterd devices
launching and managing instaces running snow family devices 

Monitor device metrics Storage capacity active instance on your device 
]launch compatble aws serices on your device ec2 aws dats sync nfs 


Snow ball cannon import into glacier 
Use s3 first and then create lifecylce policy  snowballl into s3 lifecylve inot glacier 


#### Side notes
If it takes more than a week to transfer over the network, use Snowball devices!!