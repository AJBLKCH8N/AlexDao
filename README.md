**** INSTRUCTIONS FOR ALEX*****\


Since youre going to create a brand new front end, you can ignore everything except for 'SmartContracts' folder.

PRELIMINARY REQUIREMENTS:
So first, what youre going to want to do is:
 a) Create a Metamask wallet (install this in your browser as a browser extension):
 i) go to this link: https://metamask.io/ 
 ii) Download and install Metamask
 iii) Once metamask is installed, select the Goerli Test Network from the drop down as per below (you may need to go to settings and unhide other networks)
 ![image](https://user-images.githubusercontent.com/35590284/202651176-50f4f740-7d55-4dc7-b19f-d162766d1836.png)
 
 b) add test funds to your wallet - 
 i) now that you have a metamask wallet, you need to add test ethereum to your wallet - use this link( you have to sign up) and paste your wallet address in the bar:
 ![image](https://user-images.githubusercontent.com/35590284/202651768-25235548-ab11-4ed1-823a-27873db8578c.png)

Now that you have funds, you can interact with smart contracts!

CREATING a COLLECTION & NFT ON OPENSEA
_Disclaimer: this is just a quick way to do it, but in reality wed create an NFT smart contract and deploy using hardhat or truffle_
c) now that you have a wallet with funds, go here: https://testnets.opensea.io/  and use metamask to 'Accept and Sign'.
i) in OpenSea Testnet, go to the top right corner and click on the circular orb representing your account: ![image](https://user-images.githubusercontent.com/35590284/202652441-c4299a13-6e41-476d-b05a-0527431695fe.png)
ii) on the dropdown click on create
iii) now use the menu to create a new item (NFT) - upload an image, (dont worry about collection - leave it blank) keep the network on GOERLI and create the item.
Iv) now that youve created the NFT, go to 'Details' and youll see 'Contract Address' and 'Token ID':
![image](https://user-images.githubusercontent.com/35590284/202652912-92553fca-55c9-41fc-b27c-b364a763d15e.png)

Copy Contract Address to the 'daoContract' field in your constructor of your smart contract : daoContract = IdaoContract();
Copy the TOKEN ID to the valid tokens array in the constructor: validTokens = [];

DEPLOYING YOUR SMART CONTRACT:
_Normally wed deploy the smart contract using hardhat or truffle, but the quick way is using remixide_
d) go to : https://remix.ethereum.org/ 
I) copy your smart contract to a new file here, complie and in the 'deploy' blade, select 'Injected Provider -Metamask' ![image](https://user-images.githubusercontent.com/35590284/202653910-95f6548a-0e8e-4b7c-8c95-d22f52857a87.png)
and then deploy the smart contract.
It should spit out a Contract Creation Address which you can click on and view in Etherscanner.

ETHERSCANNER
 
 e) go to etherscanner: https://goerli.etherscan.io/ and past your DAO smart contract address
 i) Once you found your smart contract address you can 'verify your code' by copy and pasting your code into Etherscanner to verify your code.
 ii) once your code is verified you are all set to go. You can now look at your contract and find your smart contract ABI which is needed for the front end
 
 
 **_DISCLAIMER - this is a long winded way of doing all of this, but basically, hardhat and/or truffle will do alllllll of this for us... however there is a learning curve for it (not too hard); we can run through this when youre ready. Hardhat is my tool of choice tbh... and once you build your contract it generates the ABI and also acn deploy it to Ethereum or the testnets easily from the commandline. (you can even spin up a test blockchian)_**









#Smart Contract Folder
the DAO.SOl smart contract allows for token holders (NFT Holders) to create and vote on submitted proposals.
This version is based on the project tutorial by MoralisWeb3.

This project utilises the Moralis Web3 suite and Web3API to integrate the front end to the Polygon chain. 

Future Releases:
a. To apply use case to real world application of the Rotary Club and its members:
    1. Create a Rotary Club NFT that allows specified Club Owners with access control to mint new tokens, allocate to addresses (i.e club members), and to destroy tokens (when a member leaves the club).
    2. Modify DAO contract to change ownership structure so in line with required rules and logic
    3. Modify front end to cater for Rotary Club use case.
b. Add functionality for the Home.js to include the Forum and Documentation pages
c. Refactor code to decouple the project from Moralis Web3 APIs to an alternative.
d. Rebuild project and refactor contracts where possible to allow for deployment on Solana
