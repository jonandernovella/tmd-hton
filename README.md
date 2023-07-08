# GraphQL federation demo

## Start the services

```command
docker compose -f deployment/docker-compose.yml up -d
./start
```

## Stop the services

```command
docker compose down --volumes
```

## Service endpoints

- [Node 1](http://localhost:8080)
- [Node 2](http://localhost:8081)
- [Gateway node](http://localhost:8082)
- [Dashboard](http://localhost:4567)
