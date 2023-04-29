# Sample Exam Questions II

Source: Whizlabs 

## WL1

You are an AWS Solutions Architect. Your company has a successful web application deployed in an AWS Auto Scaling group. The application attracts more and more global customers. However, the application’s performance is impacted. Your manager asks you how to improve the performance and availability of the application. Which of the following AWS services would you recommend? 

    [( )] AWS DataSync 
    [( )] Amazon DynamoDB Accelerator
    [( )] AWS Lake Formation
    [(X)] AWS Global Accelerator
***********************************************************************

Answer: D

AWS Global accelerator provides static IP addresses that are anycast in the AWS edge network. Incoming traffic is distributed across endpoints in AWS regions. The performance and availability of the application are improved.

Option A is *incorrect:* Because DataSync is a tool to automate the data transfer and does not help to improve the performance.

Option B  is *incorrect:* DynamoDB is not mentioned in this question.

Option C  is *incorrect:* Because AWS Lake Formation is used to manage a large amount of data in AWS which would not help in this situation.

Option D  is  CORRECT:  Check the [AWS Global Accelerator use cases](https://docs.aws.amazon.com/global-accelerator/latest/dg/introduction-benefits-of-migrating.html). The Global Accelerator service can improve both application performance and availability.

***********************************************************************

## WL2

Your team is developing a high-performance computing (HPC) application. The application resolves complex, compute-intensive problems and needs a high-performance and low-latency Lustre file system. You need to configure this file system in AWS at a low cost. Which method is the most suitable?

    [(X)] A. Create a Lustre file system through Amazon FSx.
    [( )] B. Launch a high-performance Lustre file system in Amazon EBS.
    [( )] C. Create a high-speed volume cluster in an EC2 placement group.
    [( )] D. Launch the Lustre file system from AWS Marketplace.
***********************************************************************

Answer: A

The Lustre file system is an open-source, parallel file system that can be used for HPC applications. Refer to http://lustre.org/ for its introduction. In Amazon FSx, users can quickly launch a Lustre file system at a low cost.

Option A is CORRECT: Amazon FSx supports Lustre file systems and users pay for only the resources they use.

Option B is incorrect: Although users may be able to configure a Lustre file system through EBS, it needs lots of extra configurations, Option A is more straightforward.

Option C is incorrect: Because the EC2 placement group does not support a Lustre file system.

Option D is incorrect: Because products in AWS Marketplace are not cost-effective. For Amazon FSx, there are no minimum fees or set-up charges. Check its pricing in Amazon FSx for Lustre Pricing.

***********************************************************************

## WL3

You host a static website in an S3 bucket and there are global clients from multiple regions. You want to use an AWS service to store cache for frequently accessed content so that the latency is reduced and the data transfer rate is increased. Which of the following options would you choose?

[( )] A. Use AWS SDKs to horizontally scale parallel requests to the Amazon S3 service endpoints.
[( )] B. Create multiple Amazon S3 buckets and put Amazon EC2 and S3 in the same AWS Region.
[( )] C. Enable Cross-Region Replication to several AWS Regions to serve customers from different locations.
[(X)] D. Configure CloudFront to deliver the content in the S3 bucket.
***********************************************************************

Answer: D

CloudFront is able to store the frequently accessed content as a cache and the performance is optimized. Other options may help on the performance however they do not store cache for the S3 objects.

Option A is incorrect: This option may increase the throughput however it does not store cache.

Option B is incorrect: Because this option does not use cache.

Option C is incorrect: This option creates multiple S3 buckets in different regions. It does not improve the performance using cache.

Option D is CORRECT: Because CloudFront caches copies of the S3 files in its edge locations and users are routed to the edge location that has the lowest latency.

***********************************************************************

## WL4

You host a static website in an S3 bucket and there are global clients from multiple regions. You want to use an AWS service to store cache for frequently accessed content so that the latency is reduced and the data transfer rate is increased. Which of the following options would you choose?

[( )] A. Use AWS SDKs to horizontally scale parallel requests to the Amazon S3 service endpoints.
[( )] B. Create multiple Amazon S3 buckets and put Amazon EC2 and S3 in the same AWS Region.
[( )] C. Enable Cross-Region Replication to several AWS Regions to serve customers from different locations.
[(X)] D. Configure CloudFront to deliver the content in the S3 bucket.
***********************************************************************

Answer: D

CloudFront is able to store the frequently accessed content as a cache and the performance is optimized. Other options may help on the performance however they do not store cache for the S3 objects.

Option A is incorrect: This option may increase the throughput however it does not store cache.

Option B is incorrect: Because this option does not use cache.

Option C is incorrect: This option creates multiple S3 buckets in different regions. It does not improve the performance using cache.

Option D is CORRECT: Because CloudFront caches copies of the S3 files in its edge locations and users are routed to the edge location that has the lowest latency.

***********************************************************************

## WL5

Your company has an online game application deployed in an Auto Scaling group. The traffic of the application is predictable. Every Friday, the traffic starts to increase, remains high on weekends and then drops on Monday. You need to plan the scaling actions for the Auto Scaling group. Which method is the most suitable for the scaling policy?

[( )] A. Configure a scheduled CloudWatch event rule to launch/terminate instances at the specified time every week.
[(X)] B. Create a predefined target tracking scaling policy based on the average CPU metric and the ASG will scale automatically.
[( )] C. Select the ASG and on the Automatic Scaling tab, add a step scaling policy to automatically scale-out/in at fixed time every week.
[( )] D. Configure a scheduled action in the Auto Scaling group by specifying the recurrence, start/end time, capacities, etc.
***********************************************************************
Answer: B

The correct scaling policy should be scheduled scaling as it defines your own scaling schedule. Refer to https://docs.aws.amazon.com/autoscaling/ec2/userguide/schedule_time.html for details.

Option A is incorrect: This option may work. However, you have to configure a target such as a Lambda function to perform the scaling actions.

Option B is CORRECT: The target tracking scaling policy defines a target for the ASG. The scaling actions happen automatically based on the metric. This is the most suitable option in this scenario.

Option C is incorrect: The step scaling policy does not configure the ASG to scale at a specified time.

Option D is incorrect: With scheduled actions, the ASG scales based on the predefined schedule. It does not automatically scale based on the metric.

***********************************************************************

## WL6

You need to deploy a machine learning application in AWS EC2. The
performance of inter-instance communication is very critical for the application
and you want to attach a network device to the instance so that the performance can
be greatly improved. Which option is the most appropriate to improve the
performance?

[( )] A. Enable enhanced networking features in the EC2 instance.
[(X)] B. Configure Elastic Fabric Adapter (EFA) in the instance.
[( )] C. Attach high-speed Elastic Network Interface (ENI) in the instance.
[( )] D. Create an Elastic File System (EFS) and mount the file system in the instance.
***********************************************************************
Answer:B

With Elastic Fabric Adapter (EFA), users can get better performance if compared
with enhanced networking (Elastic Network Adapter) or Elastic Network Interface.
Check the differences between EFAs and ENAs in
https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/efa.html

Option  A   is  incorrect:  Because with Elastic Fabric Adapter (EFA),
users can achieve a better network performance than enhanced networking.
Option  B  is CORRECT: Because EFA is the most suitable method for
accelerating High-Performance Computing (HPC) and machine learning applications.
Option C is incorrect:  Because Elastic Network Interface (ENI) cannot improve the performance as required.
Option  D  is incorrect: inter-instance communication. The Elastic File System (EFS) cannot accelerate

***********************************************************************

## WL7

You have an S3 bucket that receives photos uploaded by customers. When an
object is uploaded, an event notification is sent to an SQS queue with the object
details. You also have an ECS cluster that gets messages from the queue to do the
batch processing. The queue size may change greatly depending on the number of
incoming messages and backend processing speed. Which metric would you use to
scale up/down the ECS cluster capacity?

[(X)] A. The number of messages in the SQS queue.
[( )] B. Memory usage of the ECS cluster.
[( )] C. Number of objects in the S3 bucket.
[( )] D. Number of containers in the ECS cluster.
***********************************************************************
Answer:A

In this scenario, the SQS queue is used to store the object details which is a highly
scalable and reliable service. ECS is ideal to perform batch processing and it should
scale up or down based on the number of messages in the queue. For details please check
https://github.com/aws-samples/ecs-refarch-batch-processing.

Option A is CORRECT: Users can configure a CloudWatch alarm based on the number of messages in the SQS queue and notify the ECS cluster to scale up or
down using the alarm.
Option B is incorrect: Because memory usage may not be able to reflect the workload.
Option C is incorrect: Because the number of objects in S3 cannot determine if the ECS cluster should change its capacity.
Option D is incorrect: Because the number of containers cannot be used as a metric to trigger an auto-scaling event.

***********************************************************************

