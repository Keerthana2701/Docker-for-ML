# Docker-for-ML

## Docker:



Docker is a tool that packages applications with its dependencies in a  container.

It is based on "build once and deploy anywhere"



## Docker Image:



A docker image is actual package with configuration and dependencies  and it is a artifact that is portable. It is used to create a docker container. 

After image is created for the code, instead of pushing code, we push the docker image to the deployment phase(container registry)

The same docker image can be used in every step of deployment process and this can reduce time since it runs in parallel across environment.

To view the images : docker images



Docker File --->  Docker Image (using docker build command)---> Docker container (by running the docker image using docker run command)

## Docker Containers:

Running instance of docker image. 

We need to run  a docker image to create a docker container.

It provides portability and reproducibility of environments and hence reproducibility of output.



to get information about running containers - docker ps

## Docker File:

We need to build a docker file and build a image out of it.

It contains all commands that user calls on command line to form an image.

FROM - used to access a base image (from docker hub, which base image to select)

COPY - copy from host system to location present inside docker image

EXPOSE - to expose a port. (network port number)

WORKDIR -same as present in COPY since its the working directory

RUN -  pip install requirements.txt since we need the dependencies. it installs all the libraries to docker.

CMD - run the python file here. say, python app.py

app.py is the python file where we have written our python code using ML algorithm, build model,flask, flassger to make predictions.



## Docker Build:

After docker file is written, Docker build is used to build a docker image from that docker file

Open docker quickstart terminal.

Navigate to the path where we have docker file and the codes.



To build the docker image: docker build -t apiname .

apiname  - api name we need

. - dot indicates we need to build from the current directory

this executes the docker file.

ex : docker build -t studentapi



To see which all dockers are running - docker ps

this shows all the images and containers



## Docker Run:



After building docker image, we need to run the image.

To run docker image : docker run -p localporthost :dockerhost dockerimagename



ex: docker run -p 8000:8000 studentapi



this gives o/p as running on http ://0.0.0.0:8000/

Refer to the IP address of docker in docker terminal. say , 192.168.99.100 

give this along with the port number in web

192.168.99.100:8000

This opens the UI.

Thus a docker container is created.
