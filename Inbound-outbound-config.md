# Configuring Inbound Rules for AWS Security Groups

This guide will walk you through the process of configuring inbound rules for AWS Security Groups to allow traffic on specific ports, including additional ports like 3001 and 3002.

## Prerequisites

1. An AWS account with necessary permissions to manage security groups.
2. Basic understanding of AWS services.

## Step 1: Accessing the AWS Management Console

1. Log in to your AWS Management Console.

## Step 2: Navigating to the EC2 Dashboard

1. Navigate to the EC2 Dashboard.

## Step 3: Selecting Security Groups

1. In the EC2 Dashboard, locate and click on "Security Groups" under the "Network & Security" section.

## Step 4: Selecting the Security Group to Modify

1. Select the appropriate security group associated with your EC2 instance by clicking on its name.

## Step 5: Adding Inbound Rules

1. In the "Inbound Rules" tab, click on "Edit inbound rules."

2. Click on "Add rule."

3. Configure the inbound rule:

   - Type: Select the protocol (e.g., TCP).
   - Port Range: Specify the port or port range you want to open (e.g., 3001-3002).
   - Source: Enter the IP address range or source from which traffic is allowed (e.g., 0.0.0.0/0 for all IPv4 addresses).

4. Click on "Save rules."

## Step 6: Verifying Inbound Rules

1. After saving the rules, ensure that the new inbound rules are correctly configured by reviewing the list of inbound rules for the security group.

## Step 7: Testing the Configuration

1. Test the configuration by attempting to access the specified ports from an external source.

## Step 8: Monitoring and Maintenance

1. Regularly review and update your security group rules as needed to ensure the security of your resources.

## Additional Notes

- Repeat the steps above to add inbound rules for other ports as required, such as 3001, 3002, etc.
- Ensure that you only open ports that are necessary for your application to minimize exposure to potential security threats.

You have successfully configured inbound rules for AWS Security Groups to allow traffic on specific ports, including additional ports like 3001 and 3002.
