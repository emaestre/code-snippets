# Docker Cheatsheet

## List all networks a container belongs to

``` bash
docker inspect -f '{{range $key, $value := .NetworkSettings.Networks}}{{$key}} {{end}}' [container]
```

## List all containers belonging to a network by name

``` bash
docker network inspect -f '{{range .Containers}}{{.Name}} {{end}}' [network]
```

## Attach a running container to a network

``` bash
docker network connect [network] [container]
```

## With containerA already running, test if containerA can connect to containerB by using its name

``` bash
docker exec [containerA] ping [containerB] -c2
```

## Create a network

``` bash
docker network create [network]
```

## List networks

``` bash
docker network ls
```

## Get IP Address

``` bash
docker inspect <container_id> | grep IPAddress
```

## Inspect network

``` bash
docker inspect bridge
```
