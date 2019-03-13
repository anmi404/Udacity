# Project #5, Decentralized Star Notary

In this project I built a DApp in such a way that: 
1. The smart contract tokens have a name and a symbol.
2. The function: lookUptokenIdToStarInfo() in StarNotary.sol file has been implemented.
```
function: lookUptokenIdToStarInfo in StarNotary.sol file
@Receives the token ID
@Returns the name of the star
```
3. The function exchangeStars() has been implemented.
```
function: exchangeStars in StarNotary.sol file.
@Receives 2 token IDs, allows two users to exchange their stars
```
4. The function transferStar() was implemented.
```
function transferStar in StarNotary.sol file.
@Receives an address and a token. Transfers the corresponding star to that address. 
```
5. I have added Unit Tests in TestStarNotary.js file for asserting that:
   - The token name and token symbol are added properly.
   - 2 users can exchange their stars.
   - Stars Tokens can be transferred from one address to another.
6. The file truffle-config.js is configured to support deploying the contract to Rinkeby Public Network.	
7. The front-end function lookUp has been implemented in the index.js file. This allows to retrieve the star name given its token Id. An example web page has been provided in order to show this function in action. 
When you click on the button "Look Up" the application shows in the status the Star information.

## Setup project for Review.

The smart contract tokens should have a name and a symbol. They can be changed in the StarNotary.sol file.
Currently, the name of the token is **Project 5 Token**, and the symbol is **P5T**.

The versions or the packages installed are:
- Truffle v5.0.7 (core: 5.0.7)
- Solidity v0.5.0 (solc-js)
- Node v10.13.0
- openzeppelin-solidity v2.1.2
- truffle-hdwallet-provider v1.0.2

### Deploy your Contract to Rinkeby

In order to deploy the contract to the Rinkeby Public Network, you need to configure file truffle-config.js (or truffle.js). 
To that end the following steps can be followed:
1. Get the endpoint address from https://infura.io: Create a new project and choose the Rinkeby network from the Endpoints menu. Copy the address and paste the infura key into the truffle.js file. 
2. Uncomment the line: 
```
const HDWalletProvider = require('truffle-hdwallet-provider'); 
```
3. Copy the mnemonic returned by Metamask to constant __mnemonic__. 
4. Insert the following lines into the networks table:
```
rinkeby: {
        provider: () => new HDWalletProvider(mnemonic, `https://rinkeby.infura.io/v3/${infuraKey}`),
          network_id: 4,       // rinkeby's id
          gas: 4500000,        // rinkeby has a lower block limit than mainnet
          gasPrice: 10000000000
        },
```
5. Setup a valid Rinkeby account in Metamask.

## Testing the project
In order to test the project in the local network, run:
```
truffle migrate --reset
truffle test --network develop
```
To execute in the rinkeby network the contract run command:
```
truffle migrate --reset --network rinkeby
```
A web page has been provided, allowing both to create a star and to retrieve the name of the star given its token.
You can access that page at address localhost:8080 after executing __npm run dev__ in the terminal. 

## What do I learned with this Project

I was able to apply in practice the knowledge related to the necessary tools to create a DApp, from the smart contract to the front end. 

## Acknowledgments
Thanks for the help in general.
