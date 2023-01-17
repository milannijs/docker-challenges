# Challenge 2
### Managing containers & images
Set of challenges to learn how to view and manage containers and images

In these challenges we'll learn how to
- List images
- List containers
- Control lifecycle of images and containers

Setup environment:
- Run the Dockerfile in the challenge folder
- Run `docker run -dit ubuntu /bin/bash`

Repeat the setup step as many times as necessary throughout the challenges.

Advised time: 1h30min

### Listing challenges
Images
- List images (`docker images`)
- List all images, including dangling (`docker images -a`)
- List only the images IDs (`docker images -q`)
- List only images from Ubuntu (`docker images --filter "reference=ubuntu"`)
- List untagged images (`docker images --filter "dangling=true"`)

Containers
- List containers (`docker ps` or `docker container ls`)
- List all containers (`docker ps -a` or `docker container ls -a`)
- List containers not running (`docker ps --filter "status=exited"`)
- List containers by name (`docker ps --filter "name=brave_spence"`)
  - Optional: give a specific name to a container (`docker rename brave_spence cowardly_turtle`)

### Lifecycle challenges
- Delete the ubuntu image (`docker rmi ubuntu`)
- Delete the helloworld container (`docker container stop cowardly_turtle`, `docker rm cowardly_turtle`)
- In a single command, delete all stopped containers (docker rm $(`docker ps --filter status=exited -q)`)
  - Optional: do it in 3 different ways
- In a single command, delete all unused containers and images (`docker system prune -a`)
- In a single command, remove all images (`docker images purge`)
  - Optional: do it in 2 different ways