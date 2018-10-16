# Help

### Make Docker Autostart at Startup
```
$ systemctl enable docker.service
```
### Delete the Repository
To delete everything e.g. to start from scratch you can use this:
```
&> make delete
```

**Warning**
`make delete` delete all volumes, leading to a loss of all your data. Make sure you have saved everything before you run it.

### Rebuild from Backup
If you want to start from scratch or reinitialse your MISP instance, make sure you have delete everything. Clone the repository and start the container deployment with `make start`. After that restore all your volumes as described at `Backup and Recovery`.

### Access the Container
To access the container e.g. to change MISP config.php or proxy config, you can use:
```
docker exec -it dcso/[container] bash
```
Container variants: `misp-robot` `misp-server` `misp-proxy` (for the ubuntu version only)

For the misp-proxy if you have alpine version:
```
docker exec -it dcso/misp-proxy sh
```

### Usefull Commands
To Delete all local Images:
```
docker system prune -a
```

To delete only all non-tagged (dangling) Images:
```
docker rmi $(docker images -f "dangling=true" -q)
```

List Logs
```
docker logs -f misp-server
```