## Docker
# What exactly is docker ?? 
- Container Technology -> creating and managing
- Container = Unit of Software (package of code + deps to run that code - means NodeJs code + NodeJs RT) -> always yield the same behavior and result
- self contained and isolated -> can be taken everywhere container could be run
# Why Containers ? 
- Independent, standardised "application packages"
- Having exact same dev and prod env helps a lot 
- Here comes docker -> make code executes in container with same version is developed with
- Reproducibility - share commn dev env among teammates
- Clashing Versions -> swtiching among projects
- RUN IN OUR CONTAINERS
# VM vs Docker ?
- VM - maachine running on our machine with virtual os encapsulated in shell independent from host os
- Virtual OS (just anothr machine)
- Problem - Vitual OS and Overhead (CPUs and Memory)
- Pros - Seperated Env, Env Specific Config, Reporoducible
- Cons - Redundant, Overhead - of setting upa nd config it (not a single config file that we can share), Performance - Slow
- Container - we have our OS -> using OS built-in Container Support -> Docker engine Runs on it -> Container
- We have config files here -> images shareable
- Docker (low impact on OS, fast, sharing, re-building, Encapsulated) vs VM (biggger impact on OS, slow, higer disk usage, sharing, re-building, encapsulated whole machine)
# Docker Engine - installed by Docker Desktop (DAEMON + CLI)
- hosts linux requires to run docker
- daemon - process keeps on running that ensures docker is working - heart
- cli
- docker hub - used to host images
- docker compose - tools used to maintain multiple containeres
- kubernetes - used while deploying container
# Commands
- docker build . -> creates a docker image (set of instruction ready to run as container)
- docker run -p 3000:3000 <id>
# Foundation
- Images & Containers    
- Data & Volumes
- Containers and Networking
# Real Life
- Multi-Container Projects
- Docker Compose
- Utility Containers
- Deploy Docker Containers using AWS
# Kubernetes
- Introduction and Basics
- Data & Volumes
- Networking
- Deploying a cluster
# Images and Containers 
- Container (Runnin unot of software - code + env)
- Images (Templates/BP for  containers) -> Contains code and required tools/rt
- same img can be used to create multiple containers
- img - is shareable bp - setup code and environment
- container - running instance of img
- Image -> existing/ pre-built or create 
- docker run node -> gives interactive shell where we can insert command - but by default container is isolated -> not automatically exposed to user
- docker ps -a -> ps - processes
- docker run -it node -> we want interactive session
- Creation of images -> pulling base image + logic (running on top of the base image)
- Dockerfile - setup instruction for our image
- FROM (ALL CAPS)
- COPY .(local host) /app(inside container)
- WORKDIR /app (all cmds run in this subfolder)
- RUN npm install 
- All this here run during building the image
- All this here are instructions to setup the image - template for container
- container runs based on image
- CMD ["node", "server.js"] -> run once the conatienr is running
- Docker container is isoolated has its own network
- To make it expose to the local
- EXPOSE 80 -> only for documentation purposes not do really anything (optional)
- docker build . -> build our image
- docker run <id> -> runs a new container based on image
- docker ps -a -> shows every container
- docker ps -> shows running containers
- docker run -p 3000:80 <id> -> -p (publish)
- As an additional quick side-note: For all docker commands where an ID can be used, you don't always have to copy / write out the full id.
- You can also just use the first (few) character(s) - just enough to have a unique identifier.
- Images are **Read Only** -> takes SNAPSHOT of source code -> SO need to build the image again if there is changes
- Yup there is a way to simplify - later
- Image is **closed template**
- Images are **Layer Based** -> while building/ re-building the image -> **only instructions where something changed and all the instruction there after are reevaluated** -> once the layer changes after that every layer is re executed.   
- **Layer Based Architecture** -> every instructions represent layers -> layers are cached -> container bassed on image just adds a **container layer (read+write)**
# Managing Images and Containers
- -t
- docker images
- docker image inspect
- docker rmi, docker prune
- --name
- --help
- docker ps -> show containers
-a: gives the all containers
- docker start <name> -> run the existing container - not blocking the terminal -> **detached mode** -> -a for **attahced mode**
- docker rm
# Attached and Detached Container
- Detached - container runnning in background
- Attached - running in foreground -> means we're listening to the outputs
- docker run -p _:_ -d <id> -> -d: for detached mode
- docker attach <name/id> -> now we can listen to the outputs
- docker logs -f <name/id> -> we can see the past logs related to container -> -f: follow the logs -> attached

