# Fargate

- Fargate is a service which provides us the ability to run Docker container in AWS without having to provision the underlying EC2 infrastructure
- It is a serverless solution for container orchestration in the cloud
- In order to scale an application we just have to increase the number of task

## Creating a Fargate Cluster

- We have to chose **Networking only** option for ECS
- VPCs and Subnets are optional in case of Fargate
- ECS EC2 task definitions are incompatible with Fargate, we will have to recreate them if we migrate from EC2
- There is no host port mapping in Fargate
