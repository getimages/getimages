# GetImages

A place for sharing Docker images to ditch the Docker Hub

## Why GetImages?

We love GitHub! We like to use its docker image registry instead of the Docker Hub service. That's it!

## Where is the shared images?

All the shared Docker images are available here:

[https://github.com/orgs/getimages/packages](https://github.com/orgs/getimages/packages)

## How to publish a new image?

First, you need to be a member. To do so, create a new issue on this repository.

Then tag your local image with the following command:
```
# Command:
docker tag {LOCAL-IMAGE-ID} ghcr.io/getimages/{IMAGE-NAME}:{IMAGE-TAG}

# Example:
docker tag cc8775c0fe94 ghcr.io/getimages/nginx:1.19.3-alpine
```

In the end, push it to this registry with this command:
```
# Command:
docker push ghcr.io/getimages/{IMAGE-NAME}:{IMAGE-TAG}

# Example:
docker push ghcr.io/getimages/nginx:1.19.3-alpine
```

## How to use the shared images?

Example of pulling an image:
```
docker pull ghcr.io/getimages/nginx:1.19.3-alpine
```

Example of using an image in a Docker-compose file:
```
services:
  mysql:
    image: ghcr.io/getimages/nginx:1.19.3-alpine
```

Example of using an image in a Dockerfile:
```
FROM ghcr.io/getimages/nginx:1.19.3-alpine
```

## Does is helpful to you?

* Star this repository
* Be a member and share popular images
