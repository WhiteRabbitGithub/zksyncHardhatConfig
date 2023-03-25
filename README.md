Make Sure you install Dependencies will update later

1. https://era.zksync.io/docs/dev/building-on-zksync/hello-world.html
2. https://era.zksync.io/docs/api/hardhat/hardhat-zksync-verify.html

```
npm init -y
npm i -D @matterlabs/hardhat-zksync-verify @nomiclabs/hardhat-etherscan
npm i -D typescript ts-node ethers@^5.7.2 zksync-web3 hardhat @matterlabs/hardhat-zksync-solc @matterlabs/hardhat-zksync-deploy
npm i @openzeppelin/contracts 
```

hardhat.config.ts

```
import "@matterlabs/hardhat-zksync-deploy";
import "@matterlabs/hardhat-zksync-solc";
import "@matterlabs/hardhat-zksync-verify";


module.exports = {
  zksolc: {
    version: "1.3.5",
    compilerSource: "binary",
    settings: {},
  },
  defaultNetwork: "zkSyncMain",

  networks: {
    zkSyncTestnet: {
      url: "https://zksync2-testnet.zksync.dev",
      ethNetwork: "goerli", // Can also be the RPC URL of the network (e.g. `https://goerli.infura.io/v3/<API_KEY>`)
      zksync: true,
    },
    zkSyncMain: {
      url: "https://mainnet.era.zksync.io",
      ethNetwork: "https://mainnet.era.zksync.io", // Can also be the RPC URL of the network (e.g. `https://goerli.infura.io/v3/<API_KEY>`)
      verifyURL: 'https://zksync2-mainnet-explorer.zksync.io/contract_verification',
      zksync: true,
    },
  },
  solidity: {
    version: "0.8.17",
  },
};

```

