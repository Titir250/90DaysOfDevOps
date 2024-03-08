## Day 16 Task: Docker for DevOps Engineers.

### Docker

Docker is a software platform that allows you to build, test, and deploy applications quickly. Docker packages software into standardized units called containers that have everything the software needs to run including libraries, system tools, code, and runtime. Using Docker, you can quickly deploy and scale applications into any environment and know your code will run.

# Tasks

As you have already installed docker in previous days tasks, now is the time to run Docker commands.

- Use the `docker run` command to start a new container and interact with it through the command line. [Hint: docker run hello-world]

 docker run hello-world

Unable to find image 'hello-world:latest' locally
latest: Pulling from library/hello-world
c1ec31eb5944: Pull complete
Digest: sha256:d000bc569937abbe195e20322a0bde6b2922d805332fd6d8a68b19f524b7d21d
Status: Downloaded newer image for hello-world:latest

Hello from Docker!
This message shows that your installation appears to be working correctly.

- Use the `docker inspect` command to view detailed information about a container or image.

 docker inspect a0974aebb9d4
[
    {
        "Id": "a0974aebb9d498329f3f96b82df499e4c8ffd2a311dfa4b25e280440cfdb9f51",
        "Created": "2024-03-08T17:03:52.681395013Z",
        "Path": "/hello",
        "Args": [],
        "State": {
            "Status": "exited",
            "Running": false,
            "Paused": false,
            "Restarting": false,
            "OOMKilled": false,
            "Dead": false,
            "Pid": 0,
            "ExitCode": 0,
            "Error": "",
            "StartedAt": "2024-03-08T17:03:54.404532229Z",
            "FinishedAt": "2024-03-08T17:03:54.404923597Z"
        },
        "Image": "sha256:d2c94e258dcb3c5ac2798d32e1249e42ef01cba4841c2234249495f87264ac5a",
        "ResolvConfPath": "/var/lib/docker/containers/a0974aebb9d498329f3f96b82df499e4c8ffd2a311dfa4b25e280440cfdb9f51/resolv.conf",
        "HostnamePath": "/var/lib/docker/containers/a0974aebb9d498329f3f96b82df499e4c8ffd2a311dfa4b25e280440cfdb9f51/hostname",
        "HostsPath": "/var/lib/docker/containers/a0974aebb9d498329f3f96b82df499e4c8ffd2a311dfa4b25e280440cfdb9f51/hosts",
        "LogPath": 

- Use the `docker port` command to list the port mappings for a container.

   docker port 6658b168af4a
80/tcp -> 0.0.0.0:80
80/tcp -> [::]:80

 docker port e961e7b6f416
8080/tcp -> 0.0.0.0:8080
8080/tcp -> [::]:8080
 docker port 77a67ec2da59
3306/tcp -> 0.0.0.0:3306
3306/tcp -> [::]:3306
 docker port 18eea51ea34c
9000/tcp -> 0.0.0.0:9000
9000/tcp -> [::]:9000


- Use the `docker stats` command to view resource usage statistics for one or more containers.

 docker stats 6658b168af4a e961e7b6f416 77a67ec2da59 18eea51ea34c


CONTAINER ID   NAME                CPU %     MEM USAGE / LIMIT     MEM %     NET I/O       BLOCK I/O   PIDS
6658b168af4a   frosty_goldberg     0.00%     7.383MiB / 3.693GiB   0.20%     866B / 0B     0B / 0B     9
e961e7b6f416   adoring_aryabhata   0.15%     84.89MiB / 3.693GiB   2.24%     866B / 0B     0B / 0B     39
77a67ec2da59   blissful_almeida    0.79%     381.5MiB / 3.693GiB   10.09%    936B / 0B     0B / 0B     37
18eea51ea34c   vigorous_feistel    2.38%     1.837GiB / 3.693GiB   49.75%    1.16kB / 0B   0B / 0B     265
CONTAINER ID   NAME                CPU %     MEM USAGE / LIMIT     MEM %     NET I/O       BLOCK I/O   PIDS
6658b168af4a   frosty_goldberg     0.00%     7.383MiB / 3.693GiB   0.20%     866B / 0B     0B / 0B     9
e961e7b6f416   adoring_aryabhata   0.13%     84.89MiB / 3.693GiB   2.24%     866B / 0B     0B / 0B     39
77a67ec2da59   blissful_almeida    0.83%     381.5MiB / 3.693GiB   10.09%    936B / 0B     0B / 0B     37
18eea51ea34c   vigorous_feistel    1.17%     1.837GiB / 3.693GiB   49.75%    1.16kB / 0B   0B / 0B     265
CONTAINER ID   NAME                CPU %     MEM USAGE / LIMIT     MEM %     NET I/O       BLOCK I/O   PIDS
6658b168af4a   frosty_goldberg     0.00%     7.383MiB / 3.693GiB   0.20%     866B / 0B     0B / 0B     9
e961e7b6f416   adoring_aryabhata   0.13%     84.89MiB / 3.693GiB   2.24%     866B / 0B     0B / 0B     39
77a67ec2da59   blissful_almeida    0.83%     381.5MiB / 3.693GiB   10.09%    936B / 0B     0B / 0B     37
18eea51ea34c   vigorous_feistel    1.17%     1.837GiB / 3.693GiB   49.75%    1.16kB / 0B   0B / 0B     265

- Use the `docker top` command to view the processes running inside a container.

  docker top 18eea51ea34c
UID                 PID                 PPID                C                   STIME               TTY
TIME                CMD
titir               202915              202895              1                   22:38               ?
00:00:05            /opt/java/openjdk/bin/java -jar lib/sonarqube.jar -Dsonar.log.console=true
titir               202962              202915              0                   22:38               ?
00:00:04            /opt/java/openjdk/bin/java -Xms4m -Xmx64m -XX:+UseSerialGC -Dcli.name=server -Dcli.script=./bin/elasticsearch -Dcli.libs=lib/tools/server-cli -Des.path.home=/opt/sonarqube/elasticsearch -Des.path.conf=/opt/sonarqube/temp/conf/es -Des.distribution.type=tar -cp /opt/sonarqube/elasticsearch/lib/*:/opt/sonarqube/elasticsearch/lib/cli-launcher/* org.elasticsearch.launcher.CliToolLauncher

- Use the `docker save` command to save an image to a tar archive.

   docker save -o hello-world.tar hello-world:latest

- Use the `docker load` command to load an image from a tar archive.
    docker load -i hello-world.tar
Loaded image: hello-world:latest


These tasks involve simple operations that can be used to manage images and containers.

For reference you can watch this video:
https://youtu.be/Tevxhn6Odc8

You can Post on LinkedIn and let us know what you have learned from this task by #90DaysOfDevOps Challenge. Happy Learning :)

[← Previous Day](../day15/README.md) | [Next Day →](../day17/README.md)
