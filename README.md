# Building Organization Service Health Check Solution with Cloud9 and QuickSight
Showcase retrieving service health status via Cloud9 by calling health api at organization level, and visualise the health status data through QuickSight.

# Introduction
This lab aims to show users how easy it is to call AWS health API at organization level through Cloud9. The python code initially runs locally in the Cloud9 environment, where we will upload the health status data to S3 bucket, and then visualise the data using QuickSight. Optionally, user can consider to integrate email SNS to get notification upon the conditions setup by the operation team.

![Image of Yaktocat](https://github.com/JerryChenZeyun/aws-health-api-organization-view/blob/master/Screen%20Shot%202020-02-23%20at%209.02.34%20pm.png)

# Setup
1. Goto to AWS Console, select Cloud9 service (In N.Virginia Region -- "us-east-1"). Or simply click the following link:
https://console.aws.amazon.com/cloud9/home?region=us-east-1

2. Create a new Cloud9 environment by Clicking the "Create Environment" button
![Image of Yaktocat](https://github.com/JerryChenZeyun/aws-health-api-organization-view/blob/master/Screen%20Shot%202020-02-23%20at%209.30.48%20pm.png)

3. Give a name to the new environment. In this demo, we can name it as "demo-env". 
![Image of Yaktocat](https://github.com/JerryChenZeyun/aws-health-api-organization-view/blob/master/Screen%20Shot%202020-02-23%20at%209.32.55%20pm.png)

4. Accept other default settings, click "Next step", and then finalise the creation by clicking "Create environment".
![Image of Yaktocat](https://github.com/JerryChenZeyun/aws-health-api-organization-view/blob/master/Screen%20Shot%202020-02-24%20at%208.38.54%20pm.png)

5. Once the Cloud9 environment has been provisioned, use the following command to update the boto3 library -- as the current default library version (1.10.41) doesn't support the latest AWS health API for Organization.

    `python -m pip install boto3 -t ./`

6. As we need to use python pandas module to translate the json data into csv file, please use the following command to install pandas module

    `python -m pip install pandas --user`
    
7. Now the environment has almost ready. So please use the following command to download the project to Cloud9, and copy the "health_org_demo.py" date to the environment folder.

    `git clone https://github.com/JerryChenZeyun/aws-health-api-organization-view.git`
    
    `cp /home/ec2-user/environment/aws-health-api-organization-view/health_org_demo.py /home/ec2-user/environment/health_org_demo.py`

8. Use the Cloud9 editor environment to change the following parameter value based on your Lab environment info:

    1) accountId - change it to your 12 digit account id number. You can find your AWS account id via this link:
    https://console.aws.amazon.com/billing/home?#/account
    
    2) bucketName - change it to your bucket name, which is used to host the data fetched by the health api. You can find your buckets via this link:
    https://s3.console.aws.amazon.com/s3/home


![Image of Yaktocat](https://github.com/JerryChenZeyun/aws-health-api-organization-view/blob/master/Screen%20Shot%202020-02-24%20at%208.38.54%20pm.png)




