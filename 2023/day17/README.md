## Day 17 Task: Docker Project for DevOps Engineers.

### You people are doing just amazing in **#90daysofdevops**. Today's challenge is so special Because You are going to do DevOps project today with Docker. Are You Exited 😍

# Dockerfile

Docker is a tool that makes it easy to run applications in containers. Containers are like small packages that hold everything an application needs to run. To create these containers, developers use something called a Dockerfile.

A Dockerfile is like a set of instructions for making a container. It tells Docker what base image to use, what commands to run, and what files to include. For example, if you were making a container for a website, the Dockerfile might tell Docker to use an official web server image, copy the files for your website into the container, and start the web server when the container starts.

For more about Dockerfile visit [here](https://rushikesh-mashidkar.hashnode.dev/dockerfile-docker-compose-swarm-and-volumes)

task:

- Create a Dockerfile for a simple web application (e.g. a Node.js or Python app)


# Use the official Python image from the Docker Hub
FROM python:3.9-slim
# Set the working directory in the container
WORKDIR /app
# Copy the dependencies file to the working directory
COPY requirements.txt .
# Install Flask and other dependencies
RUN pip install --no-cache-dir -r requirements.txt
# Copy the content of the local src directory to the working directory
COPY . .
# Expose port 5000 to the outside world
EXPOSE 5000
# Command to run the application
CMD ["python", "app.py"]




- Build the image using the Dockerfile and run the container

docker build -t simple-python-app:latest .

docker run -d -p 5000:5000 simple-python-app:latest
0efdf11bb270ebd18fd3fd25dac73f773c9d18e03dc42088660a2470ebc8044f

docker images
REPOSITORY           TAG        IMAGE ID       CREATED              SIZE
simple-python-app    latest     a8f1d8870987   33 seconds ago       137MB
<none>               <none>     78ffc882d31d   About a minute ago   137MB



- Verify that the application is working as expected by accessing it in a web browser

yes, running..

- Push the image to a public or private repository (e.g. Docker Hub )


docker login
docker tag simple-python-app titirroy/simple-python-app
docker push titirroy/simple-python-app



For Refference Project visit [here](https://youtu.be/Tevxhn6Odc8)

If you want to dive further, Watch [bootcamp](https://youtube.com/playlist?list=PLlfy9GnSVerRqYJgVYO0UiExj5byjrW8u)

You can share the learning with everyone over linkedin and tag us along 😃

Happy Learning:)

[← Previous Day](../day16/README.md) | [Next Day →](../day18/README.md)
