# WordPress

Deploying wordpress on AWS/Azure with RDS using Terraform, and Docker.

Create a Terraform script to deploy a VM. The VM should be in public subnet.
In the same VM Create a Dockerfile to deploy Apache webserver + PHP + Wordpress. Use COPY, ARG, RUN, ENTRYPOINT, CMD, WORKDIR in Dockerfile.
Build the docker image, tag the image and push the docker image to Docker Hub and run the container.
Deploy the RDS on AWS/Azure and it should be on private subnet.
Connect your Wordpress container with RDS database.
Setup the Wordpress and attach all the screenshot and code to Github. 
