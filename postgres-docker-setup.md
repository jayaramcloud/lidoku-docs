1. Install postgresql docker image from docker hub
```bash
sudo docker run bitnami/postgresql:17.0.0-debian-12-r1
```

2. Configure database, username and password for postgresql
```bash
POSTGRES_DATABASE: guacamole_db
POSTGRES_PASSWORD: guacamole_user@1a-z
POSTGRES_POSTGRES_PASSWORD: guacamole_user@1a-z
POSTGRES_USER: guacamole_user
```

3. Run postgresql docker image
```bash
sudo docker run --name postgres-guacamole \
  -e POSTGRES_DB=guacamole_db \
  -e POSTGRES_PASSWORD=guacamole_user \
  -e POSTGRES_USER=guacamole_user \
  -p 5432:5432 \
  -d bitnami/postgresql:17.0.0-debian-12-r1
```

4. Run postgresql docker container
```bash
sudo docker exec -it d94b0414815d /bin/sh
```

5. Login to postgresql
```bash
psql -U guacamole_user -d guacamole_db
```

6. Create database schema
You can use the following sql script present in the location
`extensions/guacamole-auth-jdbc/modules/guacamole-auth-jdbc-postgresql/schema/001-create-schema.sql` and `extensions/guacamole-auth-jdbc/modules/guacamole-auth-jdbc-postgresql/schema/002-create-admin-user.sql`





jay@jay-GE62-7RD:~/guac/guacamole-client$ sudo docker run --name postgres-guacamole \
  -e POSTGRES_DB=guacamole_db \
  -e POSTGRES_PASSWORD=guacamole_pass \
  -e POSTGRES_USER=guacamole_user \
  -p 5432:5432 \
  -d bitnami/postgresql:17.0.0-debian-12-r1
d94b0414815d218d15d1c01fbdbc91f460aab1c26d49e54c24091f29a2736aba

jay@jay-GE62-7RD:~/guac/guacamole-client$ sudo docker ps
CONTAINER ID   IMAGE                                    COMMAND                  CREATED         STATUS                  PORTS                                       NAMES
d94b0414815d   bitnami/postgresql:17.0.0-debian-12-r1   "/opt/bitnami/script…"   4 seconds ago   Up 3 seconds            0.0.0.0:5432->5432/tcp, :::5432->5432/tcp   postgres-guacamole

jay@jay-GE62-7RD:~/guac/guacamole-client$ sudo docker exec -it d94b0414815d /bin/sh
$ ls
bin	 boot  docker-entrypoint-initdb.d     etc   lib    media  opt	root  sbin  sys  usr
bitnami  dev   docker-entrypoint-preinitdb.d  home  lib64  mnt	  proc	run   srv   tmp  var

$ psql -U guacamole_user -d guacamole_db
Password for user guacamole_user: 
psql (17.0)
Type "help" for help.

paste
~/guac/guacamole-client/extensions/guacamole-auth-jdbc/modules/guacamole-auth-jdbc-postgresql/schema/001-create-schema.sql
~/guac/guacamole-client/extensions/guacamole-auth-jdbc/modules/guacamole-auth-jdbc-postgresql/schema/002-create-admin-user.sql

