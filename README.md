# Movie app

## Development setup
Install Python 3.8

### Env
Create a virtual environment: <br/>
`python3 -m env venv`

To activate a venv: <br/>
`source env/bin/activate`

Install dependencies: <br/>
`pip install -r requirements.txt`

### Docker

[Install Docker](https://docs.docker.com/get-docker/)
```
docker -v
Docker version 19.03.5, build 633a0ea

docker-compose -v
docker-compose version 1.25.4, build 8d51620a
```
Build the image:

`docker-compose build`

Fire up the container in detached mode:

`docker-compose up -d`

Go to http://localhost:8000/ and check the server is running.

If you have errors, you may use:

`docker-compose logs -f`

To bring down containers and associated volumes use `-v` flag:

`docker-compose down -v`

Build the new image and spin up the two containers:
`docker-compose up -d --build`

Tu run migrations:

`docker-compose exec movies python manage.py migrate --noinput`

To check the default Django tables were created:

`docker-compose exec movies-db psql --username=movies --dbname=movies_dev`

To create a superuser:

In the first terminal:

`docker-compose up`

In the second terminal:

`docker-compose exec movies python manage.py createsuperuser`

## Migrate db:
`python manage.py makemigrations` <br>
`python manage.py migrate`

## Test

`python manage.py test`

## To create an admin account:

`python manage.py createsuperuser`

## To run server:

`python manage.py runserver`

## Additional information when you make changes to the database in models.py

- in the first terminal use command below

`docker-compose up`

- in the second terminal:

check if the tests passed

`docker-compose exec movies pytest`

if everything works fine use the commands below:

`docker-compose exec movies python manage.py makemigrations` <br/>
`docker-compose exec movies python manage.py migrate`

## Access API

ToDo

## Stack ToDo:

- Python
- Django
- Docker
- Postgres
- Pytest
- Django REST Framework
- Gunicorn
- Coverage.py
- flake8
- Black
- isort
- HTTPie
- Heroku
- WhiteNoise
- Swagger/OpenAPI
- GitHub

## Info

An application inspired by a tutorial.

## Personal goals

Learning TDD, Docker and other technologies.