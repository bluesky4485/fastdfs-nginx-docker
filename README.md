# Docker for fastdfs-nginx

[fastdfs](https://github.com/happyfish100/fastdfs)


# Supported tags and respective `Dockerfile` links

- [`latest` (*Dockerfile*)](https://github.com/bluesky4485/fastdfs-nginx-docker/blob/master/Dockerfile)

## Simplest docker run example

```
docker network create fastdfs-net
docker run -dit --network=fastdfs-net --name tracker -v /var/fdfs/tracker:/var/fdfs kolehank/fastdfs-nginx-docker:latest tracker
docker run -dit --network=fastdfs-net --name storage -e TRACKER_SERVER=tracker:22122 -v /var/fdfs/storage0:/var/fdfs kolehank/fastdfs-nginx-docker:latest storage

```

