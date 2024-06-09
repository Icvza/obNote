## overview
- Different type of storage for EC2 instance

## EBS Elastic block storage
- Elastic block sotrage
- An Elastic block store volume is a network drive you can attach to you instance while they run
- It allows your instance to persist data even after the instance is terminated
- They can only be mounted to one instance at at time (there is a note about this being a CCP Level)
- They are bound to a specift availibility zone
- think about them as network usb sticks and put it another computer
- It is a network drvie  not a physical drive
- there may be alittle bit of latency because it uses the network to communicate
- It can be detached from an ec2 Instance and attached to another one quickly
- Its locked to and az
- To move a volume accross you will need to snapshot it and then you can move it to another az
- Have to provision capacity in advace and  IOPS
- you will get billed for the capacity 
- It is possible to have two ebs attacvhed to the same ex2 instance
- [object Object]
- [object Object]

## EC2 instance store
- A way to have a physical drive on the server
- The name of the harddrive attached to the server
- better io performace
- the sotrage is lost when the instance is termiantied
- ephemeral storage
- good for buffer chache and temp content
- Ris of data loss if the hardware fails
- backup and replication is your responsibility

# EBS volume tyes
**gp2 and gp3**: General purpose SSD volume that balacnes price and performance for a variety of worklaods

**io1 and io2**: high performance SSD volume for critical low latency or high throughput worklaods

**st1**: Low cost HDD volume designed for frequently accessed throughput intensive worloads

**sc1**: Lowest cose HDD volume designed for less frequently accessed worloads

## How can you define an ebs volume there?
- size
- Throughput
- IOPS
- only for ec2 instances gp2 and gp3 and io1 and io2 block express can be used as boot volumes (where the root os will run)

## General purpose SSD use cases
- cost effective low latency
- system boot volumes virtual desktops development and test enviorments
- 1gib - 16tiib
- gp3 has a baseline of 3,000 iops and 125mibs can increase to 16k and 1k respectivly
- gp2 small gp2 volumes can burst iops to 3k
- size of the volume and iops are linked max iops is 16k
- 3iops per GB so once the ssd is at 5334 you will have the max iops

## Provisioned IOPS ssd
- Critical business  applications that require sustained iops performance
- applications that need more the 16k iops
- Great for DBs workloads that are sensitive to storage performance
- io1 max piops 64k for nitro and 32k for other
- Can increase PIOPS independently of the storage size
- io2 block express
- 256k max PIOPS
- supports EBS multi match

## Hard disk drive
- Cannot be a boot volume
- 16 tbs
- st1 big data warehouses log prrocessions

## EBS multi attach io1 io2 family
- Attach the same EBS volumes to multiple ec2 instance in the same AZ
- can use it for clustering and high availibility workloads
- io1 and io2 only
- Full read and write to the high performance volume
- hihger application availiblity 
- must manage concurent writes
- Up to 16 at a time
- you must use a file system that is cluster aware
- NOT XFS or ES4

