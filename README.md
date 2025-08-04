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

![Django + code-server mimarisi](https://uml.planttext.com/plantuml/png/PLCzRzim4DtrAmuU0Wcm71JTF1I9OpSjwhPEh7GnCh3IMQPDaG99sL2BpFaP7ZjxwPJDwlyAFoJKRW61uXqVxpqU7w-K9b9N1GiqrGnXl2Oy5t01toeSh1NCf5YZed2B71byfWMHD0XAacv8Zj0RYtI3iWS_0m3pBJAtFNu3Du9hGZdAHo2ghMe1smh_MpLKVdjB7iVlO3o28SplfbJZMxDY83xj4KFua2Gpk9vzXECpQVQoEJ1Y1WZl9_FaybQISdKtXUttGHG4JoTwfo8bR2MKzf8Ndoh626yEgTcR44bgDrNDmGaRIR5JA0smdJaDLiiGl8BmlJH7GPv5_u3EXOOZ8y2Y83p-bXoRFUL0iiACYjHBOWYZCvtjzgxxOL6NTfhgo0jFHL4AZbn3xulGgE2XpYj62bkfPwNxh8NQfbFSgK5PFpffYqeo5_d5GcHu6Y-5B4v2ZKN9Y2bsQHDF_g9EwEUeDUMvSgnTq16hDZRb81oF-d3pzNxUXwIhsJUEoZA6Eo8nylLD5xZH3fBcAmrY-TSxCJpOxbvNUcNk6NEgDCe-J4LEkVk9IaTENkoE3vCDmm9XYp2rM1VuPMkS2SzAGRanlQGcRMu7B75Bpt3fsBqtu-uvBDlhxkhKrdHfv-QCmF4NOStXpxuvr4Asg5EJMOyTNtuSNyuehypKli5N)





    
