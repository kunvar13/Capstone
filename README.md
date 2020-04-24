# Capstone-project
##Step 1: Scope the Project and Kubernetes Cluster
1)	Pipeline has three steps Linting, Continuous Integration and Continues Deployment
2)	For Docker application I have chosen the open source application available online. This is java based project.
3)	I have setup the Kubernetes cluster manually.
4)	I have opened the port 31200 in kubernetes cluster to access the webapp
##Step 2: Used Jenkins with Rolling Deployment
1)	Plugging Installed on Jenkins are 
A)	Maven Integrator
B)	Maven Invoker
C)	Deploy to Container
D)	Publish Over SSH
E)	Java plugin
##Step 3: Rolling Deployment step
1)	Linting is the first step of the pipeline, I have performed the linting on the xml files used to build the project. Idf the linting is successful it triggers the next step in pipeline
 
2)	In continuous integration I have used the send build artifacts over the SSH. This SSH in to the Ansible server and execute the Ansible command to deploy the docker image using “kal-devops-image.yml”. This also pushes the image to Docker Hub. 
3)	Docker hub Repository :- https://hub.docker.com/r/kunvar13/kal-devops-image
4)	Command to pull image docker pull kunvar13/kal-devops-image

 
5)	Once the Continues integration stage is passed it triggers the Continues Deployment,
In continuous deployment step it SSH into the Ansible serer and executes two Ansible command using kubernetes-kal-deployment.yml and kubernetes-kal-service.yml.
 
