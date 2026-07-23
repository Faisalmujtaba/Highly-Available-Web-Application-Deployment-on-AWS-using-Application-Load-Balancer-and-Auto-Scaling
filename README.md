Highly Available Web Application Deployment on AWS using Application Load Balancer and Auto Scaling

Project Overview
This project demonstrates the deployment of a highly available and scalable web application infrastructure on Amazon Web Services (AWS). The architecture utilizes a custom Virtual Private Cloud (VPC), multiple public subnets across different Availability Zones, EC2 instances running Apache Web Server, an Application Load Balancer (ALB), Launch Templates, and an Auto Scaling Group (ASG).

The primary objective of this project is to implement a fault-tolerant and highly available web application architecture capable of automatically distributing incoming traffic, replacing unhealthy instances, and maintaining application availability during failures.


Project Objectives
- Design a custom AWS Virtual Private Cloud (VPC)
- Deploy EC2 instances across multiple Availability Zones
- Configure Internet Gateway and Route Tables
- Secure infrastructure using Security Groups
- Automate Apache installation using EC2 User Data
- Configure an Application Load Balancer
- Implement Target Groups with Health Checks
- Deploy Auto Scaling Group for automatic instance replacement
- Demonstrate High Availability and Fault Tolerance

 AWS Services Used
Service 	Purpose 
Amazon EC2 	Virtual Web Servers 
Amazon VPC	Isolated Network Infrastructure 
Public Subnets	High Availability Deployment 
Internet Gateway	 Internet Connectivity 
Route Tables 	Traffic Routing 
Security Groups 	 Firewall Rules 
Application Load Balancer 	Traffic Distribution 
Target Groups 	Load Balancer Targets 
Launch Templates 	Instance Configuration 
Auto Scaling Group	Automatic Scaling & Self-Healing 
EC2 User Data 	Automated Apache Installation 

Project Workflow
1. Created a custom VPC
2. Created two Public Subnets
3. Attached Internet Gateway
4. Configured Route Tables
5. Created Security Groups
6. Launched EC2 Instance 1
7. Installed Apache using User Data
8. Launched EC2 Instance 2
9. Created Target Group
10. Configured Application Load Balancer
11. Verified Load Balancer functionality
12. Created Launch Template
13. Created Auto Scaling Group
14. Attached Auto Scaling Group to Target Group
15. Verified High Availability and Load Balancing


User Data Script

```bash
#!/bin/bash
apt update -y
apt install apache2 -y
systemctl enable apache2
systemctl start apache2

HOST=$(hostname)

cat <<EOF >/var/www/html/index.html
<html>
<head>
<title>AWS ELB Project</title>
</head>
<body style="font-family:Arial;text-align:center;margin-top:80px;">
<h1>AWS Elastic Load Balancer Project</h1>
<h2>Apache Web Server</h2>
<h3>$HOST</h3>
<p>Instance deployed automatically using EC2 User Data.</p>
</body>
</html>
EOF
```

High Availability Demonstration
The Application Load Balancer distributes incoming HTTP requests across multiple EC2 instances deployed in separate Availability Zones.
The Auto Scaling Group continuously monitors instance health. If an EC2 instance becomes unhealthy or is terminated, Auto Scaling automatically launches a replacement instance using the predefined Launch Template, ensuring uninterrupted service availability.


Testing Performed
✔ Verified Internet connectivity

✔ Verified Apache installation

✔ Verified EC2 accessibility

✔ Verified ALB DNS accessibility

✔ Verified Target Group Health Checks

✔ Verified Load Balancer traffic distribution

✔ Verified Auto Scaling Group instance creation

✔ Verified automatic replacement of unhealthy instances


 Skills Demonstrated
- Amazon Web Services (AWS)
- Cloud Infrastructure Design
- Virtual Private Cloud (VPC)
- EC2 Administration
- Linux System Administration
- Apache Web Server
- Elastic Load Balancer (ALB)
- Target Groups
- Auto Scaling Groups
- Launch Templates
- Security Groups
- Route Tables
- Internet Gateway
- User Data Automation
- High Availability
- Fault Tolerance
- Infrastructure as a Service (IaaS)

 Project Outcome
Successfully designed and deployed a highly available, scalable, and fault-tolerant web application infrastructure on AWS capable of distributing incoming traffic, monitoring application health, and automatically replacing failed instances using Auto Scaling.

Future Improvements
- HTTPS using AWS Certificate Manager (ACM)
- Amazon Route 53 Custom Domain
- CloudWatch Dashboard
- CloudWatch Alarms
- SNS Email Notifications
- Private Subnets
- NAT Gateway
- AWS WAF
- Terraform Automation
- CI/CD using GitHub Actions
