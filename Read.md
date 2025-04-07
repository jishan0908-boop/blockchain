```
sudo apt update
```
to update the system

```
sudo apt install golang-go
```
to install golang-go

```
sudo snap install docker
```
to install docker

```
sudo apt install git
```
to install git

```
git clone -b main https://github.com/hyperledger/fabric-samples.git
```
to install fabric-samples

```
sudo apt install curl
```
to install curl


```
cd fabric-samples
```
to get in fabric-samples

```
sudo bash
```


```
curl -sSL https://bit.ly/2ysbOFE | bash -s
```
to pull hyperledger docker images


```
cd test-network
```
to get into test-network

```
./network.sh
```
```
./network.sh up
```
to up the network

```
./network.sh createChannel
```
to create channel

```
./network.sh down
```
to down the network

```
wget https://dist.ipfs.tech/kubo/v0.32.1/kubo_v0.32.1_linux-amd64.tar.gz
```
to install IPFS

```
tar -xvzf kubo_v0.32.1_linux-amd64.tar.gz
```
to use kubo

```
cd kubo
```
to get into kubo directory

```
sudo bash install.sh
```
to move to local bin

```
ipfs init
```
to initialise ipfs

```
ipfs daemon
```
to use daemon

![pic 3](https://github.com/user-attachments/assets/70fe107a-0780-4f92-a65e-724c1d8c426b)



```
ipfs.log 2>&1 &
```
To run ipfs daemon in background

```
echo "Hello, IPFS!" > hello.txt
ipfs add hello.txt
ipfs cat <CID>
```
to add file

![two](https://github.com/user-attachments/assets/a3498732-e133-41c6-a4f2-7b1e21234150)

```
mkdir myfolder
echo "File 1 content" > myfolder/file1.txt
echo "File 2 content" > myfolder/file2.txt
ipfs add -r myfolder
```
to add a directory

![three](https://github.com/user-attachments/assets/4e0d51e5-ae0e-4034-b79d-fe3ac89a0666)


```
ps aux | grep ipfs
```
lists running processes

```
kill <PID>
```
to kill the process

## encrypting and decrypting
```
echo "Hello, bruh" > myfile.txt
ipfs add myfile.txt
openssl enc -aes-256-cbc -pbkdf2 -iter 100000 -salt -in myfile.txt -out myfile_encrypted.txt -pass pass:yourpassword
ipfs add myfile_encrypted.txt
cat myfile_encrypted.txt
openssl enc -d -aes-256-cbc -pbkdf2 -iter 100000 -in myfile_encrypted.txt -out decrypted_file.txt -pass pass:yourpassword
cat decrypted_file.txt
ipfs add decrypted_file.txt
```

![enc-dec](https://github.com/user-attachments/assets/293f1b3a-4ba4-4b35-8f04-d93fb9c9a6f7)


## to push video and audio

```
ipfs add <audio-path>
```
to add audio

![pic2](https://github.com/user-attachments/assets/23e5aa80-51d3-4f99-8daf-8e354b5c94d1)



```
ipfs add <video-path>
```
to add video

![pic1](https://github.com/user-attachments/assets/bc6c1e37-bff7-45d7-b25a-61c80d6dbfb2)


# Creating Meta Mask Account

## The metamask account is our wallet where it store the token , like sepolia faucet which are the test token , with the help of metamask wallet we will do the transaction and deploy our smart contract on the blockchain.

![Screenshot from 2025-04-07 14-05-57](https://github.com/user-attachments/assets/fd40a51f-29f0-4b0b-ac32-cae2e36eeccb)

# Sepolia Faucet

## These are the test token because we can;t efford the etherum coin , also for the learning purpose we use them , these faucet can be get from the Google Cloud.

![Screenshot from 2025-04-07 14-08-21](https://github.com/user-attachments/assets/197de3d9-335a-41e5-a63e-6a7bf40e5640)

![Screenshot from 2025-04-07 14-08-43](https://github.com/user-attachments/assets/015216ac-1931-407c-a698-238a237f2c91)

### Here in the above Image you can see the Wallet Address where we have to add the our metmask wallet address then click on the recive button and when you refresh your metamask account you can see the faucets.


# Solidity:

## We write our smart contract in the solidity language .

## To use this Language I have used the Remix ide website where I can deploy my contract for free also we can use our metamask account to know how to make transcation through that.

![Screenshot from 2025-04-07 14-14-40](https://github.com/user-attachments/assets/999e5a01-ba76-4c09-ac6d-437fd7f6e8bb)

![Screenshot from 2025-04-07 14-15-33](https://github.com/user-attachments/assets/4278e7a5-1d63-4dbf-a762-33c43c31e0a9)

![Screenshot from 2025-04-07 14-16-15](https://github.com/user-attachments/assets/0c21e558-0b39-4fc4-a87d-f97e08af0140)

### In above Image , the file explore saves our contracts.


## Practice of Solidity:

## 1. To work in solidity we have to add these line of code in every smart contract that we are going to create , here SPDX is licence which tells , who can see the our contract and use it because the blockchain provides transpency , in next line we use pragma it tells the version of solidity we are using we can change the version of solidity as per our needs.

```
// SPDX-License-Identifier: MIT
pragma solidity ^0.8.18;
```







