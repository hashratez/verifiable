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
wget https://github.com/hashratez/verifiable/blob/master/genesis.json
```
```
wget https://github.com/hashratez/verifiable/blob/master/static-nodes.json
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


geth init $~/genesis.json
```
Might look like this:
```
geth init /home/sysadmin/verifiable/genesis.json
