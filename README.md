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
