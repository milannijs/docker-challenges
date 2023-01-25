# Challenge 3
### Copying files and validating them in running containers
Set of challenges to copy files from and to the container and local machine

In these challenge we'll learn how to
- Copy files through instructions on the Dockerfile
- Ignoring content to be copied
- Copy files from the local machine to a container
- Copy files from the container to the local machine
- Interact with running containers

### Copying files through the Dockerfile challenge
- Create an image where your working directory is challenge3
- Copy the files in the folder `dockerfile_files`, except file `file4`
- Copy `output.tar` file in the Dockerfile where its content is automatically extracted
  - `output.tar` contains `compressed_file1` and `compressed_file2` 
- Run the image and validate its content

To check the content of the Docker container, run the following:
- `docker build -t test .` 
- `docker run -dit test /bin/bash`
- `docker ps` to check if the container has been spun up and find the container name
- `docker exec -it <container_name> /bin/bash` now you are in the command line of the docker container.

### Copying files from the local machine to a container
- Copy the folder `docker_container_files` to the container of the previous challenge
(`docker cp docker_container_files/ 9d41ca837f85:/challenge3/`)
- Validate the content in the container (`docker exec -it <container_name> /bin/bash` and check)

### Copying files from a Docker container to the local machine
- Create a file `hello_world` in the container of the previous challenge and copy it to the local machine
(go inside the docker container `docker exec -it <container_name> /bin/bash` and make a file `touch hello_world`. Copy using `docker cp 9d41ca837f85:/challenge3/hello_world .`)
- Validate locally the file was copied