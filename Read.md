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

## 2. Worst basic program we can write .

```
contract Hello {
    string public welecome = "Hello World";
}
```
## The above code is the worst program but have some basic imp concepts that we can use , for eg , the contract is the key word in solidity , where inside the contract we are going to write our how ER200 , after that we used the string which is a datatype , and public represent that everyone can see our contract and use it.

## 3. Creating function in solidity:

```
contract Calculator{
    uint256 result = 0 ; 
    function add(uint128 num1) external {
        result += num1;
    }

    function subtract(uint128 num2) public{
        result -= num2;
    }

    function multiply(uint128 num3) public{
        result *= num3;
    }

    function get() public view returns (uint256){
        return result; 
    }

}
```
##  In the above code we have use the function , where to define any function first we use the function keyword them we name that function then we add some paameters that we are going to pass , then we add the abtraction level , where we have four type of abstraction  public , private , internal and external, then we add view keyword to see the result and then we add retruns if our function is returning any thing we have to give the retrun type also.

## 4. Showing demonstation how we deploy our contract on block chain.

## I have created an code where I have used the modifyier , struct ,constructor .
# code
## Breif about code , here the code is of twitter , where a person can tweet and that tweet is stored in the string array , also that array stores the author information which is our address of wallet , content which is our tweet , timestamp which store the time and the likes which tell the number of likes we get on our tweet. 
```
// SPDX-License-Identifier: MIT
pragma solidity ^0.8.18;

contract Twitter{
    
    struct Tweet {
        address author;
        string content;
        uint256 timestamp;
        uint256 likes;
    }

    uint8  MAX_TWEET_LENGTH = 100;
    address public owner;
    constructor(){
        owner = msg.sender;
    }

    modifier onlyOwner(){
        require(msg.sender == owner , "You are not the owner");
        _;
    }

    mapping(address => Tweet[]) public tweets;

    function chnageTweetLength(uint8 newTweetLength) public onlyOwner{
        MAX_TWEET_LENGTH = newTweetLength;
    } 

    function createTweet(string memory _tweet) public {
        require(bytes(_tweet).length <= MAX_TWEET_LENGTH , "Tweet is tooo long \n");

        Tweet memory newTweet = Tweet({
            author:msg.sender,
            content:_tweet,
            timestamp:block.timestamp,
            likes: 0
        });
        tweets[msg.sender].push(newTweet);
    }

    function getTweet( uint _i) public view returns(Tweet memory){
        return tweets[msg.sender][_i];
    }

    function getAllTweets(address  _owner) public view returns (Tweet[] memory){
        return tweets[_owner];
    }
}

```
# Complieing the code
![Screenshot from 2025-04-07 14-34-01](https://github.com/user-attachments/assets/37e7677e-722f-4a28-a2c6-dbab8257a348)
![Screenshot from 2025-04-07 14-34-48](https://github.com/user-attachments/assets/10c99103-6e3c-462e-9c8b-d80077b94342)

# Deploying on blockchain

![Screenshot from 2025-04-07 14-35-04](https://github.com/user-attachments/assets/ad666360-c7d5-4ff5-ad07-75a70b626110)

## After Deploying we can see the green tick which show our contract is deployed on the blockchain

![Screenshot from 2025-04-07 14-35-32](https://github.com/user-attachments/assets/755c771e-4082-4db2-82dd-94c0a6f8b004)

## Running the code 

![Screenshot from 2025-04-07 14-39-21](https://github.com/user-attachments/assets/6e3b4f1b-9a33-4f7b-95d2-5dfbdf411698)

![Screenshot from 2025-04-07 14-39-53](https://github.com/user-attachments/assets/9c99934e-7f9e-4508-b559-80027e202ab6)

![Screenshot from 2025-04-07 14-40-20](https://github.com/user-attachments/assets/d8fc347f-6e1c-4e8c-9612-4794260d6544)

![Screenshot from 2025-04-07 14-40-33](https://github.com/user-attachments/assets/de9a6069-b291-4ea6-9159-9510dd01fa83)
