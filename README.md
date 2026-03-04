*This project has been created as part of the 42 curriculum by kjolly*

# Inception - System Administration & Docker

## Description
Inception is a 42 school project designed to deepen knowledge in system administration by using **Docker**. The goal is to set up a small infrastructure composed of several services, all running in isolated containers within a dedicated network.

The project mimics a real production environment where services (Nginx, WordPress, MariaDB) must communicate securely while maintaining data persistence.

Key Components:
* NGINX: A web server configured with TLSv1.2/v1.3 for secure connections.
* WordPress + PHP-FPM: The content management system, pre-configured with two user profiles.
* MariaDB: The relational database management system.
* Docker Compose: To orchestrate the building and launching of the entire stack.
* Persistent Volumes: Ensuring data survives container restarts or deletions.

## Instruction
Prerequisites
A Linux environment (or a VM).
Docker and Docker Compose installed.
Domain mapping: Add kjolly.42.fr to your /etc/hosts pointing to 127.0.0.1.

### Step 1: Compilation
Use the provided Makefile at the root of the project. It handles directory creation for volumes and triggers the build.

-make up

### Step 2: Watch the Logs
Wait for the containers to initialize, then verify the logs to ensure all services are healthy.

-make logs

### Step 3: Testing via browser
Open your browser and navigate to:
https://kjolly.42.fr

### Step 4: Down and Clean
To stop the services without deleting data:

-make down

To wipe everything (containers, images, and volumes):
--make clean

## Ressources
https://www.docker.com/
https://blog.stephane-robert.info/docs/conteneurs/moteurs-conteneurs/docker/
https://www.ibm.com/fr-fr/think/topics/docker
https://gaotian.medium.com/premi%C3%A8re-utilisation-de-docker-compose-296fe9690e70

## Technical Features
* Infrastructure as Code: Everything is automated via Dockerfiles and docker-compose.yml.
* Security: Use of custom SSL certificates and restricted network communication between containers.
* Volume Management: Specific mapping for WordPress files and MariaDB databases on the host machine.
* Custom Images: Every image is built from a Debian base to ensure total control over the environment.
* Environment Variables: Secure management of credentials via a .env file (not tracked in Git).

## Use of IA
AI was used as a learning assistant during this project for:
* Clarifying complex Docker concepts and networking.
* Debugging and interpreting container logs.
* Optimizing shell scripts for entrypoints.