# DOCKER MICROSERVICE DEMO

Application was built in demo purpose

## Dependencies

* [Node Express Api Demo](https://github.com/Bomavi/node-express-api-demo)
* [React MobX Demo](https://github.com/Bomavi/react-mobx-demo)
* [React Redux Demo](https://github.com/Bomavi/react-redux-demo)
* [React Hooks Demo](https://github.com/Bomavi/react-hooks-demo)

## Features

* Microservice architecture
* Reverse proxy
* Load balancing

## Running application

This application depends on [Docker](https://www.docker.com/) and [Docker Compose](https://docs.docker.com/compose/), so before going ahead, be sure, you have installed [Docker](https://www.docker.com/) and [Docker Compose](https://docs.docker.com/compose/) locally. Then, follow instructions below:<br>

1. Create `demos` folder and go inside
1. Clone next repositories
    > ```bash
    > git clone https://github.com/Bomavi/docker-microservice-demo.git
    > git clone https://github.com/Bomavi/node-express-api-demo.git
    > git clone https://github.com/Bomavi/react-mobx-demo.git
    > git clone https://github.com/Bomavi/react-redux-demo.git
    > git clone https://github.com/Bomavi/react-hooks-demo.git
    > ```
1. As we will use port 80, it should be free, if you have nginx locally or other similar application, you have to turn them off, eg for unix like systems `sudo service nginx stop`
1. Choose project which you want to see
    > ```bash
    > cd docker-microservice-demo/react-mobx
    > cd docker-microservice-demo/react-redux
    > cd docker-microservice-demo/react-hooks
    > ```
1. Execute following command to run docker-compose, it will take some time
    > ```bash
    > docker-compose -f docker-compose.dev.yml up -d
    > ```
1. Or you can create alias to write it shorter, eg `alias devdc="docker-compose -f docker-compose.dev.yml"` and then
    > ```bash
    > devdc up -d
    > ```
1. If there are no errors, you can visit http://localhost and check application
1. If there is error with proxy container about port 80, go back to step 3
1. To stop docker-compose run
    > ```bash
    > docker-compose -f docker-compose.dev.yml down
    > ```
1. To see logs, you can run
    > ```bash
    > docker-compose -f docker-compose.dev.yml logs -f proxy
    > docker-compose -f docker-compose.dev.yml logs -f api
    > docker-compose -f docker-compose.dev.yml logs -f frontend
    > ```
1. After all, after you are done, to remove all the images
    > ```bash
    > docker images
    > docker image prune -a
    > ```
1. Or you can delete by IMAGE_ID
    > ```bash
    > docker images
    > docker rmi -f IMAGE_ID
    > ```

## TODO

- [x] application code base
- [x] microservice architecture
- [x] reverse proxy
- [ ] microservice communication
- [ ] load balancing
- [ ] unit tests
