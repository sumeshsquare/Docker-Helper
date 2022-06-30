### Jenkins using docker
docker run -it -p 8080:8080 -p 50000:50000 -v /home/sumesh/Sumesh/Jenkins:/var/jenkins_home -v /var/run/docker.sock:/var/run/docker.sock -v /usr/bin/docker:/usr/bin/docker jenkins/jenkins:lts

https://www.tiuweehan.com/blog/2020-09-10-docker-in-jenkins-in-docker/
