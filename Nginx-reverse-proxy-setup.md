# Nginx Reverse Setup Guide

## This guide will provide instruction how server project on PORT with proxy_pass


### Nginx config code demo
```bash
server {
    listen 80;
    server_name _;

    # First please go through below instructions.
        # - required to add permission to serve static files from /home/ubuntu.
        # - Check you user of nginx

    # check user:
    grep -E 'user|group' /etc/nginx/nginx.conf
    # mostly you will get www-data [make sure, required for next step]

    # provide permissions
    sudo chown -R www-data:www-data /home/ubuntu
    sudo chmod -R 755 /home/ubuntu

    # how to change permission to provide back to ubuntu
    sudo chown -R ubuntu:ubuntu /home/ubuntu


    # react app - serving using static files - [1]
    location / {
        root /home/ubuntu/my-app/build;
    }

    # if serving form other than root(/) - [2]
    location /frontend {
        # use alias instead of root
        alias /home/ubuntu/my-app/build;
    }

    # express app with port(but always use production ready [build folder])
    location / {
        # dummy proxy_pass
        # localhost and port on which app is running
        proxy_pass http://127.0.0.1:8000;
   }

    # express app 
    location / {
        proxy_pass http://127.0.0.1:8000;
   }
}
```

This setup will server app on PORT 80, which will be running on PORT 3000