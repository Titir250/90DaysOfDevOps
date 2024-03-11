# Day 18 Task: Docker for DevOps Engineers

Till now you have created Docker file and pushed it to the Repository. Let's move forward and dig more on other Docker concepts.
Aj thodi padhai krte hai on Docker Compose 😃

## Docker Compose

- Docker Compose is a tool that was developed to help define and share multi-container applications.
- With Compose, we can create a YAML file to define the services and with a single command, can spin everything up or tear it all down.
- Learn more about docker-compose [visit here](https://tecadmin.net/tutorial/docker/docker-compose/)

## What is YAML?

- YAML is a data serialization language that is often used for writing configuration files. Depending on whom you ask, YAML stands for yet another markup language or YAML ain’t markup language (a recursive acronym), which emphasizes that YAML is for data, not documents.
- YAML is a popular programming language because it is human-readable and easy to understand.
- YAML files use a .yml or .yaml extension.
- Read more about it [here](https://www.redhat.com/en/topics/automation/what-is-yaml)

## Task-1

Learn how to use the docker-compose.yml file, to set up the environment, configure the services and links between different containers, and also to use environment variables in the docker-compose.yml file.


ubuntu@ip-172-31-91-182:~/projects/nginx-mysql$ docker-compose up
Creating network "nginx-mysql_default" with the default driver
Pulling web (nginx:latest)...
latest: Pulling from library/nginx
e1caac4eb9d2: Already exists
88f6f236f401: Pull complete
c3ea3344e711: Pull complete
cc1bb4345a3a: Pull complete
da8fa4352481: Pull complete
c7f80e9cdab2: Pull complete
18a869624cb6: Pull complete
Digest: sha256:c26ae7472d624ba1fafd296e73cecc4f93f853088e6a9c13c0d52f6ca5865107
Status: Downloaded newer image for nginx:latest
Pulling db (mysql:)...
latest: Pulling from library/mysql
9a5c778f631f: Pull complete
9e77c3a95bf2: Pull complete
8b279a2086e0: Pull complete
c8bfbcde7882: Pull complete

ubuntu@ip-172-31-91-182:~/projects/nginx-mysql$ docker-compose down
Removing nginx-mysql_web_1 ... done
Removing nginx-mysql_db_1  ... done
Removing network nginx-mysql_default




[Sample docker-compose.yaml file](https://github.com/LondheShubham153/90DaysOfDevOps/blob/master/2023/day18/docker-compose.yaml)

## Task-2

- Pull a pre-existing Docker image from a public repository (e.g. Docker Hub) and run it on your local machine. Run the container as a non-root user (Hint- Use `usermod ` command to give user permission to docker). Make sure you reboot instance after giving permission to user.

  
- Inspect the container's running processes and exposed ports using the docker inspect command.
- Use the docker logs command to view the container's log output.
- Use the docker stop and docker start commands to stop and start the container.
- Use the docker rm command to remove the container when you're done.

## How to run Docker commands without sudo?

- Make sure docker is installed and system is updated (This is already been completed as a part of previous tasks):
- sudo usermod -a -G docker $USER

sudo usermod -aG docker $USER

- Reboot the machine.

sudo reboot

For reference you can watch this [video](https://youtu.be/Tevxhn6Odc8)

You can Post on LinkedIn and let us know what you have learned from this task by #90DaysOfDevOps Challenge. Happy Learning :)

[← Previous Day](../day17/README.md) | [Next Day →](../day19/README.md)
