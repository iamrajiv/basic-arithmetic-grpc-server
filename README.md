<div align="center">
<img src="assets/basic-arithmetic-grpc-server.svg" height="auto" width="400" />
<br />
<h1>Basic Arithmetic gRPC Server</h1>
<p>
Simple Basic Arithmetic gRPC Server which uses gRPC-Gateway
</p>
<a href="https://github.com/iamrajiv/basic-arithmetic-grpc-server/network/members"><img src="https://img.shields.io/github/forks/iamrajiv/basic-arithmetic-grpc-server?color=0969da&style=for-the-badge" height="auto" width="auto" /></a>
<a href="https://github.com/iamrajiv/basic-arithmetic-grpc-server/stargazers"><img src="https://img.shields.io/github/stars/iamrajiv/basic-arithmetic-grpc-server?color=0969da&style=for-the-badge" height="auto" width="auto" /></a>
<a href="https://github.com/iamrajiv/basic-arithmetic-grpc-server/blob/master/LICENSE"><img src="https://img.shields.io/github/license/iamrajiv/basic-arithmetic-grpc-server?color=0969da&style=for-the-badge" height="auto" width="auto" /></a>
</div>

## About Project

A Basic Arithmetic gRPC server that uses gRPC-Gateway and reads protobuf service definitions and generates a reverse-proxy server. It performs four basic operations Addition, Division, Multiplication, and Subtraction between two given integers.

To get more references about gRPC-Gateway check out [Hello World gRPC-Gateway](https://github.com/iamrajiv/helloworld-grpc-gateway).

It is a simple hello world program that uses gRPC-Gateway. This project was created when I participated in Google Season of Docs 2020 with [gRPC-Gateway](https://github.com/grpc-ecosystem/grpc-gateway). The reason for making this project is to make people familiarize themselves with gRPC-Gateway.

I have added all the tutorials related to Hello World gRPC-Gateway to the [gRPC-Gateway documentation website](https://grpc-ecosystem.github.io/grpc-gateway/docs/tutorials/).

#### Folder structure:

```shell
.
├── Dockerfile
├── LICENSE
├── Makefile
├── README.md
├── assets
│   └── basic-arithmetic-grpc-server.svg
├── buf.gen.yaml
├── buf.yaml
├── go.mod
├── go.sum
├── main.go
└── proto
    ├── arithmetic
    │   ├── arithmetic.pb.go
    │   ├── arithmetic.pb.gw.go
    │   ├── arithmetic.proto
    │   └── arithmetic_grpc.pb.go
    └── google
        └── api
            ├── annotations.proto
            └── http.proto
```

## Usage

Before running this project install all the required Go packages by running the command `make install`. Also, we can generate the stubs using the command `make generate` and delete the stubs using the command `make clean`.

Start the server using the command:

```shell
go run main.go
```

Then use cURL to send HTTP requests:

```shell
curl -k  -X POST "http://localhost:8090/v1/arithmetic/add" -H  "accept: application/json" -H  "Content-Type: application/json" -d "{  \"a\": \"15\",  \"b\": \"17\"}"
```

```shell
{"result":"32"}
```

## License

[MIT](https://github.com/iamrajiv/basic-arithmetic-grpc-server/blob/master/LICENSE)
