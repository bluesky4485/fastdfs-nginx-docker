# Docker for fastdfs-nginx

[fastdfs](https://github.com/happyfish100/fastdfs)


# Supported tags and respective `Dockerfile` links

- [`latest` (*Dockerfile*)](https://github.com/bluesky4485/fastdfs-nginx-docker/blob/master/Dockerfile)

## Simplest docker run example

```
docker network create fastdfs-net
docker run -dit --network=fastdfs-net --name tracker -p 8888:80 -p 22122:22122 -v /var/fdfs/tracker:/var/fdfs kolehank/fastdfs-nginx-docker:latest tracker
docker run -dit --network=fastdfs-net --name storage -e TRACKER_SERVER=tracker:22122 -p 23000:23000 -v /var/fdfs/storage:/var/fdfs kolehank/fastdfs-nginx-docker:latest storage

```

## Upload file example
```
docker exec -it tracker sh
```
copy 1.jpg to `/var/fdfs/tracker`

```
/usr/bin/fdfs_upload_file /etc/fdfs/client.conf /var/fdfs/1.jpg 
```


http://localhost:8888/
