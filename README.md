# quaich

A Scala “Serverless” Microframework for AWS Lambda, inspired by Amazon's Chalice (https://github.com/awslabs/chalice)

## WTF is a "quaich"

Amazon named their version of the AWS Lamba Microframework “Chalice”, which references what we suppose is a perfectly acceptable drinking vessel.

Being partial to whisky, however, the quaich (pronounced as 'quake') – A Scottish two-handled drinking bowl, often used to serve whisky – sounded like a better inspiration. Sir Walter Scott was said to have served whisky from a quaich carved from the elm tree that served as the Duke of Wellington's command post at the Battle of Waterloo. Which is pretty awesome.

AWS Lambda is an interesting emerging platform for “serverless” programming. Entirely event driven, it provides an easy model to handle both ‘built-in’ Amazon events – such as DynamoDB & S3 Bucket changes, and HTTP calls through services such as Amazon's API Gateway... as well as custom events. Being “serverless”, Lambda allows us to drop in simple JVM code via assembly JAR that responds through an event loop, minimizing execution costs and eliminating the need to setup and maintain dedicated server instances.

quaich (pronounced ‘quake’) is a Scala microframework, inspired by the Python based [chalice](https://github.com/awslabs/chalice) released by Amazon recently. The concept is simple, single file applications that can receive and handle the JSON events pushed by the Lambda system. Through clever tricks with macros, etc. we provide an easy model for defining your routes files and even parsing custom variables.

# Authors
[Thomas Lockney](https://github.com/tlockney)*

[Brendan McAdams](https://github.com/bwmcadams)

* Original idea by Thomas

# TODO

- [Logging support](http://docs.aws.amazon.com/lambda/latest/dg/java-logging.html)
- Flexibility using both core, structured base handler APIs such as Amazon provides, and customizable ones.
- Support for multiple pluggable JSON libraries, because Scala has about 64k of them and everyone has their own preference
- Macro annotations like chalice's python decorates for easily defining routes
- Variable handling in routes
- sbt deployment plugin
- Support for POJO translation
- Support for S3 & DynamoDB Triggers
- Write an sbt-lambda-deploy plugin that doesn't suck. the gilt one is an unreliable mess. Use [Amazon's Transfer](http://docs.aws.amazon.com/AWSJavaSDK/latest/javadoc/com/amazonaws/services/s3/transfer/TransferManager.html) status APIs for upload
- Offline simulator for easier testing / dev. There's an [interesting one for Node](https://github.com/dherault/serverless-offline)
