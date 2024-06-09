---
id: 1717957382-QIYR
aliases:
  - sns+sqs fan out
tags:
  - sns
---
# sns+sqs The idea here is to hace one sns topic talk to multiple sqs queues

service -> sns topic -> 1 sqs que: fraud service, 2 sqs que: shipping service

Feats:
- fully decoupled 
- no data loss
- sqs allows for data persistence dealayed processing and retries of work
- Ability to add more sqs subscribers over time
- Make sure your sqs queue access policyu alows for sns to write
- cross region delivery works with sqs queues in other regions

### How to use fan out pattern for other pruposes
- s3 events into multiple queues
  - for the same combination of:event type ex object created and prefix you can only have one s3 event rule
  - If you want to send the same event to multuiple sqs queses
  - s3 event -> s3 -> sns topoic -> sqs queues
- SNS to S3 through kinesis data firehose
  - SNS can send to kinesis and therefore we can have the following solutions architecture
  - service -> sns topic -> kinesis data firehose -> s3 (any supported kdf destination)

### FIFO (first in first out)
- The message producer can send out messages in order 1,2,3,4, and the sns topic will send the messages to the sqs quees in that order 1,2,3,4 
- You can order message by group id (all messsages in the same group are odered)
- Can have sqs standard and fifo queues as subscribers
- limited throughput smae throuAput as sqs fifo queue

### SNS Message filtering
• JSON policy used to filter messages sent to SNS topic’s subscriptions
• If a subscription doesn’t have a filter policy, it receives every message

