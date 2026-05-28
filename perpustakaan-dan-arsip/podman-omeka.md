# Deploy omeka pada podman
```
sudo pacman -S podman-compose
```

# membuat file compose nya
```
nvim compose.yml
```

# config compose.yml
```
version: '3'

services:
  db:
    image: docker.io/library/mariadb:10.11
    container_name: omeka-db
    environment:
      MYSQL_ROOT_PASSWORD: kelompok7
      MYSQL_DATABASE: omeka
      MYSQL_USER: omeka
      MYSQL_PASSWORD: [tambahkan password]
    volumes:
      - db_data:/var/lib/mysql:Z
    restart: always

  omeka:
    image: docker.io/omeka/omeka-s:latest
    container_name: omeka-app
    ports:
      - "8080:80"
    environment:
      DB_TYPE: mysql
      DB_HOST: db
      DB_NAME: omeka
      DB_USER: omeka
      DB_PASSWORD: [password harus sama kayak di MYSQL_PASSWORD]
      DB_PORT: 3306
    volumes:
      - files_data:/var/www/html/files:Z
    depends_on:
      - db
    restart: always

volumes:
  db_data:
  files_data:
```
# aktifkan container 
```
podman-compose up -d
```

# Menghapus berkas konfigurasi bawaan yang macet
```
podman exec -it omeka-app rm -f /var/www/html/config/database.ini
```
```
podman exec -it omeka-app sh -c "cat <<EOF > /var/www/html/config/database.ini
user     = \"omeka\"
password = \"kelompok7\"
dbname   = \"omeka\"
host     = \"db\"
port     = 3306
type     = \"mysql\"
EOF"
```

```
podman restart omeka-app
```
