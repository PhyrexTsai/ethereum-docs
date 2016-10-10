# ethereum nccu

## Connect to nccu private blockchain

On Mac OS

### Step 0 : Clean up environment 

Remove two folders. 

```
rm -rf ~/Library/Ethereum
rm -rf ~/.ethash
```

### Step 1 : Install Ethereum

Run

```
brew tap ethereum/ethereum
brew install ethereum
```

### Step 2 : Run genesis block

Download [genesis.json](genesis.json) or copy

```
{
   "difficulty": "0x0",
   "extraData": "0x16888",
   "gasLimit": "0x999999999",
   "mixhash": "0x000000000000123123123123123168647572616c65787365646c6578",
   "nonce": "0x0",
   "timestamp": "0x0"
}
```

Run

```
geth init genesis.json
```

### Step 3 : Create Ethereum wallet

Create new account

```
geth account new
```

### Step 4 : Download Ethereum wallet

[https://github.com/ethereum/mist/releases/](https://github.com/ethereum/mist/releases/)

### Step 5 : Setup static node

Download [static-nodes.json](static-nodes.json) or copy

```
[
"enode://17f920427798fe9a609b2e4f61c73198393157ed73e5ea1c19290675801f0ff7f3df020b22edc7c999b4356149a4ca9e32f3e4d3d7534d01beda11dbff0c85ce@140.119.164.155:30303"
]
```

Copy to `~/Library/Ethereum/`

```
mv /path/to/ ~/Library/Ethereum/
```  

Then run 

```
geth --networkid 16888 --port 30303 --nodiscover --maxpeers 25 --nat "any" --rpc --rpccorsdomain "*" --rpcapi "eth,net,web3,debug" --mine --minerthreads 2 --autodag
```

### geth 

list accounts

```
geth account list
```

### Command Line

Using command line

```
geth attach
```

miner control

```
miner.start(8)
miner.stop()
```

account balance

```
web3.fromWei(eth.getBalance(eth.coinbase), "ether")
```

### Build via Ethereum Wallet

#### Deploy

`CONTRACTS` > `DEPLOY NEW CONTRACT` 

Write contract code on `SOLIDITY CONTRACT SOURCE CODE`  
Then choose `DEPLOY`

#### Watch

`CONTRACTS` > `WATCH CONTRACT`

`Select function` via `WRITE TO CONTRACT`

### Contract example

#### Hello

#### Grades Contract

