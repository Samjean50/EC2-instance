## Creating an EC2 Instance

### Project Overview

#### Purpose

In this project i will be setting up an Amazon EC2 instance, which serves as a cloud-based Linux server. i will launch, configure, and access an EC2 instance on AWS, supporting cloud-based development, hosting, and server management.

#### Requirements

It includes the following:

- Cloud Computing Environment:

  - Amazon Web Services (AWS) account

  - Amazon EC2 instance setup

- Server Configuration:

    - Secure Shell (SSH) access setup

    - Elastic IP configuration (optional)

- Software Management:

    - Updating and installing necessary packages on the server


### Use Case

This is useful for developers, DevOps engineers, and cloud computing enthusiasts who need a scalable and secure Linux server in the cloud. By setting up an EC2 instance, i can:

- Deploy and manage cloud-based applications.

- Remotely access and configure a Linux server.

- Host websites and services with AWS infrastructure.

### 1. Creating an AWS EC2 Instance

#### Steps to Launch an EC2 Instance

1. Sign in to AWS Console:

- I navigated to AWS Console.

- Logged into my AWS account.

2. Open EC2 Dashboard:

- In the AWS Management Console, i searched for EC2.

- Clicked Instances > Launch Instance.
![New-instance](images/new-instance.png)

3. Choose an Amazon Machine Image (AMI):

- I selected Ubuntu 20.04 as the preferred AMI.

4. Choose an Instance Type:

- I selected t2.micro (eligible for free tier).

Configure Instance Details:

- I left the default settings.

5. Add Storage:

- I used te default 8GB root volume as it is sufficient.

6. Configure Security Group:

- I allowed SSH (port 22) from my IP for secure access.

- (Optional) Allow HTTP (port 80) and HTTPS (port 443) if hosting a website.

7. Create or Select an SSH Key Pair:

- I selected and created a new key pair.

- Downloaded the .pem file and saved it securely.
![Launch-instance](images/launch-instance.png)

8. Launch the Instance:

- Clicked Launch Instance and waited for the status to change to "Running".
![suceess](images/launch-succes.png)

#### Troubleshooting

- Cannot connect via SSH? Ensure that port 22 is open in the security group.

- Instance not launching? Check AWS region settings and instance limits.

### 2. Connecting to EC2 via SSH

#### Steps to Connect to EC2 Instance

1. Find Public IP:

- In the EC2 dashboard, i selected the running instance and noted the Public IPv4 Address.
 ![suceess](images/public-ip.png)

- Set Permissions for SSH Key:

2. Ran the following command in my terminal:

```chmod 400 your-key.pem```

3. Connect Using SSH:

Used the following command:

```ssh -i your-key.pem ubuntu@your-public-ip```

#### Troubleshooting

- Permission denied? Ensure the key has correct permissions (chmod 400 your-key.pem).

- Host unreachable? Verify that your instance is running and security groups allow SSH access.

### 3. Configuring the EC2 Instance

- Update System Packages

Ran the following commands after connecting to the instance:

```sudo apt update -y   # For Ubuntu```

- Install Common Utilities
```sudo apt install -y git wget unzip```
```sudo apt install tree```


#### Troubleshooting

Packages not installing? Check internet connectivity from the instance.

Web server not accessible? Ensure security group allows HTTP/HTTPS traffic.

### Conclusion

I have successfully created, connected to, and configured an AWS EC2 instance. This server can now be used for hosting applications, managing cloud-based workloads, and running development environments. Ensuring security and proper configurations will help maintain a reliable cloud-based server setup.

