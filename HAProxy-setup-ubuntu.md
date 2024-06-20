# HAProxy Setup.

# This guide will provide you step by step instruction how to setup HAProxy

1. Step 1: Update the Package List

```bash
sudo apt update
```

2. Step 2: Install HAProxy

```bash
sudo apt install haproxy -y
```

3. Start HAProxy

```bash
sudo systemctl start haproxy
```

4. enable, stop, status, reload
```bash
# auto start on server reboot
sudo systemctl enable haproxy
sudo systemctl stop haproxy
sudo systemctl status haproxy
sudo systemctl reload haproxy
```