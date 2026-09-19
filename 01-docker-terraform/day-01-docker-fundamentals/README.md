# Week 1 Day 1 — Docker Fundamentals

## What is Docker?

Docker is an open-source platform used to build, package, test, and run applications using containerization.

Containers include the application and its required dependencies in a consistent environment, which makes applications easier to run across development, testing, CI/CD, and production.

Docker is lighter than a traditional virtual machine because containers share the host operating system kernel instead of running a full guest operating system.

---

## Why Docker is Useful

Managing application code, libraries, dependencies, and runtime configuration separately can become difficult and inconsistent across different systems.

Docker helps solve this by packaging the application and its dependencies into an image.

This improves:

- Reproducibility
- Portability
- Environment consistency
- Deployment reliability
- Isolation between applications

It also helps reduce the common "works on my machine" problem.

---

## Basic Docker Commands

```bash
docker pull
docker run
docker ps
docker ps -a
docker start
docker stop
docker rm
docker images


## Docker Client

Docker Client is the interface through which we give commands to Docker.

For example:

```bash
docker run python:3.13-slim
```

The Docker Client sends this request to the Docker Daemon, which performs the actual operation.

---

## Docker Daemon

Docker Daemon is the background service that manages Docker resources.

It performs operations such as:

- Pulling images
- Creating containers
- Starting containers
- Stopping containers
- Removing containers

In simple terms:

**Docker Client gives the instruction, and Docker Daemon performs the work.**

---

## Docker Registry

Docker Registry is a place where Docker images are stored.

Docker Hub is an example of a public Docker registry.

When we run:

```bash
docker pull python:3.13-slim
```

Docker checks the registry and downloads the required image to the local machine.

---

## Image vs Container

A Docker image is an immutable blueprint used to create containers.

A Docker container is a runnable instance created from that image.

Simple way to remember:

**Image = Blueprint**

**Container = Runnable instance of the blueprint**

Multiple containers can be created from the same Docker image.

---

## docker run vs docker start

### docker run

```bash
docker run <image>
```

`docker run` creates a new container from an image and starts it.

So:

**docker run = create + start**

### docker start

```bash
docker start <container_id>
```

`docker start` starts an already existing stopped container.

It does not create a new container.

---

## docker ps vs docker ps -a

```bash
docker ps
```

Shows only currently running containers.

```bash
docker ps -a
```

Shows all containers, including running, stopped, and exited containers.

---

## Container Lifecycle

The basic Docker container lifecycle I practiced was:

```text
Image
  ↓
docker run
  ↓
Container Created and Running
  ↓
docker stop
  ↓
Container Stopped
  ↓
docker start
  ↓
Container Running Again
  ↓
docker stop
  ↓
docker rm
  ↓
Container Removed
```

Important commands:

```text
docker run   → Create and start a new container
docker stop  → Stop a running container
docker start → Start an existing stopped container
docker rm    → Remove a stopped container
```

A stopped container still exists until it is removed.

---

## What Happens When docker run is Executed?

Example:

```bash
docker run python:3.13-slim
```

High-level flow:

```text
Docker Client
     ↓
Docker Daemon
     ↓
Check image locally
     ↓
If image is missing
     ↓
Pull image from Docker Registry
     ↓
Create container from image
     ↓
Start container process
```

---

## Docker vs Virtual Machine

Both Docker containers and Virtual Machines provide isolation, but they work differently.

### Docker Container

- Shares the host operating system kernel
- Lightweight
- Starts quickly
- Uses fewer resources
- Contains mainly the application and its required dependencies

### Virtual Machine

- Has its own guest operating system
- Has its own OS kernel
- Uses more CPU, RAM, and storage
- Usually takes longer to start

Therefore, Docker containers are generally lighter and faster than traditional Virtual Machines.

---

## Day 1 Hands-on Commands

```bash
docker pull python:3.13-slim

docker images

docker run -it python:3.13-slim bash

docker ps

docker ps -a

docker start <container_id>

docker stop <container_id>

docker rm <container_id>
```

Inside the Python container I also practiced:

```bash
python --version
pwd
ls
cat /etc/os-release
```

---

## Day 1 Key Learnings

- Docker Client sends commands to Docker.
- Docker Daemon performs the actual Docker operations.
- Docker Registry stores Docker images.
- An image is an immutable blueprint.
- A container is a runnable instance of an image.
- `docker run` creates and starts a new container.
- `docker start` starts an existing stopped container.
- `docker ps` shows running containers.
- `docker ps -a` shows all containers.
- A stopped container still exists until it is removed.
- Docker containers share the host OS kernel and are lighter than traditional Virtual Machines.
```

