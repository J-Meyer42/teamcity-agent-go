[![jmeyer42/teamcity-agent-go](https://img.shields.io/docker/pulls/jmeyer42/teamcity-agent-go.svg)](https://hub.docker.com/r/jmeyer42/teamcity-agent-go/)

# teamcity-agent-go
Teamcity Docker Build Agent for Golang. Based on the [teamcity-minimal-agent](https://hub.docker.com/r/jetbrains/teamcity-minimal-agent/) image from Jetbrains.

## Run with `docker run`
```
docker run -d --name="container_name" -e AGENT_NAME="agent_name" -e SERVER_URL="https://your.teamcity.com" jmeyer42/teamcity-agent-go:latest
```

## Run with docker-compose
Within your `docker-compose.yml` file create a new service:
```docker
 teamcity-agent1:
    container_name: teamcity-agent1
    image: jmeyer42/teamcity-agent-go:latest
    expose:
      - 9090     
    environment:
      - SERVER_URL=https://your.teamcity.com
      - AGENT_NAME=agent_name
    restart: always
```
