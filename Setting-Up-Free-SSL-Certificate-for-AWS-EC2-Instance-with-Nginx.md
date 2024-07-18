# This guide will walk you through the steps to set up an SSL certificate on an AWS EC2 instance using Nginx.

- Step 1: Connect to Your EC2 Instance

```bash
ssh -i your-key.pem ubuntu@your-ec2-ip
```

-  Step 2: Install Snapd

```bash
sudo apt update
```

```bash
sudo apt install snapd
```

- Step 3: Install Certbot

```bash
sudo snap install --classic certbot
```

- Step 4: Prepare Certbot

```bash
sudo ln -s /snap/bin/certbot /usr/bin/certbot
```

Step 5: Configure of Nginx

```bash
sudo certbot --nginx 
```

- Step 6: Add Domain

```bash
sudo certbot --nginx -d yourDomainName.com -d www.yourDomainName.com
```

- Step 7: Add auto-renew (After 90 days)

```bash
sudo certbot renew --dry-run
```

- Step 8: Restart Nginx

```bash
sudo systemctl restart nginx
```