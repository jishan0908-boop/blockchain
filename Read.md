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


# Deploying My COntract on the Sepolia Network !!

## Code :-

```

// SPDX-License-Identifier: MIT
pragma solidity ^0.8.18;

contract Twitter{
    uint256 retweet = 0;
    uint16 public MAX_LEN = 100;
    struct Profile{
        uint256 id;
        address User;
        string Data;
        uint256 Likes;
        uint256 Timestamp;
        uint256 Retweets;
    }
    mapping(address => Profile[]) public tweets;
    address public UserAcc;
    constructor(){
       UserAcc = msg.sender;
    }
    
    modifier OnlyOwner() {
        require(msg.sender == UserAcc, "User Name Not Found!!");
        _;
    }
    function changeTweetLength(uint16 _newTweetLen) public OnlyOwner {
        MAX_LEN = _newTweetLen;
    }

    function createTweet(string memory _tweet) public{
        require(bytes(_tweet).length <= MAX_LEN , "Tweet is too long!!!!!."); //Adding condition where the length of tweet must be limited.
        Profile memory PF1 = Profile({
            id:tweets[msg.sender].length,
            User:msg.sender,
            Data:_tweet,
            Likes:0,
            Timestamp:block.timestamp,
            Retweets: retweet
        });
        tweets[msg.sender].push(PF1); // This will add the tweets into the array .
        retweet++;
    }
    function LikesTweets(address User , uint256 id) external {
        require(tweets[User][id].id == id , "Tweet Dose Not Exit !!!");
        tweets[User][id].Likes++;
    }
    function UnLikeTweets(address User , uint256 id) external{
        require(tweets[User][id].id == id ,"Tweet Dose Not Exit !!!");
        require(tweets[User][id].Likes > 0 , "There is on Likes!!");
        
        tweets[User][id].Likes--;
    }
    function getTweets(address _owner, uint32 _i) public view returns(Profile memory){
        return tweets[_owner][_i]; // It will provide the specifc tweet , that is persent at the specifc index of the array.
    }
    function getAllTweets(address _owner) public view returns(Profile[] memory){
        return tweets[_owner]; // This will return all the tweets present in that address .
    } 
}

```

## MetaMask Asking for conormation : - 

