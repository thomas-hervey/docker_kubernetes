## Commands
- `docker build .` giving docker file off to docker cli (which then gives it to the docker server)
- `docker run ${id}` calls `docker create` and `docker start`, and actually creates a container
- Tagging a container makes it easy to reference using `docker build -t ${docker id}/projectname:tag .`. For example `docker build -t thomashervey/projectName:latest`, can then be run using `docker run tomtom92/redis`
- We actually attach a container and start up a shell in it via a command like `docker exec -it ${container id} sh`. Remember the `-i` and `-t` flags help make sure there is an output and formatting it.