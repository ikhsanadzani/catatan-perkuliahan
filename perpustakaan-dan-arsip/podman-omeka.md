# Deploy omeka pada podman
## Perkondisian jika meminta password root

```
sudo usermod --add-subuids 100000-165535 --add-subgids 100000-165535 nama_user
```

```
mkdir -p ~/.config/containers
podman system migrate
```
## test tanpa sudo untuk podman
```
podman run hello-world
```
### Output
```
Resolved "hello-world" as an alias (/etc/containers/registries.conf.d/00-shortnames.conf)
Trying to pull quay.io/podman/hello:latest...
Getting image source signatures
Copying blob 81df7ff16254 done   | 
Copying config 5dd467fce5 done   | 
Writing manifest to image destination
!... Hello Podman World ...!

         .--"--.           
       / -     - \         
      / (O)   (O) \        
   ~~~| -=(,Y,)=- |         
    .---. /`  \   |~~      
 ~/  o  o \~~~~.----. ~~   
  | =(X)= |~  / (O (O) \   
   ~~~~~~~  ~| =(Y_)=-  |   
  ~~~~    ~~~|   U      |~~ 

Project:   https://github.com/containers/podman
Website:   https://podman.io
Desktop:   https://podman-desktop.io
Documents: https://docs.podman.io
YouTube:   https://youtube.com/@Podman
X/Twitter: @Podman_io
Mastodon:  @Podman_io@fosstodon.org
```

## Podman Desktop
> ketika ingin menjalankan omeka pada podman harus membuat wadah dan mengatur port agar Omeka bisa diakses dari browser.
```
podman pod create --name omeka-pod -p 8080:80
```

```
podman run -d --name omeka-db \
  --pod omeka-pod \
  -e MYSQL_ROOT_PASSWORD=1313 \
  -e MYSQL_DATABASE=omeka_db \
  -e MYSQL_USER=omeka_user \
  -e MYSQL_PASSWORD=1212 \
  docker.io/library/mariadb:10.11
```

```
podman run -d --name omeka-web \
  --pod omeka-pod \
  -e ADMIN_EMAIL=kelompok7@gmail.com \
  -e ADMIN_PASSWORD=1414 \
  -e DB_USER=omeka_user \
  -e DB_PASSWORD=1212 \
  -e DB_NAME=omeka_db \
  -e DB_HOST=127.0.0.1 \
  docker.io/elestio/omeka:latest
```
