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