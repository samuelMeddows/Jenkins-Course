# Introduction and Installation

Jenkins is the leading open source automation server, Jenkins provides hundreds of plugins to support building, deploying and automating any project.
[jenkins.io](https://www.jenkins.io/)

### Linux Dev VM

I am using CentOS Stream 9 running on Virtual Box.
[rockylinux.org](https://rockylinux.org)

### Install Docker

[Docker install for CentOS](https://docs.docker.com/engine/install/centos/)

Start docker on system boot:
`sudo systemctl enable docker`

Enable permissions to see docker as user
`sudo usermod -aG docker <username>`

Check docker is running
`docker ps`
