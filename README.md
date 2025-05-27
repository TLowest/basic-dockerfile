# Basic Dockerfile

This project demostrates how to build a minimal Docker image using Ubuntu Linux that prints "Hello, Captain!" when executed. It serves as an introduction to writing and using Dockerfiles for creating lightweight containers. 

---
## Project Overview
> This Project is inspired by [roadmap.sh](https://roadmap.sh/projects/basic-dockerfile)

Creating a basic `Dockerfile` that uses `ubuntu:latest` as its base image.
When the container is run, it will execute a command to display a custom greeting message and then exit. 

---
## Instructions
> If you are installing Docker Engine for the first time, you may use the script: `docker-setup.sh`.
>
> But make sure to run the following command to uninstall all conflicting packages:
> 
> `for pkg in docker.io docker-doc docker-compose docker-compose-v2 podman-docker containerd runc; do sudo apt-get remove $pkg; done`
>
> Referenced by [dockerdocs](https://docs.docker.com/engine/install/ubuntu/)

1. Clone this repository or create your own directory with a `Dockerfile`.

(*Optional but recommended*) 
In order to run Docker without `sudo`:
```BASH
sudo usermod -aG docker $USER
```

2. Build the Docker image:
```BASH
docker build -t hello-captain .
```

3. Run the Docker container:
```BASH
docker run --rm hello-captain 
```

After running the container, you should see the following output in the terminal:
```BASH
Hello, Captain!
```

---
## Optional Enhancement
To make the greeting dynamic, while preserving the original `Dockerfile` and avoid overwriting it, you can create a second one:
```BASH
Dockerfile.arg
```
Then build using the `-f` flag and your name:
```BASH
docker build -f Dockerfile.arg -t hello-name --build-arg NAME=<insert_name>
```
Run the image:
```BASH
docker run --rm hello-name
```

After running the container, you should see the following output in the terminal: 
```BASH
Hello, <inserted_name>!
```

---
## Learn More
Refer to the offical Dockerfile reference:
[Dockerfile Documentation](https://docs.docker.com/reference/dockerfile/)

