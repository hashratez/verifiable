# verifiable
Setup a Verifiable Node
Download the genesis & static json files to your directory where you want your blockchain data
For example:
```
https://github.com/hashratez/verifiable/blob/master/genesis.json
```

Typical Windows Geth command to initialize the blockchain
```
C:\Program Files\Geth>geth init C:\Users\name\AppData\Roaming\Ethereum\genesis.json
```
For Linux
```
geth init $~/genesis.json
```
Might look like this:
```
geth init /home/sysadmin/verifiable/genesis.json
