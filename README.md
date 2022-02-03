# blockchain-homework

This assignment creats a Proof-of-Authority (PoA) blockchain with 2 nodes, that can complete and send transactions to each other. 

In order to run the blockchain: 

  A terminal style interface is required (GIT Bash for Windows, Terminal on MacOS, etc)
  The Go-Ethereum (Geth) & Tools available from https://geth.ethereum.org/downloads/ 
  MyCrypto or other Ethereum wallet application, capable of accessing wallets and sending 
      transactions over an Ethereum-protocol blockchain. 
      
Network Configuration:

Name of blockchain = fintechnet /n
Consensus = Clique - proof-of-authority 
Block seconds = 15
Prefund accounts? = yes 
Chain/Network id = 5151
  
Geth commands to start blockchain:

  ./bootnode -nodekey boot.key -verbosity 9 -addr :30310     // Address can be whatever port you'd like 
  
Geth commands to begin Nodes:

Node 1: 

  ./geth --datadir node1/ --syncmode "full" --port 30311 --rpc --rpcaddr "localhost" --rpcport 8545 --rpcapi "personal,db,eth,net,web3,txpool,miner" --bootnodes "enode://2c4b863969f1f70559acd87a87a289d3b94a3be3acacb06418e0a8d434e58b5f65cca7e047d89a5c65572211f6a7a1ea5d0e111c46e98c05b53c05676499b7aa@127.0.0.1:30310" --networkid 5151 --unlock "0x07965e52eB7EBB3f9485b618625b03c3c1047Dac" --password node1/password.txt --allow-insecure-unlock --mine
  
Node 2:

  ./geth --datadir node2/ --syncmode "full" --port 30312 --rpc --rpcaddr "localhost" --rpcport 8546 --rpcapi "personal,db,eth,net,web3,txpool,miner" --bootnodes "enode://2c4b863969f1f70559acd87a87a289d3b94a3be3acacb06418e0a8d434e58b5f65cca7e047d89a5c65572211f6a7a1ea5d0e111c46e98c05b53c05676499b7aa@127.0.0.1:30310" --networkid 5151 --unlock "0x99971588F1EB72f0Ab8cdCf2c008c0110d4897c5 " --password node2/password.txt --allow-insecure-unlock --mine
  
In order to send transactions, a keystore file will need to be loaded into MyCrypto, and the corresponding password entered, in order to send transactions. Load the node/wallet that you want to send the transaction from. Connect to the fintechnet custom node by using the chain ID and RPC port. Enter the wallet address you would like to send ETH to - and send the transaction. 

If the nodes are active the block will be made and the transaction will be processed by the network. 
