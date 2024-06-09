## overview
- when you create an encrypted EBS volume you get the following
- Data at rest is encrypted inside the volume
- All the data in flight moving between the instance and the volme is encrypted
- All Snapshots are encrypted
- All volumes created from the snapshot are encrypted
- Encryption and decryption are handled transparenlty meaning you have nothing to dp
- Encryption has a minimal impact on latency
- Keys from KMS AES256
- when you copy a unencrypted snapshot it will allow encryption
- Snapshots of encrypted volumes are encrypted
- Create an EBS snaopt of the volume ENCRYPT the EBS snapshot Create a new EBS from the encrypted snapshot attach the encrypted volume to the EC2 instance
- Yout can also creat volume from the un encrypted snapshot and the encrypt the volume on creatioon

