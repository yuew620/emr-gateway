# emr-gateway

This project is used to set up a gateway for AWS EMR.
You can use  command such as spark, hive, beeline, hadoop etc , on this gateway.
There are several steps.

Requisit:
You already set up an AWS EMR.

1 launch an EC2 instance as a gateway instance， in the same VPC as EMR use

2 Configure EMR Security Group inbound rule, including master, core, task's security group.
Let the gateway can send traffic to emr nodes.

3 you need an S3 bucket, for temporary saving files. Copy the s3 bucket name.

4 ssh the EMR master node, upload the emr.sh .
Modiy the emr.sh , input the correct s3 bucket name that you copied in the previous step.
Run the emr.sh

5 configure the gateway.
Use command:
AWS configure
Input the region , AKSK. (You can get acesskey secretkey in IAM user configuration)

ssh the gateway instance
Modify the gateway.sh, input the correct s3 bucket name
Run the gateway.sh
6 Done
Check the hadoop command
