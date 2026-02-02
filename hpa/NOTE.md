## HPA

`HPA` stands for Horizontal Pod Autoscaler

used to automatically scale up or scale down the pod based on memory and cpu comsumption.

→ Tool needed

`Apache Benchmark` used for load testing

```bash
sudo apt update
sudo apt install apache2-utils -y

# ab -n 10000 -c 10000 http://10.233.9.141/ # sending 10000 requests
```

resources:

- **limits**: max of resource which container can use
- **requests**: min of resource which container request for using in order to run service smoothly.
    - inside both
        - CPU
        - Memory