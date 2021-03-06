# Go API Server for openapi

A hello world service.

## Overview

This server was generated by the [openapi-generator](https://openapi-generator.tech) project.

By using the [OpenAPI-Spec](https://github.com/OAI/OpenAPI-Specification) from a remote server, you can easily generate a server stub.

To see how to make this your own, look here:

[README](https://openapi-generator.tech)

- API version: 1.0
- Build date: 2022-05-25T19:03:07.072094+10:00[Australia/Sydney]

```bash
export GO_POST_PROCESS_FILE="/usr/local/bin/gofmt -w"
openapi-generator generate -i openapi3.yaml -g go-gin-server
```

### Running the server

To run the server, follow these simple steps:

```bash
go run main.go
```

To run the server in a docker container

```bash
docker build --network=host -t openapi-gin .
```

Once the image is built, just run

```bash
docker run --rm -p 8080:8080 -it openapi-gin
```

### Known Issue

Endpoints sharing a common path may result in issues. For example, `/v2/pet/findByTags` and `/v2/pet/:petId` will result in an issue with the Gin framework. For more information about this known limitation, please refer to [gin-gonic/gin#388](https://github.com/gin-gonic/gin/issues/388) for more information.

A workaround is to manually update the path and handler. Please refer to [gin-gonic/gin/issues/205#issuecomment-296155497](https://github.com/gin-gonic/gin/issues/205#issuecomment-296155497) for more information.
