# go-perception
## ipfs agent

* ipfs api default listen on tcp 5001 
    
* ipfs gateway default listen on tcp 8080 

* agent-server/agent-client on different computers and can be used in different networks.


### agent-server 
1. start ipfs :

    `ipfs daemon`

2. start perception as agent-server for ipfs api and gateway:

    `./perception -s "ipfsapi:5001,ipfsgateway:8080"`

### agent-client 

* start perception as agent-client for ipfs api and gateway:
    
    `./perception -c "ipfsapi:45001,ipfsgateway:48080"`

* ipfs api example:
  
    `curl http://localhost:45001/api/v0/swarm/peers`

* ipfs gateway example: 
    
    `curl http://localhost:48080/ipns/QmRWuyGyWT56oLxXPCmmbCvZFYnnU5P8uQgKxx4qhMoQ67`

## API

### getastab

__Get agent-server table by peer, used to check if agent-server has been found.__

* request:

```
http://localhost:40080/api/?body={"sn":"sn-101","service":"funcs","method":"getastab"}
```

* response:

```
{
  "sn": "sn-101",
  "success": true,
  "entity": {
    "/agent/ipfsapi": [
      "Qmduz9PhkP53UiTYUuNgp6JbWj69DWdbT9vWmw3BoH2sw3"
    ],
    "/agent/ipfsgateway": [
      "Qmduz9PhkP53UiTYUuNgp6JbWj69DWdbT9vWmw3BoH2sw3"
    ],
    "/agent/web3rpc": [
      "Qmduz9PhkP53UiTYUuNgp6JbWj69DWdbT9vWmw3BoH2sw3"
    ],
    "/agent/web3ws": [
      "Qmduz9PhkP53UiTYUuNgp6JbWj69DWdbT9vWmw3BoH2sw3"
    ]
  }
}
```
  
