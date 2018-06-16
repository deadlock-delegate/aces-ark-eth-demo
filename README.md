# ACES: ARK ~ ETH

An example how easy it is to setup ACES ETH to ARK Channel Service using Docker.

## Requirements

In order to run ARK ~ ETH service you'll need to have access to a trusted DARK node (ARK node
running on devnet) and an ETH node (running on any ETH testnet).

## How to run

1. Change the settings under `environment` in `docker-compose.yml`
2. Start project by running `docker-compose up`

It might take a while for the project to start the first time.


## Useful curl commands

Subscribe `ark-eth-channel` to events on `listener-ark`

```
curl -X POST 'localhost:9091/subscriptions' \
-H 'Content-type: application/json' \
-d '{
  "callbackUrl": "http://localhost:9190/public/eventLogger",
  "minConfirmations": 5
}'
```

Create an ACES contract for sending ETH (tesnet) to someone using DARK tokens.

```
curl -X POST localhost:9190/contracts \
-H 'Content-type: application/json' \
-d '{
 "arguments": {
   "recipientEthAddress": "<recipients-eth-address>"
 }
}'
```

Check status of the contract:

```
 curl -X GET http://localhost:9190/contracts/<contract-id>
 ```

## Useful links related to this project:

- [ACES ARK Ethereum Channel Service](https://github.com/ark-aces/aces-ark-ethereum-channel-service)
- [ACES Listener ARK](https://github.com/ark-aces/aces-listener-ark)
- [ACES Listener Docs](https://ark-aces.github.io/aces-listener-docs/)
- [ACES Medium Blog](https://medium.com/@arkaces)

## Have questions or would like to learn more?

Join #aces channel on [ARK's Slack](https://ark.io/slack)
