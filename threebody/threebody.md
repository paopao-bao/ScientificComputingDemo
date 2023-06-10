### Intro
The client demo writen in Python.   
用python写的示例程序  
|filename | comments|
|:---|:---|
|threeBodyClient-Chinese.ipynb | 中文版 |
|not done yet | English version |

### Prerequisites
The "threebody_simulation" backend service is running on a container. （You can pull the docker image from Docker Hub and run it locally or on cloud; the image name is "threebody_simulation".）   
需要在容器上运行threebody_simulation后端服务。（从docker hub上pull来镜像，在本机或云上运行；镜像的名字是threebody_simulation。）  

### P.S. Recipe for the backend service  
后端服务使用方法  
1, Start docker, and pull the image from docker hub. 启动docker后拉下镜像。
*docker pull threebody_simulation*

2, Run the image in the background. 在后台运行镜像。
*docker run -d threebody_simulation /home/exeTB1/bin/threeBody*

3, Test the service. 测试。
*curl -X POST -i 'http://172.17.0.2:8080/threebody/' --data '{"duration":10.0, "dt":0.01, "m1":1.0, "x1":-1.0, "y1":0.0, "vx1":0.3471168881, "vy1":0.5327249454, "m2":1.0, "x2":1.0, "y2":0.0, "vx2":0.3471168881, "vy2":0.5327249454, "m3":1.0, "x3":0.0, "y3":0.0, "vx3":-0.6942337762, "vy3":-1.0654498908}'*
Remember to replace the 172.17.0.2 with the container IP address.记得把172.17.0.2替换成容器的IP。

