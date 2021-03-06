# Containers and the Cloud 

By: Jean Tirstan

Polibatam Cyber


## You Can Find These Presentations Online

Visit []() to find these presentations and more online!

<span style="padding-top: 6em; font-size: 0.4em; float: left;">Material: <a href="https://tldrlegal.com/license/creative-commons-attribution-sharealike-4.0-international-(cc-by-sa-4.0)">Creative Commons Attribution-ShareAlike 4.0</a></span><span style="padding-top: 6em; font-size: 0.4em; float: right;">Code: <a href="https://tldrlegal.com/license/bsd-2-clause-license-(freebsd)">BSD 2-Clause</a></span>



## Containers


### What is a Container?

* Abstraction at the application layer
* Multiple containers can run on the same machine and share the kernel
* Isolated processes in user space


### How is it different from a VM?

* VMs abstract physical hardware
* Containers take up far less space
* Containers can start nearly instantly


![container](container.png)


![vm](vm.png) 


### What types of containers are there?

* Docker
* LXC
* FreeBSD Jails



## Docker

* Open platform for developing, shipping, and running applications
* Primarily developed for Linux
* High-level API to provide lightweight containers that run processes in isolation


### Docker Architecture

![architecture](architecture.svg)


### Installation
`sudo apt-get install docker-engine -y`
`brew cask install docker`


### Docker Objects

* Images
* Containers


#### Docker Images

* Read-only template with instructions for creating a container
* Images are often *based* on another image w/ some changes
* For example, image based on Ubuntu installs Apache w/ configs
* Dockerfiles 


#### Docker Containers

* Runnable instance of an image
* Create, start, stop, move, or delete containers using the API


### Docker Commands

* man docker-run
* docker ps -a
* docker images
* docker stop $(docker ps -aq)
* docker rm --force $(docker ps -aq)
* docker rmi --force $(docker images -aq)
* docker run -it ubuntu /bin/bash


### Docker Registries

* Docker registries store Docker images
* docker pull OR docker run
* docker push
* Docker Hub - https://hub.docker.com/
* Docker Cloud - https://cloud.docker.com/


### Docker Compose

![docker-compose](docker-compose.png)

* Used to run multi-container Docker applications
* Uses YAML files for configuration
* Bring entire projects up/down simultaneously


### Docker Swarm

* Multiple docker hosts run in **swarm mode** act as managers and workers
* If a worker node becomes unavailable, tasks are distributed elsewhere
* Modify service configuration without the need to manually restart
* Submit service definitions to manager nodes who distribute units of work
* Units of work called tasks given to worker nodes


### Kubernetes

* Open source container management/orchestration from Google
* Flat network so all pods can interact with eachother
* Slower scaling than Swarm, but has higher fault tollerance
* Can support higher demand and is more complex overall
* Becoming adopted by large corporations


### Why Dockerize?

* Create an enviornment for legacy systems
* Easy portability
* Customization of enviornments
* Easy to manage services


## Break Out?

* Containers are still vulnerable to kernel exploits
* Dirty COW write to vDSO
* Exploit shared memory



