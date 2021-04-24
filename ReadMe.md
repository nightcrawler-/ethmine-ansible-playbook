# Etherium Mining: Ansible Playbook

The configuration files in this repository will enable you quickly provision a VM to mine etherium.

## Prerequisites - Ubuntu 18.04 LTS
1. An Etherium wallet (The address)
2. A mining pool, available at https://ethermine.org/start. It does not require registration, and will deposit as little as 0.01 ETH ($18 ca. Feb, 2021).
3. A remote VM instance with python installed, and required ssh settings configured. `sudo apt-get install python`

# What will be setup: 

1. ethminer, available from GitHub (https://github.com/ethereum-mining/ethminer). 
2. Initialize mining - provide pool endpoint and wallet address

##  Ansible

### Test instance access
Setup the VM ip addresses in the inventory file, to ping:
`ansible -i ansible/inventory -m ping rails`

##  Note:

Before starting mining, you will need to install compatible CUDA and NVIDIA drivers for your platform. (GPU Drivers)
https://cloud.google.com/compute/docs/gpus/install-drivers-gpu#ubuntu-driver-steps

### To run:
Inside the ansible dir:
`ansible-playbook -i inventory eth.yml`

###

#### Important notes/links

Download ethminer (source): https://github.com/ethereum-mining/ethminer/archive/refs/tags/v0.19.0.tar.gz
Linux Distro: https://github.com/ethereum-mining/ethminer/releases/download/v0.19.0-alpha.0/ethminer-0.19.0-alpha.0-cuda-9-linux-x86_64.tar.gz
Unpack ethminer (All this can be inferred from the included playbook, eth.yml)

#### Extra - mining command, with etherium address you wanna use. This should be mine, from blockchain.com
./ethminer -P stratums://0x9e27D5996f7417581886CbA9dd6C70643C8d7742@eu1.ethermine.org:5555

# In this directory

## ethermine.yml

Provisions an Ubuntu 18.04 LTS VM, that has a GPU, with all the necessary drivers, mining software, and starts mining right away.

## geth.yml

Provisions an Ubuntu 18.04 LTS VM, with the go-etherium and etherium software, I deal to sync the net and establish a node from which `Clef` or other tools can be used. Will allow you to process transactions on the network.








