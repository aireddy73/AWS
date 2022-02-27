# ECR - Elastic Container Registry

- Used for for storing private Docker images
- Access for ECR is controller by IAM. If a service like ECS wants to pull a container, we have to add the correct permissions to the service
- Authenticate against ECR using CLI:
    - AWS CLI v1 login command:
        `$(aws ecr get-login --no-include-email --region eu-west-1)` - the output of the `get-login` command is executed
    - AWS CLI v2 login command:
        `aws ecr get-login-password --region eu-west-1 | docker login --username AWS --password-stdin 12345.dkr.ecr.eu-west-1.amazonaws.com` - uses pipes, the first part of the command will give the login password, the second part of the command will take the login password and do the authentication

