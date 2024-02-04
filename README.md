# GetImages

It's a registry for sharing Docker images to ditch the Docker Hub.

## Images

[https://github.com/orgs/getimages/packages](https://github.com/orgs/getimages/packages)

## Pulling Images

Example of pulling an image:

```shell
docker pull ghcr.io/getimages/nginx:1.19.3-alpine
```

Example of using an image in a Docker-compose file:

```yaml
services:
  mysql:
    image: ghcr.io/getimages/nginx:1.19.3-alpine
```

Example of using an image in a Dockerfile:

```Dockerfile
FROM ghcr.io/getimages/nginx:1.19.3-alpine
```

## Pushing Images

First, you need to be a member.
To do so, create a new issue on this repository.
I'll accept you as soon as possible.

After being a member, follow these steps to push an image.

```shell
# Login docker (use your Github username and personal access token instead of password).
docker login ghcr.io

# Pull the official image from Docker Hub.
docker pull nginx:1.23.0

# Find the image ID.
docker images | grep nginx
# nginx    1.23.0    55f4b40fe486    3 months ago    142MB

# Tag the image to create a new one.
# docker tag {LOCAL-IMAGE-ID} ghcr.io/getimages/{IMAGE-NAME}:{IMAGE-TAG}
docker tag 55f4b40fe486 ghcr.io/getimages/nginx:1.23.0

# Push the new image.
# docker push ghcr.io/getimages/{IMAGE-NAME}:{IMAGE-TAG}
docker push ghcr.io/getimages/nginx:1.23.0
```

## P.S.

Was it helpful to you?
* Star this repository
* Be a member and share popular images
