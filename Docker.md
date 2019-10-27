# Docker
- (Course) Docker for Devops - https://www.udemy.com/docker-tutorial-for-devops-run-docker-containers

## Install
https://docs.docker.com/install/

## Amazon ECR
- Registry
- Authorization token
- Repository
- Repository policy
- Image

Run the `aws ecr get-login --no-include-email` command to get the **docker login** authentication command string for your registry.

Run the `docker login` command that was returned in the previous step. This command provides an authorization token that is valid for 12 hours.

