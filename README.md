# Getting Started

Create a basic Spring Boot app using Docker and Kubernetes


## Prerequisites
* JDK 8 or higher (Please ensure you have a JDK installed and not just a JRE)
* [Docker](https://docs.docker.com/install/) installed
* [Kubectl](https://kubernetes.io/docs/tasks/tools/install-kubectl/) installed

### Run the App
In the terminal window run

```
$ ./mvnw spring-boot:run
```

or if you prefer use maven 
```
$ mvn package
$ java -jar target/<JAR FILE>.jar
```


### Test the App
Make an HTTP request to http://localhost:8080 in another terminal 
```
$ curl http://localhost:8080; echo
Hello World
```

or you can put the URL in the web bowser

### Building A Container
* You must need installed Docker
Spring Boot 2.3.x can build a container for you without the need for any additional plugins or files

* To do this use the Spring Boot Build plugin goal build-image
```
$ ./mvnw spring-boot:build-image
```

* Running docker images will allow you to see the built container
```
$ docker images
REPOSITORY                            TAG                 IMAGE ID            CREATED             SIZE
k8s-demo-app                          0.0.1-SNAPSHOT      ab449be57b9d        5 minutes ago       124MB
```

### Run the Container
```
$ docker run --name k8s-demo-app -p 8080:8080 k8s-demo-app:0.0.1-SNAPSHOT
```


### Test The App Responds
In the terminal window run
```
$ curl http://localhost:8080; echo
Hello World
```
or you can write the URL (http://localhost:8080) in a web bowser





