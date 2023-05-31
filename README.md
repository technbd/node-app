# Node JS Application: </br>
This demo purpose for node.js based apps. Uses in Docker to setup a node.js and loadbalancing using HAproxy.
# Prerequisites: </br>
1. Docker installed
2. HAproxy installed

# Build Docker Image: </br>
- Expose the application in 9999 port.
- env: APPID=your_value
```
# docker build -t nodeapp .
# docker images
```
# Create Docker Container: </br> 
```
# docker run --name nodeapp1 -dit -p 2222:9999 -e APPID=2222 nodeapp
  
# docker run --name nodeapp2 -dit -p 3333:9999 -e APPID=3333 nodeapp
  
# docker run --name nodeapp3 -dit -p 4444:9999 -e APPID=4444 nodeapp
  
# docker run --name nodeapp4 -dit -p 5555:9999 -e APPID=5555 nodeapp
```

`Verify:`  
---
```
# docker ps

curl your_host_ip:2222
curl your_host_ip:2222/app1
curl your_host_ip:2222/app2
curl your_host_ip:2222/admin

```

# Configure HAproxy: </br>
__haproxy.cfg__

- Verify after proxy configure:
```
http://your_host_ip/
http://your_host_ip/app1
http://your_host_ip/app2
```

`Links:`
---
[Github](https://github.com/technbd?tab=repositories)




