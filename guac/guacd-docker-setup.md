1. Run the guacd docker image
```bash
sudo docker run --name guacd \
    -d \
    -p 4822:4822 \
    guacamole/guacd
```