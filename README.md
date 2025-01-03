docker::
FROM openjdk:8
EXPOSE 8080
ADD target/spring-docker-demo.jar spring-docker-demo.jar
ENTRYPOINT["java","-jar","/spring-docker-demo"]

<finalname>spring-docker-demo<finalname>

maven install

C:\Users\Boby Burman\OneDrive\Documents\Desktop\LearningQueue2025\OnlineShopingApplication\DockerDemo>dir
ren DockerFile Dockerfile
docker build -t spring-docker-demo.jar .
docker image ls
docker run -p 9090:8080 spring-docker-demo.jar

To get an IP of Docker Img::
docker ps
docker inspect c0b0daff2af5
docker inspect -f "{{range .NetworkSettings.Networks}}{{.IPAddress}}{{end}}" c0b0daff2af516ad6d3d05885402858d861d53986359918416137cc5d41e5ab4


push to docker hub creating repo::
docker image ls
docker tag spring-docker-demo.jar bobyburman/spring-docker-demo.jar
docker image ls
docker push bobyburman/spring-docker-demo.jar


pull from docker hub ::
docker pull bobyburman/spring-docker-demo.jar
docker run -p 9090:8080 bobyburman/spring-docker-demo.jar
