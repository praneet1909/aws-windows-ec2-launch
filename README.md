# aws-windows-ec2-launch
Step-by-step guide to launching a Windows Server EC2 instance on AWS, securing it with a restricted security group, and connecting via RDP. Includes screenshots, security tips, and cleanup steps.

# Launching a Windows EC2 Instance on AWS

## Overview
Step-by-step guide to launching a Windows Server EC2 instance and connecting via RDP.

## Prerequisites
- AWS account
- Key pair (.pem) created in the target region
- RDP client (Windows Remote Desktop / Microsoft Remote Desktop on Mac)

## Steps
1. Open EC2 Console > Launch Instance
2. Name the instance and choose a Windows Server AMI
3. Select instance type (e.g., t3.medium)
4. Select or create a key pair
5. Configure network: allow RDP (TCP 3389) from **My IP only**
6. Configure storage (default 30 GiB gp3)
7. Launch the instance
8. Select instance > Connect > RDP client > Get password (upload .pem)
9. Connect using the public IP, user `Administrator`, and the decrypted password

## Screenshots
1)Instance Dashboard

![Launch Instance](screenshot/1-launch-instance.png)
![AMI Page](screenshot/2-AMI.png)
![Instance Type](screenshot/3-Instance-type.png)
![Networking Page](screenshot/4-networking.png)
![Storage Config Page](screenshot/5-storage-config.png)
![Runnig Instance Page](screenshot/6-runnig-instance.png)
![Connection Method Page](screenshot/7-connection-method.png)
![Password Decrypt Page](screenshot/8-decrypt-pass.png)
![Runnig Windows Page](screenshot/9-windows-ec2.jpeg)


## Security Notes
- Never open 3389 to 0.0.0.0/0
- Never commit your .pem file (add `*.pem` to .gitignore)
- Stop or terminate the instance when done to avoid charges

## Cleanup
Terminate the instance and delete unused volumes and Elastic IPs.
