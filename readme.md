# Complex Docker with Multi Containers Setup

[![Build Status](https://travis-ci.org/dalenguyen/complex-docker.svg?branch=master)](https://travis-ci.org/dalenguyen/complex-docker)

Setting multi containers from develoment to production.

## Getting Started

This is an simple React app that use Nginx for routing, and Express server for handling Redis and Progres Database.

## For Development

![Dev Diagram](https://raw.githubusercontent.com/dalenguyen/complex-docker/master/images/dev.png)

Build local images and containers. Obmit --build for the next run.

Docker-compose will build from Dockerfile.dev files.

```sh
docker-compose up --build
```

After this, you can access the app through: http://localhost:8080

Take them down

```sh
docker-compose down
```

## For Production

![Prod Diagram](https://raw.githubusercontent.com/dalenguyen/complex-docker/master/images/prod.png)

In this case, Javis CI/CD will create test images, run test and create prod images. The prod images will be pushed to Docker Hub or Private Registry. Travis will will push the project to AWS or other servers.

The AWS will pull images and start deploying.

For the Database Services, we better use outside services because they're secured, easy to scale and other awesome features like auto backup and rollback.

## Reference

[Docker and Kubernetes: The Complete Guide](https://www.udemy.com/docker-and-kubernetes-the-complete-guide/)