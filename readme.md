# Complex Docker with Multi Containers Setup

Setting multi containers from develoment to production.

## Getting Started

This is an simple React app that use Nginx for routing, and Express server for handling Redis and Progres Database.

## For Development

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

In this case, Javis CI/CD will create test images, run test and create prod images. The prod images will be pushed to Docker Hub or Private Registry. Travis will will push the project to AWS or other servers.

The AWS will pull images and start deploying.

## Reference

[Docker and Kubernetes: The Complete Guide](https://www.udemy.com/docker-and-kubernetes-the-complete-guide/)