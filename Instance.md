# Setting Up AWS Ubuntu Cloud Instance

This guide will walk you through the process of setting up an AWS Ubuntu Cloud Instance, configuring the PEM key for SSH access, and enabling inbound rules for ports 80, 443, 3000, and 3001.

## Prerequisites

1. An AWS account with necessary permissions to create and manage EC2 instances.
2. Basic knowledge of AWS services.
3. Basic understanding of SSH and security groups.

## Step 1: Launching an EC2 Instance

1. Log in to your AWS Management Console.
2. Navigate to the EC2 Dashboard.
3. Click on the "Launch Instance" button.
4. Choose an Amazon Machine Image (AMI), preferably Ubuntu Server.
5. Select an Instance Type according to your requirements.
6. Configure Instance Details, such as instance number, network settings, etc.
7. Add storage and configure any additional options if necessary.
8. Add Tags for easy identification.
9. Configure Security Group:
   - Click on "Review and Launch."
   - Click on "Edit security groups."
   - Add rules for ports 80, 443, 3000, and 3001 with source set to `0.0.0.0/0`.
   - Review and launch the instance.

## Step 2: PEM Key Setup

1. During the instance creation process, or if you already have an instance running, ensure you have a PEM key associated.
2. If not, create a new key pair:
   - In the EC2 Dashboard, go to "Key Pairs" under "Network & Security."
   - Click on "Create Key Pair."
   - Provide a name for your key pair and download the PEM file.
   - Keep this PEM file safe, as it will be used for SSH access to your instance.
