<img src="https://cdn-icons-png.flaticon.com/512/5969/5969059.png" width="100" height="100" alt="Docker">

# Docker

## ⁉️ Overview
Docker is a platform that enables developers to easily create, deploy, and run applications in containers. Containers are lightweight, portable, and self-contained environments that can run on any machine that supports Docker.
<details><summary>...more</summary>
To get started with Docker, you would typically create a Dockerfile that specifies the base image for your application and any additional dependencies that are required. You can then use the `docker build` command to create a Docker image from the Dockerfile.

Once you have created a Docker image, you can use the `docker run` command to start a container from the image. This will launch a new instance of the application in a container. You can use various flags with the `docker run` command to specify how the container should be run and to map ports, volumes, and other resources between the container and the host machine.

Docker-compose is another tool that simplifies the management of multiple containers. With Docker-compose, you can define a set of containers and their configuration in a single file, and then use the `docker-compose` command to start, stop, and manage the containers as a group.

Overall, Docker provides a powerful and flexible platform for building and deploying applications in a consistent and repeatable way.
</details>


## **🧑‍🎓** Resources
<details><summary>Here are some helpful resources for learning about Docker:</summary>

### **Official Documentation**

- **[Docker Docs](https://docs.docker.com/)** - the official documentation for Docker, includes tutorials, user guides, and API reference.
- **[Docker Curriculum](https://docker-curriculum.com/)** - This free online course provides a comprehensive introduction to Docker. It includes both theory and practical exercises to help you get started with Docker.
- **[Docker for Beginners](https://dev.to/azure/docker-for-beginners-from-zero-to-hero-3o16)** - This tutorial is a great introduction to Docker for beginners. It covers everything you need to know to get started, from installing Docker to building and running containers.
- **[Dockerizing a Node.js web app](https://nodejs.org/en/docs/guides/nodejs-docker-webapp/)** - This tutorial shows you how to Dockerize a Node.js web app. It covers creating a Dockerfile, building the image, and running the container.
- **[Dockerizing Flask with Postgres, Gunicorn, and Nginx](https://testdriven.io/blog/dockerizing-flask-with-postgres-gunicorn-and-nginx/)** - This tutorial shows you how to Dockerize a Flask app with Postgres, Gunicorn, and Nginx. It covers creating a Dockerfile, building the image, and running the container.

### **Online Courses**

- **[Docker Mastery: with Kubernetes +Swarm from a Docker Captain](https://www.udemy.com/course/docker-mastery/)** - an in-depth course covering Docker and containerization, with a focus on using Docker with Kubernetes and Swarm.
- **[Docker for Developers](https://www.pluralsight.com/courses/docker-for-developers)** - a comprehensive course that covers the fundamentals of Docker, including containerization, images, and networking.
- **[Docker and Kubernetes: The Complete Guide](https://www.udemy.com/course/docker-and-kubernetes-the-complete-guide/)** - a popular course that covers both Docker and Kubernetes, with a focus on deploying containerized applications to the cloud.

### **Books**

- **[Docker Deep Dive](https://www.amazon.com/Docker-Deep-Dive-Nigel-Poulton/dp/1521822808)** by Nigel Poulton - a comprehensive guide to Docker, with a focus on architecture, deployment, and troubleshooting.
- **[The Docker Book: Containerization is the new virtualization](https://www.amazon.com/Docker-Book-Containerization-new-virtualization-ebook/dp/B00LRROTI4)** by James Turnbull - a popular guide to Docker, covering everything from the basics to more advanced topics like clustering and deployment.
</details>


### 💻 Commands
<details><summary>Here are 20 of the most commonly used Docker commands:
</summary>

- **`docker run`**: This command is used to run a Docker container.
- **`docker pull`**: This command is used to download a Docker image from a registry.
- **`docker build`**: This command is used to build a Docker image from a Dockerfile.
- **`docker ps`**: This command is used to list running Docker containers.
- **`docker images`**: This command is used to list Docker images on your system.
- **`docker stop`**: This command is used to stop a running Docker container.
- **`docker rm`**: This command is used to remove a Docker container.
- **`docker rmi`**: This command is used to remove a Docker image.
- **`docker exec`**: This command is used to execute a command inside a running Docker container.
- **`docker logs`**: This command is used to view logs for a running Docker container.
- **`docker network create`**: This command is used to create a Docker network.
- **`docker network ls`**: This command is used to list Docker networks on your system.
- **`docker network connect`**: This command is used to connect a Docker container to a network.
- **`docker network disconnect`**: This command is used to disconnect a Docker container from a network.
- **`docker-compose up`**: This command is used to start a set of Docker containers defined in a **`docker-compose.yml`** file.
- **`docker-compose down`**: This command is used to stop and remove the set of Docker containers defined in a **`docker-compose.yml`** file.
- **`docker inspect`**: This command is used to view detailed information about a Docker container or image.
- **`docker save`**: This command is used to save a Docker image to a file.
- **`docker load`**: This command is used to load a Docker image from a file.
- **`docker tag`**: This command is used to tag a Docker image with a specific name and version.

These are just a few of the most commonly used Docker commands. There are many more commands and options available, so it's worth exploring the Docker documentation to learn more.
</details>


### 📦 Running a Docker container

Docker comes with an example image, that contains a http webpage with tutorials.

`docker run -d -p 80:80 docker/getting-started`

You'll notice a few flags being used. Here's some more info on them:

- `d` - run the container in detached mode (in the background)
- `p 80:80` - map port 80 of the host to port 80 in the container
- `docker/getting-started` - the image to use
- `rm` - remove when done
- `it` - interactive
- `--entrypoint=bash`  defines where to start from

You can combine single character flags to shorten the full command. As an example, the command above could be written as:

`docker run -dp 80:80 docker/getting-started`

`docker run -it python:3.9` → runs a docker instance with python in interactive mode

`docker run -it --entrypoint=bash  python:3.9`  → same as above, but starting in bash

</br>

### ✍️ Writing a docker file


1. **`FROM`**: </br>
This specifies the base image that you want to use for your Docker image. For example, you might use **`FROM postgres:13`** to use the official postgres 13 image as the base image for your application.
2. **`COPY`** or **`ADD`**: </br>
This allows you to copy files from your local machine into the container. For example, you might use **`COPY . /app`** to copy all the files from the current directory on your local machine into the **`/app`** directory inside the container.
    <details><summary>The difference between COPY and ADD</summary>

    In Docker, **`COPY`** and **`ADD`** are similar commands, but they have some differences that make them not entirely interchangeable.

    **`COPY`** is used to copy files or directories from the host machine to the container. It takes two arguments: the source path on the host machine and the destination path in the container. For example:

    ```
    COPY src/app.py /app/
    ```
    This will copy the app.py file from the src directory on the host machine to the /app/ directory in the container.

    **`ADD`** is similar to **`COPY`**, but it also has some additional features. In addition to copying files, it can also extract compressed archives (such as .tar, .tar.gz, or .zip) and download files from URLs. It takes two arguments: the source path on the host machine or URL and the destination path in the container. For example:

    ```
    ADD https://example.com/archive.tar.gz /app/
    ```
    This will download the archive.tar.gz file from the specified URL and extract it to the /app/ directory in the container.

    However, because **`ADD`** has additional functionality, it is generally recommended to use COPY unless you specifically need the additional features provided by **`ADD`**. This is because COPY is more transparent in terms of what it does, whereas **`ADD`** can have unexpected behavior in certain situations (such as when the source is a URL and the server is down).

    In summary, while **`COPY`** and **`ADD`** are similar, they have some differences that make them not entirely interchangeable. It is generally recommended to use COPY unless you specifically need the additional functionality provided by ADD.
    </details>

3. **`RUN`**: </br>
This allows you to run commands inside the container during the build process. For example, you might use **`RUN npm install`** to install dependencies for your Node.js application.
4. **`WORKDIR`**: </br>
This sets the working directory inside the container. For example, you might use **`WORKDIR /app`** to set the working directory to **`/app`**.
5. **`EXPOSE`**: </br>
This specifies which ports the container should listen on. For example, you might use **`EXPOSE 3000`** to indicate that your application listens on port 3000.
6. **`CMD`** or **`ENTRYPOINT`**: </br>
This specifies the command that should be run when the container starts. For example, you might use **`CMD CMD ["python", "app.py"]`** to start your Python application.
Here's an example Dockerfile for a simple Python application:

    ```docker

    FROM python:3.9-slim
    WORKDIR /app
    COPY . /app
    RUN pip install -r requirements.txt
    EXPOSE 8000
    CMD ["python", "app.py"]

    ```

    In this example, we start with the official Python 3.9 slim image as the base image, set the working directory to **`/app`**, copy all the files from the current directory into the container's **`/app`** directory, install dependencies using **`pip install`**, specify that the container should listen on port 8000, and finally start the application using **`python app.py`** when the container starts.

    <details><summary>The difference between ENTRYPOINT and CMD</summary>

    In Docker, **`ENTRYPOINT`** and **`CMD`** are both used to define the command that should be run when the container starts, but they have different behaviors and purposes.

    **`CMD`** is used to define the default command that should be executed when the container starts. This command is usually specified as an array of strings, where the first element is the executable or script to run, and the subsequent elements are arguments to that command. If a user specifies a command at runtime when running the container, it will override the default command specified in **`CMD`**.

    For example, **`CMD ["npm", "start"]`** in a Dockerfile for a Node.js application will start the application using the **`npm start`** command by default when the container starts.

    **`ENTRYPOINT`**, on the other hand, is used to specify the executable or script that should always be executed when the container starts, regardless of any commands or arguments passed in at runtime. If a user specifies a command at runtime, the command and its arguments will be appended to the **`ENTRYPOINT`**.

    For example, **`ENTRYPOINT ["python", "app.py"]`** in a Dockerfile for a Python application will always start the application using the **`python app.py`** command, and any additional commands or arguments passed in at runtime will be appended to this command.

    In summary, while both **`ENTRYPOINT`** and **`CMD`** are used to define the command that should be run when the container starts, **`CMD`** is used to define the default command, while **`ENTRYPOINT`** is used to specify the executable or script that should always be executed, with any additional commands or arguments appended to it.
    </details>



### Docker-Compose

**`Docker-Compose`** simplifies the management and orchestration of multi-container Docker applications, by allowing you to define, launch, and manage the entire application stack with a single command.

Using Docker Compose, you can:

- Define the application stack: You can define the services, dependencies, and configurations for your multi-container application in a **`YAML`** file, using a simple and readable syntax.

- Launch the application: You can start up the entire application stack with a single command, which will create, configure, and start all the containers defined in the **`YAML`** file.

- Manage the containers: Docker Compose provides a range of commands to manage the containers, such as stopping, restarting, and removing the containers.

- Scale the services: You can scale up or down the number of instances of a service defined in the **`YAML`** file, using the docker-compose up --scale command.

- Share the environment: You can define the environment variables, networks, and volumes for your application, and share them across the containers in the stack.

- Debug and troubleshoot: Docker Compose provides tools for debugging and troubleshooting your application stack, such as viewing the logs and inspecting the container status.

**Here's an example of an ETL (extract, transform, load) pipeline using Docker containers.**

In this example, we have three services: **`extract`**, **`transform`**, and **`load`**. Each service is defined by an image, a command to run, and any necessary environment variables or volumes.

1. Extract:

    The **`extract`** service runs a Python script **`extract.py`** that fetches data from an API specified by the **`SOURCE_URL`** environment variable and stores it in a file **`data/raw_data.csv`** inside the container. The **`./data`** volume maps this file to a local directory so that it can be accessed outside the container.

    In this stage, we extract data from the source system. We can use a Docker container to run an application that fetches data from the source system and stores it in a file or a database. For example, we might use a Python script to fetch data from a REST API and store it in a CSV file. We can create a Docker image for this script and run it as a container.

    Here's an example Dockerfile for your **`my-extract-image`**:

    ```docker
    FROM python:3.9-slim-buster

    WORKDIR /app

    COPY requirements.txt .
    RUN pip install --no-cache-dir -r requirements.txt

    COPY extract.py .

    CMD ["python", "extract.py"]

    ```

    In this Dockerfile, we're using the **`python:3.9-slim-buster`** base image, which is a lightweight version of Python 3.9 on the Debian Buster operating system.

    We're setting the working directory to **`/app`** and copying the **`requirements.txt`** file to the image. We're then installing the Python dependencies specified in **`requirements.txt`** using **`pip`**.

    Next, we're copying the **`extract.py`** file to the image.

    Finally, we're setting the default command for the container to run the **`extract.py`** script using Python.

2. Transform:

    The **`transform`** service runs a Python script **`transform.py`** that reads the raw data from **`data/raw_data.csv`**, performs some transformations, and stores the transformed data in a file **`data/transformed_data.csv`** inside the container.

    In this stage, we transform the data into a format that can be used by the target system. We can use a Docker container to run an application that performs the necessary transformations on the data. For example, we might use a Python script to filter, aggregate, or join the data. We can create a Docker image for this script and run it as a container.

    Here's an example Dockerfile for your **`my-transform-image`**:

    ```docker
    FROM python:3.9-slim-buster

    WORKDIR /app

    COPY requirements.txt .
    RUN pip install --no-cache-dir -r requirements.txt

    COPY transform.py .

    CMD ["python", "transform.py"]
    ```

3. Load:

    The **`load`** service runs a Python script **`load.py`** that reads the transformed data from **`data/transformed_data.csv`** and loads it into a MySQL database specified by the **`TARGET_URL`** environment variable. The **`./data`** volume maps the file to a local directory so that it can be accessed outside the container.

    In this stage, we load the transformed data into the target system. We can use a Docker container to run an application that loads the data into a database, a file, or a messaging system. For example, we might use a Python script to insert the data into a MySQL database. We can create a Docker image for this script and run it as a container.

    Here's an example Dockerfile for your **`my-load-image`**:

    ```docker
    FROM python:3.9-slim-buster

    WORKDIR /app

    COPY requirements.txt .
    RUN pip install --no-cache-dir -r requirements.txt

    COPY load.py .

    CMD ["python", "load.py"]
    ```

### Compose

Now we can put everything together in a `docker-compose.yaml` file:

```yaml
version: '3'
services:
  extract:
    image: my-extract-image
    command: python extract.py
    volumes:
      - ./data:/app/data
    environment:
      - SOURCE_URL=http://example.com/api
  transform:
    image: my-transform-image
    command: python transform.py
    volumes:
      - ./data:/app/data
  load:
    image: my-load-image
    command: python load.py
    volumes:
      - ./data:/app/data
    environment:
      - TARGET_URL=mysql://user:password@localhost:3306/mydb

```

The **`extract`** service runs a Python script **`extract.py`** that fetches data from an API specified by the **`SOURCE_URL`** environment variable and stores it in a file **`data/raw_data.csv`** inside the container. The **`./data`** volume maps this file to a local directory so that it can be accessed outside the container.

The **`transform`** service runs a Python script **`transform.py`** that reads the raw data from **`data/raw_data.csv`**, performs some transformations, and stores the transformed data in a file **`data/transformed_data.csv`** inside the container.

The **`load`** service runs a Python script **`load.py`** that reads the transformed data from **`data/transformed_data.csv`** and loads it into a MySQL database specified by the **`TARGET_URL`** environment variable. The **`./data`** volume maps the file to a local directory so that it can be accessed outside the container.

Run it:


`docker-compose up`

Run in detached mode:

`docker-compose up -d`

Shutting it down:

`docker-compose down`
</details>

## passing environment variables to dockerfile

<details><summary>A lot to read here:</summary>

[Docker ARG, ENV and .env - a Complete Guide](https://vsupalov.com/docker-arg-env-variable-guide)
 </br>
This article provides a complete guide on working with Docker ARG, ENV, env_file, and .env files. It explains that the .env file is only used during a pre-processing step when working with docker-compose.yml files. ARG is only available during the build of a Docker image, while ENV values are available to containers and RUN-style commands during the Docker build. The article also covers setting ARG and ENV values, overriding ENV values, and the availability of ARG and ENV variables during the Docker build and running a container. Overall, the article provides useful insights and tips for configuring Docker images and dockerized apps with ease.Finally, the article suggests avoiding using ARG and ENV values for secrets that are not meant to stick around.
</details>
Environment file .env can provide variables, that can be used in Docker compose.

</br>

Define a variable in the **`.env`** file:
```
SOURCE_URL = www.somthing.com
```

Use it in **`docker-compose.yaml´** file:
```
environment:
      - SOURCEURL=${SOURCEURL}
```
After running the container, the variable is availlable inside the container.
