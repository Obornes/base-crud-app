# Obornes DevOps/SRE Challenge - Vote App

This is an App Vote designed to be used in our Challenge **Time to vote** on [this repository](https://github.com/bryjai/challenges).

This App was created from the Django tutorial that you can find [here](https://docs.djangoproject.com/en/4.1/intro/tutorial01/).
Its main functionality is to vote in a poll. It can have many questions and each question can have many choices.

## Installing Django

To install the Django framework you should create a venv, add it to your path and install the requirements:

```shell
python3 -m venv venv
export PATH=$(pwd)/venv/bin:$PATH
pip install -r requirements.txt
```

## Running the migration

Before running the App you must run the database migration:

```shell
# Running the database
docker run -d -p 5432:5432 -e POSTGRES_PASSWORD=postgres postgres
# Waiting for the database start
sleep 2
# Running the migration
python manage.py migrate
```

## Seeding the database

After the migration the database will be empty, you can run the following command to seed it with one example question:

```shell
python manage.py seed --mode=refresh
```

## Running the App

You can run the App with the following commands:

```shell
python manage.py runserver
```
