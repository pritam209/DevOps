# How to setup reverse proxy with HAProxy

## This guide will provide you step by step instruction how to setup reverse proxy with HAProxy

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
    server express_server ip:port check
```

This config will serve on PORT 80, running on port e.g.3000