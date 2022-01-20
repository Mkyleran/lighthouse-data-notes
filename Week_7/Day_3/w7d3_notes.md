# W7D3 notes

## Today

NoSQL and Docker

## Core

### MongoDB

### Docker Containers

>Containers and VMs are similar in their goals: to isolate an application and its dependencies into a self-contained unit that can run anywhere.

>A VM is essentially an emulation of a real computer that executes programs like a real computer

>containers *share* the host system’s kernel with other containers

>A container is an instance of an image

`docker run  --rm  -p 8888:8888  -v <YOUR WORKING DIR>:/home/jovyan/work/  jupyter/pyspark-notebook`

### Apache Spark

- Resilient Distributed Datasets (RDDs)