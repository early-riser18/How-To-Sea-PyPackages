## Documentation

### Overview
This folder exposes various objects to allow our internal services to communicate with our authentication service.

### Server
The `Server` class is responsible for handling incoming gRPC requests and providing authentication services. To use the `Server` class:
1. Subclass `ServerABC` and implement `ValidateToken` with the service validation logic.
2. Start the server to listen for incoming requests.

### Client
The `Client` class is used to communicate with the `Server` and perform authentication operations. To use the `Client` class:
1. Initialize the client with the server's address and port.
2. Use the client's methods to send authentication requests to the server.

# Update the gRPC service definitions
More info at https://grpc.io/docs/languages/python/basics/

To build new bindings, you will need the following 
```
grpcio~=1.66
grpcio-tools~=1.66
```

1. Update the `.proto` file
2. Run the following command to generate the Python bindings
## Python implementation

Generate the python bindings with
```bash
python -m grpc_tools.protoc -I./proto --python_out=./proto --pyi_out=./proto --grpc_python_out=./proto ./proto/<filename>.proto
```