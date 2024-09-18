## AWS CPU Utilization Alert Project ##
**>>>>>>>>>>>>>>>>>AWS CPU Utilization Alert Project<<<<<<<<<<<<<<<<<**
**Table of Contents
Overview
Prerequisites
Architecture**
**Steps to Create the Project**
Step 1: Set up EC2 Instance
Step 2: Set Up AWS CloudWatch Alarms
Step 3: Send Email Notification Using SNS
**AWS Services Used**
**Future Enhancements**
**Conclusion**
**1. Overview**
This project demonstrates how to set up an alert system on AWS to monitor CPU utilization. 
Using AWS CloudWatch and SNS, email notifications are sent when the CPU usage crosses a defined threshold, 
ensuring timely actions to prevent resource strain.

**2. Prerequisites**
AWS Account
IAM Role with permissions for EC2, CloudWatch, and SNS
Valid email address for receiving notifications
**3. Architecture**
EC2 Instance: Hosts the application.
CloudWatch Alarm: Monitors CPU utilization.
SNS: Sends email notifications when an alarm is triggered.
**4. Steps to Create the Project**
****Step 1: Set Up EC2 Instance****
Create a new EC2 instance (t2.micro) or use an existing one.
Attach security groups, VPC, and key pair as required.
Launch the instance.
****Step 2: Set Up AWS CloudWatch Alarms****
Open CloudWatch and go to Alarms.
Select the EC2 instance, choose CPU Utilization, and set the threshold (e.g., 50%).
Link this alarm to the SNS topic created in Step 3.
****Step 3: Send Email Notification Using SNS****
Go to SNS and create a new topic (e.g., SendEmailTopic).
Subscribe your email to the topic.
Confirm the subscription through the email notification you receive.
**5. AWS Services Used**
Amazon EC2: Hosts the monitored instance.
AWS CloudWatch: Monitors the system's performance.
AWS SNS: Sends email notifications when thresholds are crossed.
**6. Future Enhancements**
Implement auto-scaling to automatically adjust resources based on CPU utilization.
Extend monitoring to additional metrics or integrate with Lambda for automated response actions.
**7. Conclusion**
This project sets up a simple yet effective CPU Utilization Alert System using AWS CloudWatch and SNS. It enables timely monitoring and notification of CPU spikes, ensuring system performance and stability.

