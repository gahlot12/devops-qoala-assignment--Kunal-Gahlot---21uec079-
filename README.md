# DevOps Assignment Report

## Project: Debugging and Running a Dockerized Application

## Issues Identified

1. Nginx Build Error ->
   Error Message Recieved -> Error pulling local-nginx: repository does not exist or may require 'docker login'
   Description -> Initially I attempted to run the docker-compose-up without building the Nginx image first, which led to the error

2. Missing HTML Error ->
   Error Message Recieved -> failed to calculate checksum of ref: "/html": not found
   Description -> During the Nginx image build, the Dockerfile attempted to copy a file that doesn't exist leading to the build failure.

## Resoultion Steps Taken

1. Building Docker Images ->
   Resolved the initial error by manually building the Nginx image using the command ->
   docker build -t local-nginx ./nginx
   Built the python application image with -> docker build -t local-python-app ./python

2. Creating Missing HTML Directory ->
   To fix the missing html directory issue, I created the nginx/html directory and added an index.html file with a placeholder message <h1>Hello from Nginx!</h1>

3. Running the Application:
   Successfully launched the application using Docker Compose with ->
   docker-compose up

   Accessed Nginx logs to confirm successful request handling using ->
   docker-compose logs nginx

All identified issues were successfully resolved, and the Dockerized application is fully operational.
