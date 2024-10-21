# AWS CPU Utilization Alert Project #

# Overview
This project demonstrates how to set up an automated alert system for monitoring CPU utilization on an **AWS EC2** instance using **AWS CloudWatch** and **AWS SNS (Simple Notification Service)**. 
The system sends email notifications when CPU utilization exceeds a specified threshold, enabling teams to take immediate action to prevent system strain or potential failure.

## Prerequisites
**Before starting the project, ensure that the following prerequisites are met:**

   1. An active **AWS Account**.
   2. **IAM Role** with necessary permissions for EC2, CloudWatch, and SNS.
   3. **AWS CLI** installed (optional, for local setup and configuration).
   4. A valid **email address** to receive notifications.

## Architecture
**The architecture consists of three main components:**

   1. **EC2 Instance:** Hosts the application you are monitoring.

   2. **CloudWatch:** Monitors CPU utilization and sets up alarms based on defined thresholds.

   3. **SNS:** Sends an email notification to the subscribed users when the CloudWatch alarm is triggered.


# ![AWS Architecture Diagram.gif](https://github.com/cbelose/-AWS-CPU-Utilization-Alert-Project-/blob/2ed71af34bf113dbb834efa4c499d6e756d32790/AWS%20Architecture%20Diagram.gif)

## Workflow:

CPU Utilization crosses the defined threshold.
CloudWatch triggers an alarm.
The alarm notifies an SNS Topic.
SNS sends an email notification to the subscribed email addresses.

## Steps to Create the Project
**Step 1: Set Up EC2 Instance**

1. Launch an EC2 instance from the AWS Management Console.
   1. **Instance Name:** Web Server Node 1 (and Web Server Node 2 for load testing).
   
   2. **Instance Type:** t2.micro.
   
   3. **Key Pair:** Use an existing key pair or create a new one.
   
   4. **VPC:** Select an existing VPC.
   
   5. **Security Group:** Attach an existing security group that allows HTTP traffic.
   
2. Click **Launch Instance**.
   
**Step 2: Configure SNS for Email Notifications**

   1. Open SNS (Simple Notification Service) in the AWS Console.

   2. Create a new SNS topic (e.g.,**SendEmailTopic**).

   3. Under **Access Policy**, allow **Publishers: Everyone** to send messages.

   4. Subscribe your email address to the topic:

      1. **Protocol**: Select **Email**.

      2. Enter your **email address** to receive alerts.

      3. Confirm the subscription via email to start receiving notifications.

**Step 3: Set Up CloudWatch Alarms**

   1. Go to AWS CloudWatch in the AWS Console.

   2. Navigate to **Alarms** and click **Create Alarm**.

   3. Select the EC2 instance you want to monitor.

   4. Click **Select Metric > EC2 > Per-Instance Metrics > CPU Utilization.**

   5. Set the CPU utilization threshold (e.g., 50%).

   6. Define the condition: Trigger the alarm if CPU utilization is greater than 50% for a specified period.

   7. Choose the existing SNS Topic (SendEmailTopic) to send the notification.

   8. Click **Create Alarm**.

**Step 4: Apply Load to Test the System**

   1. SSH into the EC2 instance (Web Server Node 1 or 2).

   2. Use the following commands to apply CPU load

   3. Monitor CPU utilization in CloudWatch. Once it crosses the defined threshold, you will receive an email alert from SNS.

**Step 5: Monitor CloudWatch and Receive Alerts**

   1. Once CPU utilization crosses the threshold, CloudWatch will update the alarm status to **"In Alarm"**, and you will receive an email notification.

   2. You can then take appropriate actions, such as stopping the instance or scaling resources.

## AWS Services Used
**Amazon EC2:** Hosts the application and provides infrastructure for monitoring.

**Amazon CloudWatch:** Monitors CPU utilization and triggers alarms.

**Amazon SNS:** Sends email notifications to subscribed users when the CloudWatch alarm is triggered.

## Future Enhancements
**The project can be enhanced with the following features:**

   1. Implement **Auto Scaling** to automatically adjust resources based on CPU utilization.

   2. Add more advanced monitoring metrics, such as memory and disk usage, using **CloudWatch Logs** and **Custom Metrics**.

   3. Integrate with other AWS services for better automation and scalability.

## Conclusion
This project demonstrates how to create a CPU utilization alert system using AWS CloudWatch and SNS. 
The setup ensures that administrators are notified when resource usage exceeds a defined threshold, helping to maintain system performance and prevent overloads. 
With future enhancements, this solution can be further extended to dynamically scale resources and provide deeper insights into the health of the system.
