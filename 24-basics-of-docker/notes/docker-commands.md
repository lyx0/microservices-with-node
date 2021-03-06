# Docker Commands

## Commands

- Create and run

  - docker run [image name] [alternate commands]

- Docker start

  - docker start [image name]

- Docker create

  - docker create [image name]

- List running containers

  - docker ps
    - Gives container ID, Image, Command, Created, Status, Ports, Names

- Start

  - docker start [container id]
  - and attach
    - docker start -a [container id]

- Stop a container

  - if after 10 seconds it hasn't stopped it'll send docker kill automatically
  - docker stop [container id]

- Kill a container

  - docker kill [container id]

- Remove al stopped containers

  - docker system prune

- Show all created containers

  - docker ps --all

- Retrieve output logs

  - docker logs [container id]

- Execute an additional command in a container

  - docker exec -it [container id] [command]
    - -it
      - Allow us to provide input to the container

- Get shell access in a container

  - docker [run/exec] -it [container id] sh

- Build Dockerfile

  - In project directory:
    - docker build .
  - With a tag (name)
  - docker build -t [dockerId/package:version] .
    - docker build -t lyx0/redis:latest .

- Manual image creation:
  baseImage can be alpine for example

  - docker run -it [baseImage] sh
    - [do whatever in it]
  - in new shell:
    - docker commit -c 'CMD ["redis-server"]' [containerId]

- Add port mapping
  - first port is our own, second port is the containers port
    - docker run -p [port] : [port] [containerId]
    - docker run -p 8080:8080 lyx0/simpleweb

## Flags

- -a

  - attach (shows output)

- -c

  - commit changes

- -i

  - attach to STDIN

- p
  - Add port mapping
  - first port is our own, second port is the containers port
  - docker run -p [port]:[port] [containerId]
- -t

  - makes sure all the text is nicely formatted and like normal

- -it
  - enables you to input text
  - interactive
