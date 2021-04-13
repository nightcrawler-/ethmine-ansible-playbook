# Etherium Mining: Ansible Playbook

The configuration files in this repository will enable you quickly provision a VM to mine etherium.

## Prerequisites - Ubuntu 18.04 LTS
1. An Etherium wallet (The address)
2. A mining pool, available at https://ethermine.org/start. It does not require registration, and will deposit as little as 0.01 ETH ($18 ca. Feb, 2021).
3. A remote VM instance with python installed, and required ssh settings configured.

# What will be setup: 

1. ethminer, available from GitHub (https://github.com/ethereum-mining/ethminer). 
2. Initialize mining - provide pool endpoint and wallet address

##  Ansible

### Test instance access
Setup the VM ip addresses in the inventory file, to ping:
`ansible -i ansible/inventory -m ping rails`

###

#### Important notes/links

Download ethminer (source): https://github.com/ethereum-mining/ethminer/archive/refs/tags/v0.19.0.tar.gz
Linux Distro: https://github.com/ethereum-mining/ethminer/releases/download/v0.19.0-alpha.0/ethminer-0.19.0-alpha.0-cuda-9-linux-x86_64.tar.gz
Unpack ethminer (All this can be inferred from the included playbook, eth.yml)

#### Extra
./ethminer -P stratums://0x9e27D5996f7417581886CbA9dd6C70643C8d7742@eu1.ethermine.org:5555






