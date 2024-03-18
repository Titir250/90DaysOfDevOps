# Day 19 Task: Docker for DevOps Engineers

**Till now you have learned how to create docker-compose.yml file and pushed it to the Repository. Let's move forward and dig more on other Docker-compose.yml concepts.**
**Aaj thodi padhai krte hai on Docker Volume & Docker Network** 😃

# Docker-Volume

Docker allows you to create something called volumes. Volumes are like separate storage areas that can be accessed by containers. They allow you to store data, like a database, outside the container, so it doesn't get deleted when the container is deleted.
You can also mount from the same volume and create more containers having same data.
[reference](https://docs.docker.com/storage/volumes/)

# Docker Network

Docker allows you to create virtual spaces called networks, where you can connect multiple containers (small packages that hold all the necessary files for a specific application to run) together. This way, the containers can communicate with each other and with the host machine (the computer on which the Docker is installed).
When we run a container, it has its own storage space that is only accessible by that specific container. If we want to share that storage space with other containers, we can't do that. [reference](https://docs.docker.com/network/)

## Task-1

- Create a multi-container docker-compose file which will bring _UP_ and bring _DOWN_ containers in a single shot ( Example - Create application and database container )

_hints:_

- Use the `docker-compose up` command with the `-d` flag to start a multi-container application in detached mode.

docker-compose up -d
two-tier-flask-app_mysql_1 is up-to-date
two-tier-flask-app_backend_1 is up-to-date
ubuntu@ip-172-31-26-224:~/projects/two-tier-flask-app$


- Use the `docker-compose scale` command to increase or decrease the number of replicas for a specific service. You can also add [`replicas`](https://stackoverflow.com/questions/63408708/how-to-scale-from-within-docker-compose-file) in deployment file for _auto-scaling_.


- Use the `docker-compose ps` command to view the status of all containers, and `docker-compose logs` to view the logs of a specific service.

  -
docker-compose ps
          Name                     Command           State            Ports
------------------------------------------------------------------------------------
two-tier-flask-            python app.py             Up      0.0.0.0:5000-
app_backend_1                                                >5000/tcp,:::5000-
                                                             >5000/tcp
two-tier-flask-            docker-entrypoint.sh      Up      0.0.0.0:3306-
app_mysql_1                mysqld                            >3306/tcp,:::3306-
                                                             >3306/tcp, 33060/tcp
                                                             
                                                             
docker-compose logs
Attaching to two-tier-flask-app_backend_1, two-tier-flask-app_mysql_1
backend_1  |  * Serving Flask app 'app' (lazy loading)
backend_1  |  * Environment: production
backend_1  |    WARNING: This is a development server. Do not use it in a production deployment.
backend_1  |    Use a production WSGI server instead.
backend_1  |  * Debug mode: on
backend_1  | WARNING: This is a development server. Do not use it in a production deployment. Use a production WSGI server instead.
backend_1  |  * Running on all addresses (0.0.0.0)
backend_1  |  * Running on http://127.0.0.1:5000
backend_1  |  * Running on http://172.20.0.3:5000
backend_1  | Press CTRL+C to quit



- Use the `docker-compose down` command to stop and remove all containers, networks, and volumes associated with the application

docker-compose down
Stopping two-tier-flask-app_backend_1 ... done
Stopping two-tier-flask-app_mysql_1   ... done
Removing two-tier-flask-app_backend_1 ... done
Removing two-tier-flask-app_mysql_1   ... done
Removing network two-tier-flask-app_default
ubuntu@ip-172-31-26-224:~/projects/two-tier-flask-app$



## Task-2

- Learn how to use Docker Volumes and Named Volumes to share files and directories between multiple containers.
- Create two or more containers that read and write data to the same volume using the `docker run --mount` command.
- Verify that the data is the same in all containers by using the docker exec command to run commands inside each container.
- Use the docker volume ls command to list all volumes and docker volume rm command to remove the volume when you're done.

## You can use this task as _Project_ to add in your resume.

You can Post on LinkedIn and let us know what you have learned from this task by #90DaysOfDevOps Challenge. Happy Learning :)

[← Previous Day](../day18/README.md) | [Next Day →](../day20/README.md)
