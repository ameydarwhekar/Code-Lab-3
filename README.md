# Code-Lab-3
**Amey Darwhekar**
Code Lab 3 - Creation of 3 docker containers - PostgreSQL, pgAdmin and Django

Please execute in following order:

While you are in the db folder
docker build -t mydb .

While you are in the dba folder
docker build -t mydba

When you are in public folder
docker build -t my_django .

For creating network
docker network create mynetwork
docker network ls

For Running
docker run --name mydba --network mynetwork -p 8081:80 -d mydba
docker run --name mydb --network mynetwork -itd -p5432:5432 mydb

docker run -it -p8000:8000 --network mynetwork -v "$(pwd)/app:/app" my_django /bin/bash

Initially, you have to create project called app. This step could skipped later since the folder is already created once.
django-admin startproject app
python manage.py createsuperuser

Lastly, execute both these steps.
python /app/app/manage.py migrate
python manage.py runserver 0.0.0.0:8000

Submitted by Amey Darwhekar
