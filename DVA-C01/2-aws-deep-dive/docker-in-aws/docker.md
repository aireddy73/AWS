# Docker

- Docker is a software development platform used to deploy applications
- Applications are packaged in **containers** that can be run on any operating systems
- Since application are containerized, they run the same regardless of the underlying OS
- Docker containers do not interact with each-other as long as we do not make them to do
- One faulty application may bring down one container, other containers will stay intact
- Since multiple containers can run on the same host machine, we are able to scale them horizontally

## Container Registries

- Docker images are stored in Docker Repositories also name Container Registries
- Example of container registries: Docker Hub, Elastic Container Registry (ECR), etc.

## Containers vs Virtual Machines

- VM: virtual machines are running on the hypervisor
- Container: resources are shared with the host (no hypervisor) => many containers can run on the same host