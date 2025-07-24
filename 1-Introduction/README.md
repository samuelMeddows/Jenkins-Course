# Introduction and Installation

Jenkins is the leading open source automation server, Jenkins provides hundreds of plugins to support building, deploying and automating any project.<br>
[jenkins.io](https://www.jenkins.io/)

### Linux Dev VM

I am using CentOS Stream 9 running on Virtual Box.<br>
[rockylinux.org](https://rockylinux.org)

---

### Install Docker

[Docker install for CentOS](https://docs.docker.com/engine/install/centos/)

Start docker on system boot.<br>
`sudo systemctl enable docker`

Enable permissions to see docker as user. Then logout and log back in.<br>
`sudo usermod -aG docker <username>`

Check docker is running.<br>
`docker ps`

---

### Install Jenkins on Docker

[Jenkins Docker Hub Image](https://hub.docker.com/r/jenkins/jenkins/)

Pull docker image.<br>
`docker pull jenkins/jenkins:2.516.1-lts-jdk21`

Show downloaded docker images.<br>
`docker images`

Show where docker is saving images.<br>
`docker info | grep -i root`

Show the size of the docker images folder.<br>
`sudo du -sh /var/lib/docker`

Create a jenkins data folder and move to the folder.<br>

```
mkdir jenkins-data
cd jenkins-data
```

Create a jenkins_home folder.<br>
`mkdir jenkins_home`

Create a docker compose file.<br>
`nano docker-compose.yml`

Add the following code.<br>

```
version: '3'
services:
  jenkins:
    container_name: jenkins
    image: jenkins/jenkins
    ports:
      - "8080:8080"
    volumes:
      - $PWD/jenkins_home:/var/jenkins_home
    networks:
      - net
networks:
  net:
```
