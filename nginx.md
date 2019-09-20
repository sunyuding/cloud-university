# Nginx
(Course) Nginx Fundamentals - https://www.udemy.com/nginx-fundamentals/

## Load Balancing
Readmore: https://docs.nginx.com/nginx/admin-guide/load-balancer/http-load-balancer/

```bash
$ cd /etc/nginx/conf.d/
```

### Proxying HTTP Traffic to a Group of Servers
First you need to define the group with the upstream `directive`. The directive is placed in the `http` context. Servers in the group are configured using the `server` directive (not to be confused with the `server` block that defines a virtual server running on NGINX).

```bash
http {
    upstream backend {
        server backend1.example.com weight=5;
        server backend2.example.com;
        server 192.0.0.1 backup;
    }

    server {
        location / {
            proxy_pass http://backend;
        }
    }
}
```

The name of the group is specified in the `proxy_pass` directive. In the example, a virtual server running on NGINX passes al requests to the `backend` upstream group defined in the previous example. 

### Choosing a Load-Balancing Method
NGINX open source supports 4 load‑balancing methods, and NGINX Plus adds 2 more methods:

1. Round Robin
    - Default
    - Distributed evenly

2. Least Connections
    - A request is sent to the server with the least number of active connections
    - `least_conn`

3. IP Hash
    - `ip_hash`

4. Generic Hash
    - `hash $request_uri consistent`

5. Least Time (NGINX Plus only) 

6. Random

### Server Weights
```bash
upstream backend {
    server backend1.example.com weight=5;
    server backend2.example.com;
    server 192.0.0.1 backup;
}
```
In the example, **backend1.example.com** has weight 5; the other two servers have the default weight (1), but the one with IP address 192.0.0.1 is marked as a backup server and does not receive requests unless both of the other servers are unavailable. With this configuration of weights, out of every 6 requests, 5 are sent to **backend1.example.com** and 1 to **backend2.example.com**.

