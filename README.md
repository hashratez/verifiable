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
Install Ethereum
```
sudo apt-get install software-properties-common -y
sudo add-apt-repository -y ppa:ethereum/ethereum
sudo apt-get update
sudo apt-get install ethereum -y
```
Now we set the genesis block & set it
```
geth init /home/sysadmin/verifiable/genesis.json

geth --datadir "/home/sysadmin/verifiable"
```
```
CTL+C
```
Now let's start the blockchain (replace "Verifiable-Node1-FRA" with the name of your node):

Now were are going copy the static-nodes.json file to the newly created directory .ethereum (created automatically by the processes above) to tell Ethereum where to find it's peers to join the blockchain. 
```
cp /home/sysadmin/verifiable/static-nodes.json /home/sysadmin/.ethereum/geth/static-nodes.json
```
Now we start the blockchain! Make sure to replace NAME-OF-YOUR-NODE with your text, it should be short but descriptive with a location/region: TechCo-NewYork (no spaces and no crazy special characters).  IT MAKE TAKE A MINUTE or two for the chain to fire up--just wait.   
```
geth --networkid 212121 --port 30211 --ethstats NAME-OF-YOUR-NODE:cbtestnet@82.223.12.96:3000 --rpc --rpcapi "admin,db,eth,net,personal,web3"
```
Remember that if you kill the console the blockchain will stop so you can start with nohup or setup as Linux service.
```
nohup COMMAND-STRING &
```



