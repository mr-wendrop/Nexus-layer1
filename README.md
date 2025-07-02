# Nexus Testnet 3 Prover Guide

- You can run multiple node to accumulate NEX points within a single nexus account.
- In this guide, I will show you how to earn NEX points through the CLI on a VPS.


## VPS Purchase

- You can buy from [Contabo](https://contabo.com/en/vps/) or [Hostbrr](https://my.hostbrr.com/). However, if you prefer to pay with cryptocurrency, consider using Hostbrr.


## Create/Login Nexus Account And Get Node ID

- Navigate to nexus: https://app.nexus.xyz/
- Go to your profile and link your social accounts.
- Go to https://app.nexus.xyz/nodes to get your node ID
- Now click `Add Node`, then click `Add CLI` and copy your node ID
- Save it, we will use it when executing node.


## Execute Prover Node

- Ensure that you have purchased a VPS with at least 8GB of RAM.

### Install Dependecies
```javascript
sudo apt update & sudo apt upgrade -y
```
```javascript
sudo apt install curl iptables build-essential git wget lz4 jq make gcc nano automake autoconf tmux htop nvme-cli pkg-config libssl-dev libleveldb-dev tar clang bsdmainutils ncdu unzip libleveldb-dev  -y
```
```javascript
sudo apt install -y protobuf-compiler
```
```javascript
curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh
```
> [!NOTE]
> After that, press enter to proceed with the default installation (1)
```javascript
source $HOME/.cargo/env
```
```javascript
export PATH="$HOME/.cargo/bin:$PATH"
```
```javascript
rustup target add riscv32i-unknown-none-elf
```

### Creating Screen 
1. Install screen
```javascript
sudo apt install screen
```
2. Create screen and run node on the background
```javascript
screen -S Nexus
```

### Start Node
1. Nexus command
```javascript
curl https://cli.nexus.xyz/ | sh
```
2. Run with an existing node ID
```javascript
source ~/.bashrc

nexus-network start --node-id your-node-id
```
- Replace `your-node-id` with the node_id from nexus dashboard that we copied previously.

#
### Important Notes
- Use CTRL A+D to detach from screen
- Use screen -r + screen name to visit the screen again.

#
### Drop Your Issues
- X https://x.com/Mr_wendrop
- Telegram https://t.me/Mr_wendrop
