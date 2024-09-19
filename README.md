# AWS CPU Utilization Alert Project #

# Overview
This project demonstrates how to set up an automated alert system for monitoring CPU utilization on an AWS EC2 instance using AWS CloudWatch and AWS SNS (Simple Notification Service). 
The system sends email notifications when CPU utilization exceeds a specified threshold, enabling teams to take immediate action to prevent system strain or potential failure.

# Prerequisites
Before starting the project, ensure that the following prerequisites are met:

An active AWS Account.
IAM Role with necessary permissions for EC2, CloudWatch, and SNS.
AWS CLI installed (optional, for local setup and configuration).
A valid email address to receive notifications.

# Architecture
The architecture consists of three main components:

EC2 Instance: Hosts the application you are monitoring.
CloudWatch: Monitors CPU utilization and sets up alarms based on defined thresholds.
SNS: Sends an email notification to the subscribed users when the CloudWatch alarm is triggered.


# ![AWS Architecture Diagram](https://github.com/user-attachments/assets/71132a2d-e1b4-4873-b319-fb1e6fffc891)

# Workflow:

CPU Utilization crosses the defined threshold.
CloudWatch triggers an alarm.
The alarm notifies an SNS Topic.
SNS sends an email notification to the subscribed email addresses.

# Steps to Create the Project
**Step 1: Set Up EC2 Instance**

Launch an EC2 instance from the AWS Management Console.
Instance Name: Web Server Node 1 (and Web Server Node 2 for load testing).
Instance Type: t2.micro.
Key Pair: Use an existing key pair or create a new one.
VPC: Select an existing VPC.
Security Group: Attach an existing security group that allows HTTP traffic.
Click Launch Instance.
