# Tools - Permissioning DApp

To launch the dApp for viewing and adding nodes and addresses to the network, run

## Prerequisites

For the development server to run the dapp:

- NodeJS v10.16.0 or later
- Yarn v1.15 or later
- Browser with MetaMask installed.

## Notes

- This guide is for installation in a Besu node. For installation in another server, change IP in BESU_NODE_PERM_ENDPOINT param ("localhost") with the IP of a node you can access
- Use Metamask to "login" the DApp with an admin address in order to make changes

```sh
$ cd alastria-node-besu/besu-node
$ git clone https://github.com/PegaSysEng/permissioning-smart-contracts.git
$ cd permissioning-smart-contracts
$ yarn install
$ docker container run -v `pwd`:`pwd` -w `pwd` -it --rm -e "ACCOUNT_INGRESS_CONTRACT_ADDRESS=0x0000000000000000000000000000000000008888" -e "NODE_INGRESS_CONTRACT_ADDRESS=0x0000000000000000000000000000000000009999" -e "BESU_NODE_PERM_ENDPOINT=http://localhost:8545" -e "NETWORK_ID=2020" -p 3000:3000 node:12 yarn start
```
