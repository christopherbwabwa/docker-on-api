## Docker-on-api

A Docker application containing an api service & a React app.

## Installation

via docker on the terminal
```gitbash
$ docker-compose up
```
This command will build 2 services, one for the api data and the second for the front-end

```yaml
version: '3.8'
services:
  api:
    build: ./api
    container_name: api_c
    ports:
      - '4000:4000'
    volumes:
      - ./api:/app
      - /app/node_modules
  
  frontend:
    build: ./myblog
    container_name: myblog_c
    ports:
      - '3000:3000'
    stdin_open: true
    tty: true

```

## Usage

Once those images are build, you can listen the api on your browser with this uri:

> http://localhost:4000

And to check if the react app is retrieving those data you can check this uri:

http://localhost:3000

It will retrieve data from the api and show it on it own front-end.
