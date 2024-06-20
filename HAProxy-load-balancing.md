# How to setup load balancing with HAProxy

## This guide will provide you step by step instruction how to setup load balancing with HAProxy

### Open the HAProxy configuration file:

1. Navigate:

```bash
    sudo nano /etc/haproxy/haproxy.cfg
```

2. Update file [after defaults]

```bash
frontend http_front
    bind *:80
    default_backend express_backend

backend express_backend
    balance roundrobin
    # server 1: you server(prefered provide localhost ip)
    server express_server1 127.0.0.1:3000 check
    # sever 2: 
    server express_server2 43.205.233.137:80 check
    # sever 3: 
    server express_server3 59.205.233.786:80 check
```
