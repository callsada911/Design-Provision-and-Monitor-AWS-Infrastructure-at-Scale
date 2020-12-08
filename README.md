# Design-Provision-and-Monitor-AWS-Infrastructure-at-Scale
AWS Udiacty project 
plan, design, provision, and monitor infrastructure in AWS using industry-standard and open source tools. You will practice the skills you have learned throughout the course to optimize infrastructure for cost and performance. You will also use Terraform to provision and configure AWS services in a global configuration.
Project Requirments:
Create AWS Architecture Schematics
Part 1
You have been asked to plan and provision a cost-effective AWS infrastructure for a new social media application development project for 50,000 single-region users. The project requires the following AWS infrastructure and services. Please include your name and label all elements of the infrastructure on the diagram.

Infrastructure in the following regions: us-east-1
Users and Client machines
One VPC
Two Availability Zones
Four Subnets (2 Public, 2 Private)
A NAT Gateway
A CloudFront distribution with an S3 bucket
Web servers in the Public Subnets sized according to your usage estimates
Application Servers in the Private Subnets sized according to your usage estimates
DB Servers in the Private Subnets
Web Servers Load Balanced and Autoscaled
Application Servers Load Balanced and Autoscaled
A Master DB in AZ1 with a read replica in AZ2
Use LucidChart or a similar diagramming application to create your schematic. Export your schematic as a PDF and save as Udacity_Diagram_1.pdf.

Part 2
You have been asked to plan a SERVERLESS architecture schematic for a new application development project. The project requires the following AWS infrastructure and services.

A user and client machine
AWS Route 53
A CloudFront Distribution
AWS Cognito
AWS Lambda
API Gateway
DynamoDB
S3 Storage
Export your schematic as a PDF and save as Udacity_Diagram_2.pdf

Task 2: Calculate Infrastructure Costs
Use the AWS Pricing Calculator to estimate how much it will cost to run the services in your Part 1 diagram for one month.

Target a monthly estimate between $8,000-$10,000.
Be mindful of AWS regions when you are estimating costs.
Export the estimate as a CSV file named Initial_Cost_Estimate.csv.
Return to the AWS Pricing Calculator and reconfigure your estimates for the following scenarios:

Your budget has been reduced from $8,000-$10,000 to a maximum of $6,500. What services will you modify to meet this new budget? Export the updated costs in a CSV file named Reduced_Cost_Estimate.csv and write up a brief narrative of the changes you made in the CSV file below the cost estimate.

Your budget has been increased to $20,000. What resources will you add and why?
Think about where to add redundancy and how to improve performance. Re-configure your estimate to a monthly invoice of $18K-20K. Export the updated costs to a CSV file named Increased_Cost Estimate.csv and write up a brief narrative of the changes you made in the CSV file below the cost estimate.

Task 3: Configure Permissions.
In order to complete this task, please ensure your IAM users have been granted access to the billing dashboard (Activating Access to the Billing and Cost Management Console).

Update the AWS password policy.

Minimum password length = 8
Require at least one uppercase letter
Require at least one lowercase letter
Require at least one number
Require at least one non-alphanumeric character.
Submit a screenshot of the Password Policy from the IAM Account settings page. Name the screenshot udacity_password_policy.png or udacity_password_policy.jpg.

AWS Password Policy
Example AWS Password Policy

Create a Group named CloudTrailAdmins and give it the two CloudTrail privileges.

Create a Group named Reviewers and give it the Billing privilege.

Configure a user named CloudTrail and a user named Accountant. Give the users AWS Console access and assign them a password that conforms to your password policy. Require them to change their password when they login.

Assign CloudTrail to the CloudTrailAdmins group. Assign Accountant to the Reviewers group .

Test both user accounts by logging into the AWS console as the users CloudTrail and Accountant after changing their passwords on login. Login using your numerical AccountID

AWS Sign In
While logged-in as the user CloudTrail, go to the CloudTrail page and create a trail named Udacity_Trail. Enable logging on all Read/Writes Management Events and S3 and Lambda events Data Events. Create a new S3 Bucket to store the CloudTrail log. There is no need for advanced configuration.

Download the portion of the CloudTrail log that shows the entire Task 3 timeframe and save it as UdacityCloudTrailLog.csv.

Before Logging off, return to the CloudTrail configuration page. Disable S3 logging.
Are you sure you want to stop logging?
Are you sure you want to stop logging?

Task 4: Set up Cost Monitoring
Configure CloudWatch billing alarm

Set up a Billing alarm with a $5 threshold

Set up notification so that you get an email alert when the alarm is triggered.
Save a screenshot of the CloudWatch Alarms page showing the new alarm with a green OK status as CloudWatch_alarm.png or CloudWatch_alarm.jpg

Example CloudWatch Alarm
Example CloudWatch Alarm

Task 5 : Use Terraform to Provision AWS Infrastructure
Part 1
Download the starter code.
In the main.tf file write the code to provision

AWS as the cloud provider
Use an existing VPC ID
Use an existing public subnet
4 AWS t2.micro EC2 instances named Udacity T2
2 m4.large EC2 instances named Udacity M4
Run Terraform.

Take a screenshot of the 6 EC2 instances in the AWS console. Save it as Terraform_1_1.png or Terraform_1_1.jpg .
Use Terraform to delete the 2 m4.large instances.
Take an updated screenshot of the AWS console showing only the 4 t2.micro instances and save it as Terraform_1_2.png or Terraform_1_2.jpg
Part 2
In the Exercise_2 folder, write the code to deploy an AWS Lambda Function using Terraform. Your code should include:

A lambda.py file
A main.tf file
An outputs.tf file
A variables.tf file
Take a screenshot of the EC2 instances page and save it as Terraform_2_1.png or Terraform_2_1.jpg.

Take a screenshot of the VPC page and save it as Terraform_2_2.png or Terraform_2_2.jpg.
Take a screenshot of the CloudWatch log entry for the lambda function execution and save it as Terraform_2_3.png or Terraform_2_3.jpg.
Screenshot of CloudWatch entry
Example Screenshot of CloudWatch Entry

Task 6: Destroy the Infrastructure using Terraform and prepare for submission
Destroy all running provisioned infrastructure using Terraform so as not to incur unwanted charges.
Take a screenshot of the EC2 instances page and label it Terraform_destroyed.png or Terraform_destroyed.jpg .
Upload Terraform files, screenshots, schematics and CSV files to your GitHub repo
