# k3pi
Utility to automate terraforming a fully out-of-the-box k3s cluster using Raspberry Pi as nodes.



## Goal
### Base Cluster Setup
- Setup a k3s cluster using 3 raspberry pi boards, with 1 control-plane node and 2 worker nodes
- Setup metal-lb as service-lb
- Setup longhorn as storage-provider

### Setup Method
- Automate the entire setup



## Requirements
- 3x Raspberry Pi 4 boards with 2GB of memory, 4 CPU cores
- 3x SD Cards with 16GB
- 3x Power supply 5V/3A with USB type-c connector
- 3x Ethernet patch cord CAT5-e
- 1x Internet Modem or Switch with at least 3x 10/100 Mbps ports available and at least 1 uplink port



## Usemode
``` shell
### Create cluster
git clone github.com/aleroxac/k3pi && cd k3pi
make init
make apply

### Cleanup
make destroy
```
