# SSL HTTPS Configuration for Cervantes

## Docker

The Docker Compose configuration for the `cervantes-app` service includes several environment variables related to SSL and HTTPS. Here's a brief explanation of each part:

```yaml
 cervantes-app:
        container_name: cervantes-app
        networks:
            - cervantes
        image: mesq/cervantes:1.0-dev
        depends_on: 
            - cervantes-db
        restart: unless-stopped
        ports:
            - "80:8080"
            - "443:8081"
        environment:
            - ASPNETCORE_ENVIRONMENT=Production
            - ASPNETCORE_URLS=https://+:443;http://+:80
            - ASPNETCORE_HTTPS_PORT=443
            - ASPNETCORE_Kestrel__Certificates__Default__Password=CervantesCert 
            - ASPNETCORE_Kestrel__Certificates__Default__Path=/https/cervantes.pfx
        volumes:
            - ./appsettings.json:/app/appsettings.json
            - ./https:/https:ro
```

- `"443:8081"`: This is a port mapping configuration. It maps port 443 on the host machine to port 8081 inside the Docker container. Port 443 is the standard port for HTTPS traffic.

- `ASPNETCORE_URLS=https://+:443;http://+:80`: This environment variable sets the URLs the app listens on. `https://+:443` configures the app to listen for HTTPS traffic on port 443. `http://+:80` configures the app to listen for HTTP traffic on port 80.

- `ASPNETCORE_HTTPS_PORT=443`: This environment variable sets the HTTPS port to 443.

- `ASPNETCORE_Kestrel__Certificates__Default__Password=CervantesCert`: This environment variable sets the password for the default certificate used by Kestrel, the web server used by ASP.NET Core applications.

- `ASPNETCORE_Kestrel__Certificates__Default__Path=/https/cervantes.pfx`: This environment variable sets the path to the default certificate used by Kestrel. The path is inside the Docker container.

- `./https:/https:ro`: This is a volume mapping configuration. It maps the `https` directory from the host machine to the `/https` directory inside the Docker container. The `ro` option makes the volume read-only inside the container. This directory contains the SSL certificate file `cervantes.pfx`.

If you want to use your own SSL certificate, you can replace the `cervantes.pfx` file in the `https` directory with your own certificate file. You can also change the password for the certificate by changing the value of the `ASPNETCORE_Kestrel__Certificates__Default__Password` environment variable.