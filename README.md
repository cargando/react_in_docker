# Getting Started with CRA in Docker Container

This project was bootstrapped with [Create React App](https://github.com/facebook/create-react-app).


In the project directory, you can run comands for DEV or PROD env.

## For Development

Build and tag the Docker image:
### `docker build -t sample:dev .`

Note the dot at the end. Then spin up the container:

```
docker run \
-itd \
--rm \
-v ${PWD}:/app \
-v /app/node_modules \
-p 3001:3000 \
-e CHOKIDAR_USEPOLLING=true \
sample:dev
```
Alternatively you may use docker-compose:

### `docker-compose up -d --build`

Finally, to stop run:
 
`docker-compose stop`


## For Production

Build and tag the Docker image:

### `docker build -f Dockerfile.prod -t sample:prod .`

Then spin up the container:

`docker run -it --rm -p 1337:80 sample:prod`

Fire up the container:

`docker-compose -f docker-compose.prod.yml up -d --build`

