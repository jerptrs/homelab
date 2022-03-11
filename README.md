docker-compose files are build the following order:

```yml
servies:
    app:
        container_name: <container name>
        image: <image>
        restart: <restart options, default should be unless-stopped>
        ports:
            - <port configuration>/<protocol TCP|UDP>
        environment:
            - <environment configuration>
        volumes:
            - <volume configuration> (preffered /var/<app>)
        networks:
            - <network configration>
        labels:
            - "traefik.http.routers.$ROUTE_NAME.rule=Host(`$DOMAIN`)"
```
