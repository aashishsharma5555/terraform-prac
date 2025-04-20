# Terraform Docker Practice

This project demonstrates how to use *Terraform* to provision a *Docker container* running the NGINX web server.

## What I Did

1. *Initialized Terraform Project*
   - Created a main.tf file to define infrastructure.
   - Ran terraform init to initialize the working directory.

2. *Configured Terraform Provider*
   - Used the Docker provider from kreuzwerker/docker.
   - Specified provider version ~> 3.0.2.

3. *Docker Provider Setup*
   - Configured Docker to communicate with the local Docker daemon using:
     
     host = "unix:///var/run/docker.sock"
     

4. *Defined Docker Image Resource*
   - Pulled the nginx:latest image using the docker_image resource.

5. *Defined Docker Container Resource*
   - Created a container named nginx_container.
   - Exposed internal port 80 to host port 8080.

6. *Fixed Error*
   - Originally used docker_image.nginx.latest, which gave an error.
   - Corrected to docker_image.nginx.name in the container config.

7. *Applied Configuration*
   - Ran terraform plan to preview changes.
   - Ran terraform apply and typed yes to deploy the infrastructure.

## How to Run

1. Make sure Docker is running on your machine.
2. Run the following commands:
   ```bash
   terraform init
   terraform plan
   terraform apply
   terraform destroy
