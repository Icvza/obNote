---
id: AWS SQS
aliases: []
tags: []
---

#### Overview 
- Fully manged service used to decouple applications

##### Attributes
- Unlimited throughput, unlimited number of messages in queue
- Each message is short lived. Default messages 4days, max days 14
- As soon as you send a message it has to beread and deleted within the retention period 
- Low latency 
- Limitation to 256kb
- can have duplicate messages at least once delivery occasionally
- Can have out of order messages best effort ordering

##### Producers
- Produced to sqs using the sdk send messsage applications
- The message is persisted in sqs until a consumer deletes

##### Consuming messages
- Consumers could be running on ec2 instances on aws but could also run on your own on premise servers
- polls sqs for messages can recieve up to 10 messages a time
- you handle the messages
- delete the message form the que using the delete message api
- scaling sqs multiple ec2 instances Consumers
- consumers recieve and process messages in paralllel
- best effort ordering
- if we need to increase the troughhput because we have more messages then we can scale consumers horizontally to improve throughput of processings

###### Scaling with asg 
your instance will live inside an asg and the sqs will poll for messages
you can listen to a cloudwatch metric called cube length to que length 
whenver the que lengths goes over the level set an alrm and increase asg

sqs to decouple between application tiers
use case: video upload 
you can use this to send a message to your sqs queand the sqs will then send it over to the backend and then the asg will insert into the s3

##### secuirty 
encryption in flight envtyption using https api
at rest encryption using kms keys
client side edncryption if the client wants to perforem
ami
sqs acess polices


#### Message visibility timeout
- when a messsage is poleld by a consumer it becomes invisible to other consumers
- timeout is 30 that means that you have 30seconds to process the message
- will be put back into the
- if a consumer has picked up the message but knows that it needs a little bit more time then it will call the change message visability api to get more time
- avoids processing twice
- find a balance lol

long polling
when a consumer request messages from the tque it can optionally wait for mesages to arrive if there are non in the que 
you can do this to decrease latency
1 to 20 seconds 
you can configure it a the que level or the consumer can chose by useing the wait timeout settings

#### FIFO queue
first in first out this is ordering of messages in the queue
limited trhoughput 300ms without batching 3000 with
Messages are proccessed in order by the consumers
need to maintaint the ordering of messsages

