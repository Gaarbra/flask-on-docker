# Flask on Docker

[![Development Build](https://github.com/Gaarbra/flask-on-docker/actions/workflows/dev-build.yml/badge.svg)](https://github.com/Gaarbra/flask-on-docker/actions/workflows/dev-build.yml)

## Overview

This project is a simple Flask web application that I made while learning how Docker and different web services work together. It uses PostgreSQL for the database, Gunicorn to run the production application, and Nginx as the web server. The application also lets a user upload an image and view the uploaded image.

## Demo

The GIF below shows the webpage running, uploading an image, and viewing the uploaded image.

![Demo](docs/demo.gif)

## Development

Start the development version:

    docker compose up -d --build

The development app runs on port `5002` on the AMBA server.

Check the containers:

    docker compose ps

Stop the development version:

    docker compose down

## Production

Start the production version:

    docker compose -f docker-compose.prod.yml up -d --build

Create the database:

    docker compose -f docker-compose.prod.yml exec web python manage.py create_db

The production app runs through Nginx on port `1340` on the AMBA server.

Stop the production version:

    docker compose -f docker-compose.prod.yml down

## Uploading an Image

Go to `/upload`, choose an image, and upload it.

The uploaded image can then be viewed at:

    /media/IMAGE_FILE_NAME

## Technologies Used

- Flask
- Docker
- PostgreSQL
- Gunicorn
- Nginx
- GitHub Actions
