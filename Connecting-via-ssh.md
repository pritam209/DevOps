# Connecting Instance using SSH

## Step 1: Connecting to the Instance via SSH

1. Open your terminal (or command prompt) or Git Bash depending on your operating system:

   - For Windows users using Git Bash:
     - Open Git Bash.
   - For macOS and Linux users:
     - Open your terminal.

2. Navigate to the directory containing your PEM key file.

3. Set permissions for your PEM key file:

   ```
   chmod 400 your-key.pem
   ```

4. Connect to your instance using SSH:

   ```
   ssh -i your-key.pem ubuntu@your-instance-public-ip
   ```

   Replace `your-key.pem` with the name of your PEM key file and `your-instance-public-ip` with the public IP address of your AWS instance.

5. You are now connected to your AWS Ubuntu instance.

## Step 2: Updating and Installing Necessary Packages

1. Update package lists to ensure you have the latest versions:
   ```
   sudo apt update
   sudo apt upgrade
   ```
2. Install any necessary packages based on your requirements.

## Step 3: Setting up your Application

1. Proceed with setting up your application, database, server, etc., based on your project requirements.

You have successfully set up an AWS Ubuntu Cloud Instance, configured the PEM key for SSH access, and enabled inbound rules for ports 80, 443, 3000, and 3001. You can now deploy and manage your applications on this instance.
