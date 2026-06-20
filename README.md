# Dockerized Flask Application

A minimal Python Flask web application containerized with Docker.
Built as a hands-on DevOps practice project demonstrating containerization
fundamentals.

## What This Demonstrates

- Writing a Dockerfile from first principles
- Containerizing a Python application with pinned dependencies
- Docker layer caching (dependencies copied before app code for efficient rebuilds)
- Using a slim base image to reduce image size and attack surface
- Port publishing between host and container

## Tech Stack

- Python 3.12
- Flask 3.0.3
- Docker

## How to Run

Build the image:

    docker build -t flask-hello .

Run the container:

    docker run -p 8080:5000 flask-hello

Then visit http://localhost:8080 in a browser.

## Key Concepts

The app listens on `0.0.0.0` (all interfaces) so requests forwarded from
outside the container are accepted. The container exposes port 5000 internally,
mapped to port 8080 on the host via the `-p` flag.
