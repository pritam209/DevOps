# Setting Up Node.js with NVM on an Amazon EC2 Instance

This guide will walk you through the process of setting up Node.js using NVM (Node Version Manager) on an Amazon EC2 Instance, covering different instance types and their respective usernames.

## Prerequisites

1. An AWS account with necessary permissions to create and manage EC2 instances.
2. Basic knowledge of AWS services.

## Step 1: Launching an EC2 Instance

1. Log in to your AWS Management Console.
2. Navigate to the EC2 Dashboard.
3. Click on the "Launch Instance" button.
4. Choose an Amazon Machine Image (AMI):
   - Select an AMI that suits your requirements. For Node.js applications, you can choose an AMI with Ubuntu Server or Amazon Linux.
5. Select an Instance Type according to your requirements.
6. Configure Instance Details, such as instance number, network settings, etc.
7. Add storage and configure any additional options if necessary.
8. Add Tags for easy identification.
9. Configure Security Group:
   - Click on "Review and Launch."
   - Click on "Edit security groups."
   - Add rules for SSH (port 22) and any other ports required for your Node.js application.
   - Review and launch the instance.

## Step 2: Connecting to the Instance via SSH

1. Open your terminal or command prompt.
2. Navigate to the directory containing your PEM key file.
3. Set permissions for your PEM key file:

```
chmod 400 your-key.pem
```

4. Connect to your instance using SSH:

| AMI Type       | User Name          |
| -------------- | ------------------ |
| Amazon Linux 2 | ec2-user           |
| CentOS         | centos or ec2-user |
| Debian         | admin              |
| Fedora         | fedora or ec2-user |
| RHEL           | ec2-user or root   |
| SUSE           | ec2-user or root   |
| Ubuntu         | ubuntu             |
| Oracle         | ec2-user           |
| Bitnami        | bitnami            |

- For Ubuntu instances:
  ```
  ssh -i your-key.pem ubuntu@your-instance-public-ip
  ```
- For Amazon Linux instances:
  ```
  ssh -i your-key.pem ec2-user@your-instance-public-ip
  ```
  Replace `your-key.pem` with the name of your PEM key file and `your-instance-public-ip` with the public IP address of your AWS instance.

5. You are now connected to your EC2 instance.

## Step 3: Installing NVM (Node Version Manager)

1. Install NVM using the following commands:

```
curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.1/install.sh | bash
```

2. Close and reopen your terminal to start using NVM or run the following command to source the NVM script:

```
source ~/.bashrc
```

4. Install NodeJS LTS(Long term support) version

```
nvm install --lts
```

3. Test if NodeJS in installed

```
node -v

or

node -e "console.log('Running Node.js ' + process.version)"
```

3. Install `pnpm`

```
npm install pnpm -g
```

## Step 4: Setting Up Your Node.js Application

1. Proceed with setting up your Node.js application as per your project requirements.

## Step 5: Additional Configuration and Maintenance

1. Configure any additional settings required for your Node.js application, such as environment variables, databases, etc.
2. Regularly update your EC2 instance and Node.js packages to ensure security and stability.

## Note:

- For Ubuntu instances, the default username is `ubuntu`.
- For Amazon Linux instances, the default username is `ec2-user`.

You have successfully set up Node.js with NVM on an Amazon EC2 Instance. You can now deploy and manage your Node.js applications on this instance.
