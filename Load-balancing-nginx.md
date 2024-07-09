# How to load balancing with Nginx

## This guide will provide you step by step instruction how to do load balancing with Nginx.

1. Step 1
### /etc/nginx/nginx.config(probably)

```bash
# inside http
http{
    # code goes here
    # provide upstream
    upstream demo {
    server 7.36.540.1;
    server 7.36.540.1;
    # prefered to use localhost if load balacing in same server
    server localhost_ip:port;
    }
}
```

2. Step 2
### /etc/nginx/sites-available/yourfile(probably)

```bash
server {
    listen 80;
    server_name _;

    location / {
        proxy_pass http://demo;
        }
}
```
