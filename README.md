# verifiable
Setup a Verifiable Node in Ubuntu 16.04 (later versions should work fine)
Download the genesis & static json files to your directory where you want your blockchain data.  For example you are user "sysadmin".
Login to Linux in your home directory /home/sysadmin
```
mkdir verifiable
cd verifiable
```
Download the two boot files to your directory
```
wget https://raw.githubusercontent.com/hashratez/verifiable/master/genesis.json
```
```
wget https://raw.githubusercontent.com/hashratez/verifiable/master/static-nodes.json
```
return to your home directory
```
cd ..
```
Install Ethereum
```
sudo apt-get install software-properties-common -y
sudo add-apt-repository -y ppa:ethereum/ethereum
sudo apt-get update
sudo apt-get install ethereum -y
```
Now we set the genesis block
```
geth init /home/sysadmin/verifiable/genesis.json
```
Now were are going to tell Ethereum where to find it's peers to join the blockchain.  Geth will run and stall--after it stalls CTL+C to exit Geth. 
```
geth --datadir "/home/sysadmin/verifiable"
```
```
CTL+C
```
Now let's start the blockchain (replace "Verifiable-Node1-FRA" with the name of your node):
```
geth --networkid 212121 --port 30211 --ethstats Verifiable-Node1-FRA:cbtestnet@82.223.12.96:3000 --rpc --rpcapi "admin,db,eth,net,personal,web3"
```



You will now have a hidden directory in your home folder .ethereum

/home/sysadmin/.ethereum

/home/sysadmin/.ethereum/geth

now we need to reset the peers by moving the nodes file
```
cd verifiable
cp static-nodes.json /home/sysadmin/.ethereum/geth/static-nodes.json
```
now we reset the directory
```
cp static-nodes.json /root/.ethereum/geth/static-nodes.json



