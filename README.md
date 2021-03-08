# Proof of Authority Development Chain

## Building Blockchain

1 - Create  a new project directory 

2 - Open your terminal and activate your virtual environment - conda activate ethereum5

3 - Direct to the folder in which you have “[Go Ethereum Tools](https://geth.ethereum.org/downloads/)"

4 - Create Screenshot folder


## Creating Nodes

1- Create empty directories for nodes
    mkdir node1 
    mkdir node2

2- Get new accounts numbers from nodes to use as signers
    ./geth account new --datadir node1
    ./geth account new --datadir node2
3- Save passwords & Account addresses for use later

 ![1](https://github.com/arzuisiktopbas/18-Blockchain/blob/main/Screenshot/1.png)
 
Node 1: Public address of the key:   0xDFA75550A43F59590966A4F2AE0D9Af2d43DC8DE
Path of the secret key file: node1/keystore/UTC--2021-03-08T21-12-00.576171000Z--dfa75550a43f59590966a4f2ae0d9af2d43dc8de
Node 2: Public address of the key:   0x648Ac0ab0D9bA0e692C8A9104e7fb004fD05a0b2
Path of the secret key file: node2/keystore/UTC--2021-03-08T21-12-39.703051000Z--648ac0ab0d9ba0e692c8a9104e7fb004fd05a0b2

echo 'node1' > node1/password.txt
echo 'node2' > node2/password.txt
echo 'DFA75550A43F59590966A4F2AE0D9Af2d43DC8DE' >> accounts.txt
echo '648Ac0ab0D9bA0e692C8A9104e7fb004fD05a0b2' >> accounts.txt
 
4- Run puppeth
   ./puppeth
   
5- Initialize nodes 
   ./geth init arznet.json --datadir node1
   ./geth init arznet.json --datadir node2

6- Start up a mining thread/node (node1)
   ./geth --datadir node1/ --mine --minerthreads 1 --unlock 'DFA75550A43F59590966A4F2AE0D9Af2d43DC8DE' --password node1/password.txt --rpc --allow-insecure-unlock

7- Start mining (node2)
   Open a new terminal and direct the correct folder.

  ./geth --datadir node2/ --port 30304 --bootnodes 'enode://86e4b6122b8901bb634c23ada5574336efe0b52f3f5222916e37dee83a8d7218a720ce612adf4897b881c7bb556355cbd6575a6000aec48e270170b75b716e6d@127.0.0.1:30303 '

## MyCrypto

1- MyCrypto & Click on "Add Custom Node", then add the custom network information.

2- Import the keystore file from the directory into MyCrypto.

3- Make transaction

4- Copy the hash and paste it into the "TX Status" section of the app, or click "TX Status" in the popup
    Hash : "0x4aa8e35ce6c194050b8ba68105a38d84f91429c90fb7328d468fbc4e59f1e2dd"


   ![Go Ethereum Tools](https://geth.ethereum.org/downloads/)
