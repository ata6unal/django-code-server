#  Django + Code-Server in Docker

This project sets up a Django web application with [code-server](https://github.com/coder/code-server) running in a Docker container. It allows full development and debugging experience directly from your browser.

## Requirements
- 🧰 Django web framework inside Docker
- 💻 code-server (VS Code in the browser) for remote development
- 🐳 Docker Compose for managing containers
- 🔎 Debugging via browser with breakpoints and hot reload

## 🚀 Quick Start

#### 1. Clone the Repository

```
git clone https://github.com/ata6unal/django-code-server.git
cd django-code-server

```
#### 2.Start the application
  ```
docker compose up --build
  ```
#### This will start:

Django server on http://localhost:8000

code-server on http://localhost:8080

## 🧠Default code-server Password
```
docker logs <your_code_server_container_name_or_id>
```
Or set your own password by adding the following to docker-compose.yml:
```
environment:
  - PASSWORD=my_secure_password
```
## 🛠How to Debug via Browser
1)Visit http://localhost:8080

2)Log in to code-server

3)Open the folder /app

4)Make sure Python interpreter is set to /app/venv/bin/python

5)Add breakpoints

6)Start the Django server with:
```
python3 manage.py runserver 0.0.0.0:8000
```
## Python Virtual Environment
The virtual environment is automatically created in the Dockerfile as /app/venv. All dependencies are installed there via:
```
RUN python3 -m venv /app/venv \
  && . /app/venv/bin/activate \
  && pip install -r requirements.txt
```
## 🗂Folder Structure
```
├── Dockerfile
├── docker-compose.yml
├── manage.py
├── myproject/           # Django project folder
├── requirements.txt
└── README.md
```
## 🌍Deployment
-This setup is ideal for:

-Personal development environments

-Remote containers (e.g., VPS)

-Teaching or demos

## 🎨PUML

It gives you a simpler visualize for the project with a PUML.

![Django + code-server mimarisi](https://uml.planttext.com/plantuml/png/NLAzRjim4Dxv58TCDkgVFKEHE8OBD4tImesN8CF5kWgCA5AWA1T2aRcFeR5hjMJA9lczUYHbr-qatdq_-kx8YzAXTLMkX9DE4QmgfQPhXziCbi-eKmFlO5FHxBc4M-FWlauhXJcMVIi4RfsnS5-I5Q9W1QO4Pojhj2ETm2ZAncVmGm0yN2O96z1iLn5ScRmmchHx12nXG0AfA3mXjej2l9mOB_WGV6EkmVS8UuiWYdqssqdwNiwAEhXjV17xkKb87O6RK4Nacx7v4LZvWlilFjYmYyiabte8pQU0eCCdB0b6wo-VfADnW9SBdzsl1gRJzuSHuJmiaJB5AplqF1xICVhvRlqLvbZ8-TOIEffgPinXz75zTpiMaUNvCNIq8p2gsZUkifMTGCRtXxfljtrRAmIfvBx9fEB5IIkj68JUOxbW_OQiX0phX1AcsjF4F1yJuhT0JKhM_3uua4BRjv1shxPxqwvxyyCSTOT9hh7kMpU13_pRVJE1xcVVPdsxRu1BHJcBvCb08Sprt-pm95KgFKbBI4pVM7vs5dO4TVUgoN5KmNVzttBxtzqlbcG-NEduzA_YWhVWN_eV)





    
