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

5. Building a Custom Docker Image
4.1. Create a Dockerfile
Create a file named Dockerfile with the following content:
![Screenshot from 2024-11-29 14-21-24](https://github.com/user-attachments/assets/491a98ed-a999-437e-bd33-dff02cdeba00)

4.2. Create a Python Script
Create a file named testedsa.py with the following content:
print("Olá, Bem-Vindo(a) ao Docker com a DSA!")

4.3. Build the Docker Image
Run the following command to build the image:
$ docker build -t dsa-image .
- Output:
![Screenshot from 2024-11-29 14-25-10](https://github.com/user-attachments/assets/7f8bb213-2ff9-4c96-bb9d-46ef909b6d50)


5. Using Docker Compose
5.1. Create a Docker Compose File
Create a file named docker-compose.yml with the following content:
![Screenshot from 2024-11-29 14-19-50](https://github.com/user-attachments/assets/1d4487b3-ab13-422a-9903-711d8d027056)

5.2. Run Docker Compose Commands
Start the services:
docker-compose up -d
Stop and remove the services:
docker-compose down
Access the services at:
http://localhost:8080 for web1
http://localhost:8081 for web2








