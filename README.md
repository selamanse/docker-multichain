# docker-multichain

A multichain docker image based on this guide: https://www.multichain.com/download-install/

## the why
This image is a result of different multichain evaluations and is currently not designed to be used in production.

## the how

run a multichain instance (creates a chain named chain1):

`docker run -d --name multichain selamanse/multichain`

get access to the [api](https://www.multichain.com/developers/json-rpc-api/) with multichain-cli
`docker exec -it multichain multichain-cli -rpcpassword=multichain chain1`

run it with exposed rpc port (default 8570):

`docker run -p "8570:8570" selamanse/multichain`

A basic example on how to use the api remotely with curl:

`curl -u multichainrpc:multichain yourdockerhost:8570 -d '{"method":"getinfo","params":[],"id":1,"chain_name":"chain1"}'`

## reference

- [download and install multichain](https://www.multichain.com/download-install/)
- [configure multichain](https://www.multichain.com/developers/blockchain-parameters/)
- [multichain api](https://www.multichain.com/developers/json-rpc-api/)
