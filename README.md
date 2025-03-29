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

