# mngmnt_stack

My mngmnt docker stack implementation
---

### management automation and monitoring
- https://github.com/kikearciniegas/mngmnt_stack

The definition includes a docker-compose file for a quick and easy configuration, deployment and maintenance. The stack is security and privacy centric, some configurations are bound for this. I tried to comment as much of the code as possible, also "borrowed" some great lines of code and structures from the internet elders, other contributors and the good people of [reddit](https://reddit.com), kudos to them all.

My definition for the container includes these files:
- [x] docker-compose.yaml - with the specifics for the respective service
- [x] .env - with all required parameters and values
- [x] docker_run.txt - with the `docker run` command string for the CLI - inside the docker folder for each tool

Initially, my setup runs on a Synology NAS, with different volumes for docker containers and configuration/data (bind mounts for persistent data) files.

It is important to create the corresponding folder for the containers' configuration/data before running the `docker-compose -p [stack_name] up -d` command.

For any deep-end changes run the `docker-compose -p [stack_name] up -d --force-recreate` command.

Also, for my "mngmnt" stack, I run it in the default bridge network, in case you are wondering.

<details>
  <summary>Folder/directory structure for the containers configuration/data files</summary>

```
- volume1
    - docker
        - autoheal
            - data
        - dozzle
            - data
        - healthchecks
            - data
        - heimdall
            - data
        - portainer
            - data
        - .
        - .
        - .

ie. /volume1/docker/healthchecks/data/...
```
</details>

### references
- https://www.reddit.com/
- https://github.com/petersem/DockerStack