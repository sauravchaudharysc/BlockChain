We will implement a digital bank using Ethereum Blockchain. Ethereum is an open-source, public, blockchain-based distributed computing platform. The systems will allow us to:

1. Make a cryptocurrency with a fixed market supply and tokens to represent real world asset values.
2. Create an autonomous private Blockchain with rules on spending money.
3. Mine for a new Ether by validating transactions.

**Step 1 :** Cloning Geth Code:

geth is the command line interface for running a full ethereum node implemented in Go.

```bash
Cloning the geth repository from github.
$ git clone https://github.com/ethereum/go-ethereum
```

![image-20210215161357186](img/image-20210215161357186.png)

**Step 2: ** Move to go-ethereum directory

```bash
$ cd go-ethereum
```

![image-20210215161424942](img/image-20210215161424942.png)

**Step 3:** Branch the latest version of geth.

```bash
$ git checkout tags/v1.9.25 -b EdurekaEthereumV1.9.25
```

![image-20210215161518717](img/image-20210215161518717.png)

**Step 4:** Install go Language on system. Download it from internet. Extract the zip folder

```bash
sudo tar -xvf go1.15.8.linux-amd64.tar.gz
```

![WhatsApp Image 2021-02-15 at 4.39.24 PM (1)](img/WhatsApp Image 2021-02-15 at 4.39.24 PM (1).jpeg)

**Step 5:** Move the go folder to usr/local/

```bash
mv go usr/local
```

![WhatsApp Image 2021-02-15 at 4.39.24 PM](img/WhatsApp Image 2021-02-15 at 4.39.24 PM.jpeg)

**Step 6: **Adjust the path in .bashrc

```bash
sudo gedit .bashrc
```

![WhatsApp Image 2021-02-15 at 4.39.24 PM (2)](img/WhatsApp Image 2021-02-15 at 4.39.24 PM (2).jpeg)

**Step 7:**Run this command

```bash
$ make all
```

![Screenshot from 2021-02-15 08-03-53](img/Screenshot from 2021-02-15 08-03-53.png)

**Step 8:**Creating Genesis Block
A genesis block is the first block of a block chain.
To create the genesis file, execute the following commands:

```bash
$ cd go-ethereum
$ mkdir genesis
$ cd genesis
```

**Step 9:** Step 5. Creating genesis.json in genesis folder

```bash
$ gedit genesis.json
```

This is like making Rules for our Blockchain
The rules for our Blockchain will be included in the genesis.json file we have created. Add the following code in your genesis.json file:![Screenshot from 2021-02-15 10-41-38](img/Screenshot from 2021-02-15 10-41-38.png)

**Step 10:** Now we need to initialize the blockchain.

```bash
$ /home/saurav/go-ethereum/build/bin/geth --datadir ~/ethereum/net3 init genesis/genesis3.json
```

**Step 11:** Run the geth console. 

```bash
$ /home/saurav/go-ethereum/build/bin/geth --datadir ~/ethereum/net3/ --networkid 3 console
```

**Step 12:** Creating Accounts

**personal.newAccount()** : it creates a new account as part of your blockchain which has a specific wallet attached to it.

![Screenshot from 2021-02-15 10-53-10](img/Screenshot from 2021-02-15 10-53-10.png)

**Step 13:** Checking the various accounts which are part of my blockchain.

**eth.accounts:** It helps you check the various accounts which are part of your blockchain.

![Screenshot from 2021-02-15 10-54-22](img/Screenshot from 2021-02-15 10-54-22.png)

**Step 14:** 

**eth.blockNumber():** this helps you to identify the number of blocks that are part of your blockchain.

![Screenshot from 2021-02-15 10-54-22](img/Screenshot from 2021-02-15 10-54-22.png)

**Step 15:** miner.start(): this function is used to start the mining process.

![Screenshot from 2021-02-15 12-04-13](img/Screenshot from 2021-02-15 12-04-13.png)

**Step 16:** miner.stop() Stop the mining operation.

![miner.stop() - Blockchain Tutorial -Edureka](https://d1jnx9ba8s6j9r.cloudfront.net/blog/wp-content/uploads/2017/08/miner.stop_.jpg)

**eth.blockNumber():** executing this command after the mining process tells you at which block number you are at after performing the mining operation
**eth.getBalance:** (“account number”): this command is used to check the ether balance in the specified account