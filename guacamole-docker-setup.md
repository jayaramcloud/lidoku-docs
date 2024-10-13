1. Run the guacamole docker image
```bash
sudo docker run --name guacamole \
    --link postgres-guacamole:postgres \
    --link guacd:guacd \
    -e POSTGRES_HOSTNAME=postgres \
    -e POSTGRES_DATABASE=guacamole_db \
    -e POSTGRES_USER=guacamole_user \
    -e POSTGRES_PASSWORD=guacamole_user \
    -p 8080:8080 \
    -d guacamole/guacamole
```