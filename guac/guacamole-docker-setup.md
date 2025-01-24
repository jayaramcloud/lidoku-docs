1. Run the guacamole docker image
```bash
sudo docker run --name guacamole-cors \
    --link postgres-guacamole:postgres \
    --link guacd:guacd \
    -e POSTGRES_HOSTNAME=postgres \
    -e POSTGRES_DATABASE=guacamole_db \
    -e POSTGRES_USER=guacamole_user \
    -e POSTGRES_PASSWORD=guacamole_user \
    -p 8080:8080 \
    -d rahulpeacock/guacamole-cors
```

2. Push the image to docker hub
```bash
sudo docker push rahulpeacock/guacamole-cors
```

3. Editing the docker image locally
```bash
sudo docker exec -it guacamole-cors /bin/bash
```

4. Commit a docker container
```bash
sudo docker commit <CONTAINER_ID> rahulpeacock/guacamole-cors
```

5. Strop the container
```bash
sudo docker stop <CONTAINER_ID>
```

6. Get the logs of the container
```bash
sudo docker logs -f <CONTAINER_ID>
```

7. Update the web.xml file
```bash
cd /home/guacamole/tomcat/webapps/guacamole/WEB-INF/
```
