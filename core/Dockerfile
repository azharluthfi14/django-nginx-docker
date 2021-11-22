# Pull from official base image python
FROM python:3.9.8-alpine

# Setting location work directory
WORKDIR /usr/src/app

# Set environment variables 
ENV PYTHONUNBUFFERED 1
ENV PYTHONDONTWRITEBYTECODE 1 

# Installing dependencies
RUN pip install --upgrade pip
COPY ./requirements.txt .
RUN pip install -r requirements.txt

# Copy file project
COPY . .