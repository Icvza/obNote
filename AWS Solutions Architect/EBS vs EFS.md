## EBS volume
- One instance except for io2 and io2
- Are locked at the az level
- gp2 io increase if the disk size increase
- gp3 and io can increase io independently
- To migrate and ebs volume across an az you will need to take a snapshot and then create a new EBS volume in the other az
- EBS backups will use io should not run them when there is alot of traffic
- EFS ia netwrok file system that can be attached to multiple ec3 instnace in multiple az
- Only for lunx instnace posix
- cost more tha EBS
- can leverage EFS-ia for cost savings
- instance store is phycisal disk attached to the ec22 isntance

