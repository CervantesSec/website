# Kestrel

Kestrel is a cross-platform web server for ASP.NET Core. Kestrel is the web server that's included by default in ASP.NET Core project templates.

This JSON configuration is related to the Kestrel web server settings in an ASP.NET Core application. Here's a brief explanation of each part:

```json
  "Kestrel": {
    "Endpoints": {
      "Http": {
        "Url":  "http://0.0.0.0:8080"
      },
      "Https": {
        "Url": "https://0.0.0.0:8081"
      }
    },
    "EndpointDefaults": {
      "Url": "https://0.0.0.0:8081",
      "Protocols": "Http1"
    }
  }
```

- `Kestrel`: This is the built-in web server in ASP.NET Core. It's cross-platform, supports HTTP/2, and can be configured to use HTTPS.

- `Endpoints`: This section defines the endpoints that Kestrel listens to. In this case, there are two endpoints defined: `Http` and `Https`.

    - `Http`: This endpoint is configured to listen on all network interfaces (`0.0.0.0`) on port `8080` using the HTTP protocol.

    - `Https`: This endpoint is configured to listen on all network interfaces (`0.0.0.0`) on port `8081` using the HTTPS protocol.



- __Note:__ The Docker is configured by default to use these ports 8080 and 8081. If you change the ports in the `appsettings.json` file, you need to rebuild the Docker image.



- `EndpointDefaults`: This section defines the default settings for the endpoints. If an endpoint doesn't have a specific setting, it will use the default.

    - `Url`: The default URL that Kestrel will listen to if no specific URL is provided for an endpoint. In this case, it's `https://0.0.0.0:8081`.

    - `Protocols`: The default protocol that Kestrel will use if no specific protocol is provided for an endpoint. In this case, it's `Http1`.

This configuration allows the application to listen for both HTTP and HTTPS requests on different ports, with a default of using HTTPS on port 8081 if no specific configuration is provided for an endpoint.