## Commands
- `docker build .` giving docker file off to docker cli (which then gives it to the docker server)
- `docker run ${id}` calls `docker create` and `docker start`, and actually creates a container
- Tagging a container makes it easy to reference using `docker build -t ${docker id}/projectname:tag .`. For example `docker build -t thomashervey/projectName:latest`, can then be run using `docker run tomtom92/redis`
- If we want to tag out output so we don't have to keep copying the id of the container, we can tag it like so `docker build -t tomtom92/docker-react -f Docker.dev .`
- We actually attach a container and start up a shell in it via a command like `docker exec -it ${container id} sh`. Remember the `-i` and `-t` flags help make sure there is an output and formatting it.
- If we are using **docker-compose**...
  - We can run `docker-compose up` instead of `docker run myimage`. Furthermore, instead of the typical `docker build .` and `docker run mymage` commands to build and run, we can run `docker-compose up --build`
  - Two commands for starting/stopping docker-compose commands are like starting/stopping docker-cli commands. To launch in background, add the `-d` flag like `docker-compose up -d`. We can close them down using `docker-compose down`
  - `docker-compose ps` must be run within a directory with *docker-compose*, and lists the docker-compose containers that are running given the ones in that compose file.
- To make sure a container updates when local changes are made, we need to change our *run* command. We can additionally put a bookmark on the *node_modules* folder, and map the pwd into the app folder like so: `docker run -p 3000:3000 -v /app/node_modules -v "$(pwd):/app" <image_id>`

## Deploy Notes
- When deploying to AWS, it's easiest to use Amazon's *Elastic Beanstalk*, but to run **one** container only.