**overview**: You can encypt objects in one of four ways

## methods to encypt
- serverside encyption
- You have multiple flavors of sse sse with amazon s3 managed keys enabled by defulat
- ss3 kms keys sotre in aws kms sse-kms
- ssec custom proivded keys
- encypt client side and then upload tos s3

## sse-3
- encyption using keys handled managed and owned by aws
- Object will be encypted server side
- Encyption  AES 256
- you well send over an ovjext aws will encypt the key with the objext and then store in on the s3

## ss3 KMS
- Instead of relying on s3 an the s3 key service you want to manage your own key service
- User control audi key usage via cloudTrail
- Object is encypted server side
- must set header x-amz'servi-side encyption: aws: kms
- not only do you need access to the s2 bucket but you need access to the kms the generstaed the key
- this is all in the header when using
- limiations: make api calls each call will count towards the qutoa
- they could throttle you if you make to many calals

## sse c
- you provide the key to s3
- sse using fully managed by the customer outside of aws
- https must be used and the key will have to be in the header in each reuesst

## client side ecntyp
- you can use client libaraies such as amazon s3 client side enctyption library 
- clients must encrpt data themselves before sending it to amazon s3
- clients must decrptyt the data themselves when retriving from amazon s3
- customer fully manges the keys an anctyption code

## ssl or tls
- in flight encryption
- amazon s3 exposes two endpoing
- http endpoitn not encyptied
- how to force encryption in transit aws secure transport
- you can create a s3 bucket policy and deny any get operation that secure transport is false

**mfa delete**: enable version and it wil prompt you to use mfa delete the version

**pre signed urls**: useres will inhere the persmison of the issuing usse senf someone tha tdoesnt have acces a file

**acessl log**: can log to another bucket do not make the loging and app bucket the same

**valut lock plil**: worm write one read many creat a valut lock plicy good for compliance and data retenetion

**objext lock**: versioing must be ebalbed a lock you can use for each object in the bucket

