# EtherInsure

### How to run the app with a local blockchain - hardhat after git cloning the repo and yarn (to install from package.json) for contracts and UI folders.

#### Step1 : create a .env file in contracts folder and add private keys for sepolia, goerli (they are needed otherwise hardhat will complain). You need to first create API keys in your Alchemy account for Goerli and Sepolia.

**(PS: Ensure that .env is added to .gitignore and do not push .env to github, even by mistake.)**

**The .env must contain.**
```
ALCHEMY_GOERLI_API_KEY='<Your alchemy API Key for Goerli>'
GOERLI_DEPLOYER_KEY='<Private Key of your metamask account>'
ALCHEMY_SEPOLIA_API_KEY='<Your alchemy API Key for Sepolia>'
SEPOLIA_DEPLOYER_KEY='<Private Key of your metamask account>'
```
#### Step2: Start local hardhat network on one terminal
```
$npx hardhat node --network hardhat
```
#### Step3: Deploy the contracts to the local network from another terminal
```
$npx hardhat run scripts/deploy.ts --network localhost
```
#### Step4: Choose any two accounts of the local hardhat blockchain and import the private keys into metamask from these accounts. If they are already existing then clear the nonce in advanced settings of metamask.

#### Step5: Ensure metamask is connected to localhost, if localhost is not available in metamask then create a network and add it as localhost with chain ID = 1337 and rpc as http://localhost:8545/

### Step6: Create a .env in the UI folder and add the key for web3 storage token (from web3.storage)
```
VITE_WEB3STORAGE_TOKEN=<Your Web3 Storage Token> 
```
### Step7: Now start the frontend UI with 
```
yarn run dev
```




