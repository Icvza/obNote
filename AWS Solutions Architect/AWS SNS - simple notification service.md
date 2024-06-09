---
id: AWS SNS - simple notification service
aliases: []
tags:
  - sns
---
### AWS SNS - overview

What if you want to send one message to many receivers?

Soultion: Pubb/sub mdoel one service will send a mesage to an sns topic and 
have it for thier own

- the event producer only sends the mesage to the sns topic
- As many event receivers (subs) as we watn to listen to the sns topic
- Each subscriber to the topic will get all the messages - can filiter messages
- up to 12.5 million subscriptions per topic
- 100k topics limit

Can send emails, sms and mobile push notifications and http endpoints also has connection to other aws services like:
 - sqs
 - lambda
 - Kinesis firhose

Many other aws services can send datat directly to sns for notifications
- cloud watch alarms
- auto scaling group
- cloud formation state changes
- aws budgets alerts
- s3 buckets events
- aws DMS
- lambda
- dynamo db
- RDS events

[[AWS sns fan out|sns+sqs fan out]]



