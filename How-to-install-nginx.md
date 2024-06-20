# How to install nginx on ubuntu

## This guide will provide step by step instruction how to install nginx on ubuntu

1. Update Package Lists
```bash
sudo apt update
```

2. Install Nginx
```bash
sudo apt install nginx
```

3. Start nginx
```bash
sudo systemctl start nginx
```

4. enable, stop, status, reload
```bash
# auto start on server reboot
sudo systemctl enable nginx
sudo systemctl stop nginx
sudo systemctl status nginx
sudo systemctl reload nginx
```