![Screenshot from 2025-05-15 13-05-25](https://github.com/user-attachments/assets/b45478a1-21a3-446c-abeb-6a05a9598088)


## Deploying My Smart Contract: -

![Screenshot from 2025-05-15 12-58-14](https://github.com/user-attachments/assets/d291fed6-2963-434a-8c67-47e7a1a9e4ef)

## Having Tarchsaction :-

![Screenshot from 2025-05-15 12-55-15](https://github.com/user-attachments/assets/7f63773e-81da-46e8-9db0-0ab5eeb300f2)

## All Transaction :-

![Screenshot from 2025-05-15 12-58-34](https://github.com/user-attachments/assets/3eee8f55-216f-4901-8289-6ad7754368ae)

## Created An Event :-

![Screenshot from 2025-05-15 14-59-42](https://github.com/user-attachments/assets/1d296e98-76ab-4588-9b69-7ac33710e14f)


# Lab Question:

## 1. Create a voting system with multiple candidates. Each address can vote only once.
```
// SPDX-License-Identifier: MIT
pragma solidity ^0.8.0;

contract VotingSystem {
    struct Candidate {
        string name;
        uint256 voteCount;
    }

    mapping(address => bool) public hasVoted;

    Candidate[] public candidates;

    event Voted(address indexed voter, uint256 indexed candidateIndex);

    constructor(string[] memory _candidateNames) {
        for (uint i = 0; i < _candidateNames.length; i++) {
            candidates.push(Candidate({ name: _candidateNames[i], voteCount: 0 }));
        }
    }

    function vote(uint256 candidateIndex) external {
        require(!hasVoted[msg.sender], "You have already voted!");
        require(candidateIndex < candidates.length, "Invalid candidate index");

        candidates[candidateIndex].voteCount += 1;
        hasVoted[msg.sender] = true;

        emit Voted(msg.sender, candidateIndex);
    }

    function getNumCandidates() external view returns (uint256) {
        return candidates.length;
    }

    function getCandidate(uint256 index) external view returns (string memory, uint256) {
        require(index < candidates.length, "Invalid candidate index");
        Candidate storage candidate = candidates[index];
        return (candidate.name, candidate.voteCount);
    }
}

```
![Screenshot from 2025-05-22 12-37-51](https://github.com/user-attachments/assets/20933685-6654-4959-aab5-750518856cae)
![Screenshot from 2025-05-22 12-39-16](https://github.com/user-attachments/assets/f180438c-246a-4646-b8e0-d7ce7adafc14)

##Write a contract that manages a list of student records (name, roll number). Allow adding and retrieving student data.

```
// SPDX-License-Identifier: MIT
pragma solidity ^0.8.18;

contract Student{
    struct Record {
        address RollNo;
        string Name;
    }

    Record[] public record;

    function addRecord(address Id ,string memory Name) public returns(string memory){
        require(!check(Id),"This Roll No Already Exits!!!;");
        record.push(Record({RollNo: Id, Name: Name}));
        return "Add Student Successfully!!!!";
    }
    function check(address Id) internal view returns(bool){
        for(uint256 i = 0 ; i <record.length ; i++){
            if(record[i].RollNo == Id){
                return true;
            }
        }
        return false;
    }

    function getRecord(uint256 Id) public view returns(address,string memory)
    {
        return(record[Id].RollNo,record[Id].Name);
    }
}
```


![Screenshot from 2025-05-22 18-57-45](https://github.com/user-attachments/assets/ca82cda9-4c7b-4163-b2ec-886390cc4476)

![Screenshot from 2025-05-22 18-45-16](https://github.com/user-attachments/assets/1315de0c-fc02-4457-a992-224679671760)

![Screenshot from 2025-05-22 18-56-32](https://github.com/user-attachments/assets/43dff70d-4987-44d4-b801-db55c880ff77)


## Develop a contract that only allows the deployer (owner) to call a specific function (use modifiers).
```
// SPDX-License-Identifier: MIT
pragma solidity ^0.8.18;

contract Third {
    address public owner;
    
    constructor() payable {
        owner = msg.sender; 
        emit OwnershipTransferred(owner, msg.sender);
    }
    
    modifier onlyOwner(){
        require(msg.sender == owner, "This function can only be called by the current owner");
        _;
    }
    
    event OwnershipTransferred(address _oldOwner, address  _newOwner);
    
    function transferOwnership(address _newOwner) external onlyOwner {   
    require(_newOwner != address(0), "New owner can't be the zero address");
        
        emit OwnershipTransferred(owner, _newOwner);
        owner = _newOwner;
    }
}
```
![Screenshot from 2025-05-22 19-02-19](https://github.com/user-attachments/assets/4732d6ac-ca0f-4ea5-b2fc-9f89eb21dc0b)
![Screenshot from 2025-05-22 19-02-48](https://github.com/user-attachments/assets/6e495f80-318a-4907-b1bb-1c01813fd948)
![Screenshot from 2025-05-22 19-03-08](https://github.com/user-attachments/assets/25f7a94d-20fb-4072-9f1e-8a38003f59f4)

## Write a contract where people can donate Ether and the top 3 donors are tracked.


```
// SPDX-License-Identifier: MIT
pragma solidity ^0.8.18;

contract DonationBox {
    address public owner;

    constructor() {
        owner = msg.sender; 
    }

    function donate() public payable {
        require(msg.value > 0, "Must send some Ether");
    }


    function withdraw() public {
        require(msg.sender == owner, "Only owner can withdraw");
        payable(owner).transfer(address(this).balance);
    }

    function getBalance() public view returns (uint) {
        return address(this).balance;
    }
}

```
![Screenshot from 2025-05-22 19-18-12](https://github.com/user-attachments/assets/906b4127-4a07-424f-8565-3fbcecd08126)

![Screenshot from 2025-05-22 19-18-44](https://github.com/user-attachments/assets/d96767a3-3a29-46a8-a411-5ae001f29766)

![Screenshot from 2025-05-22 19-19-00](https://github.com/user-attachments/assets/10c941a4-f142-446b-ad5f-8b5293cf1f9b)

![Screenshot from 2025-05-22 19-19-14](https://github.com/user-attachments/assets/9af8662b-14c2-4022-ab7a-78d1b2814569)

![Screenshot from 2025-05-22 19-19-56](https://github.com/user-attachments/assets/7c9d3f9d-98b9-44dc-8a83-d587c72eb821)



