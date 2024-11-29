# Docker Demonstrations with DSA

This repository demonstrates various use cases for Docker, including running a web server, creating a database, building custom Docker images, and using Docker Compose for managing services.

---

## 1. Requirements
Ensure you have the following installed:
- Docker
- Docker Compose

---

## 2. Running a Web Server

Run an Nginx web server on port 8080 using Docker:

bash
$ docker run -d -p 8080:80 nginx
Access the server at http://localhost:8080.

3. Creating a Custom Database
Set up a PostgreSQL database with custom configurations:
$ docker run --name database -p 5435:5432 -e POSTGRES_USER=dsa -e POSTGRES_PASSWORD=dsa1010 -e POSTGRES_DB=dsadb -d postgres:16.0
Parameters:
  POSTGRES_USER: Sets the database username (dsa).
  POSTGRES_PASSWORD: Sets the database password (dsa1010).
  POSTGRES_DB: Creates a database named dsadb.
Access the database at localhost:5435.

4. Building a Custom Docker Image
4.1. Create a Dockerfile
Create a file named Dockerfile with the following content:

FROM python:3.11-slim

COPY testedsa.py /testedsa.py

CMD ["python", "/testedsa.py"]

4.2. Create a Python Script
Create a file named testedsa.py with the following content:
print("Olá, Bem-Vindo(a) ao Docker com a DSA!")

4.3. Build the Docker Image
Run the following command to build the image:
$ docker build -t dsa-image .
Output:
Olá, Bem-Vindo(a) ao Docker com a DSA!

5. Using Docker Compose
5.1. Create a Docker Compose File
Create a file named docker-compose.yml with the following content:
version: '3'

services:
  web1:
    image: nginx
    ports:
      - "8080:80"

  web2:
    image: nginx
    ports:
      - "8081:80"
5.2. Run Docker Compose Commands
Start the services:
docker-compose up -d
Stop and remove the services:
docker-compose down
Access the services at:
http://localhost:8080 for web1
http://localhost:8081 for web2
![Screenshot from 2024-11-29 14-15-57](https://github.com/user-attachments/assets/82aad000-d475-444b-98d2-b9bebe7ba0e2)







