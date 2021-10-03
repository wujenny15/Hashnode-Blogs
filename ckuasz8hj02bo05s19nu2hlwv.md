## Docker Cheatsheet

### Delete all containers including its volumes
```bash
docker rm -vf $(docker ps -a -q)
```

### Delete all the images
```bash
docker rmi -f $(docker images -a -q)
```