# dockerfiles

My Docker images for local environments.

## Disclaimer

I created this simple images for development purposes only. Please, avoid use this on production environments.

## Building an image

```bash
docker build --tag {image name}:{image tag} .
```

```bash
docker build --tag {image name}:{image tag} \
    --build-arg DOCKER_HUB_IMAGE_TAG={image tag from Docker Hub} \
    --build-arg USER_ID={user ID} \
    --build-arg GROUP_ID={group ID} \
    --build-arg USER={username} \
    --build-arg password={password} \
    .
```
