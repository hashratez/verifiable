# verifiable
Setup a Verifiable Node
Download the genesis & static json files to your directory where you want your blockchain data.  For example you are user "sysadmin".
Login to Linux in your home directory /home/sysadmin
```
mkdir verifiable
cd verifiable
```
For example:
```
wget https://github.com/hashratez/verifiable/blob/master/genesis.json
```
```
wget https://github.com/hashratez/verifiable/blob/master/static-nodes.json
```


geth init $~/genesis.json
```
Might look like this:
```
geth init /home/sysadmin/verifiable/genesis.json
