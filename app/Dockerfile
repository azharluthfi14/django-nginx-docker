# Pull from official base image python
FROM python:3.9.8-alpine

# Setting location work directory
WORKDIR /usr/src/app

# Set environment variables 
ENV PYTHONUNBUFFERED 1
ENV PYTHONDONTWRITEBYTECODE 1 

# Installing psycop2 dependencies
RUN apk update \
    && apk add postgresql-dev gcc python3-dev musl-dev

# Installing dependencies
RUN pip install --upgrade pip
COPY ./requirements.txt .
RUN pip install -r requirements.txt

# Copy file entrypoint.sh
COPY ./entrypoint.sh .
RUN sed -i 's/\r$//g' /usr/src/app/entrypoint.sh
RUN chmod +x /usr/src/app/entrypoint.sh

# Copy file project
COPY . .

# Run entrypoint.sh
ENTRYPOINT ["/usr/src/app/entrypoint.sh"]