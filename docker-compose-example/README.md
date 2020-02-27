#  DevOps Challenge 

 This repository is used to run nodejs application using docker and docker-compose. It uses the official Node.js Docker image and alpine nginx docker image for proxy passing.

## Prerequisite

 *  [docker](https://docs.docker.com)
 *  [docker-compose](https://docs.docker.com/compose/)

## How to build and run the containers

```
git clone https://bitbucket.org/jithinbabusbce/interview-docker.git
cd interview-docker
docker-compose up -d
```

## Access the api
```
https://localhost/hello
```

## Why this solution
I used docker and docker-compose for solving this problem
 
* ### Why docker
Docker is an open-source platform that allows isolating the apps within code containers. This is often described as "lightweight," because it simply provides containers within the host machine's operating system. Docker containers hold an application's components, including binaries, libraries, and configurations, as well as the application's dependencies. So this can be deployed anywhere on the host where docker is installed.
* ### Why docker-compose
The main advantage is that docker-compose keeps track of the containers. If you re-run “docker-compose up -d” without changes it won’t try to recreate any containers. If on the other hand you change a service a “docker-compose up -d” will recreate only that service and any service that depends on it. Doing something similar in a bash-script is quite difficult. Additionally it is a standardized and very readable format