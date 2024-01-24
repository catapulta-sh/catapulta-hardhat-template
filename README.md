# Catapulta Hardhat Template

Template repository for getting started quickly with [Catapulta.sh](https://catapulta.sh) and Hardhat projects.

This template uses [Scaffold-ETH 2](https://github.com/scaffold-eth/scaffold-eth-2).

## Requirements

Before you begin, you need to install the following tools:

- [Node (v18 LTS)](https://nodejs.org/en/download/)
- Yarn ([v1](https://classic.yarnpkg.com/en/docs/install/) or [v2+](https://yarnpkg.com/getting-started/install))
- [Git](https://git-scm.com/downloads)

## Deploy to Sepolia testnet with Catapulta and Hardhat

1. Clone this repo & install dependencies

```
git clone https://github.com/catapulta-sh/catapulta-hardhat-template
cd catapulta-hardhat-template
yarn install
```

2. Generate a new private key with Catapulta, is stored offline in your .env, or add your own as `PRIVATE_KEY` in the .env file stored at the root of the project

```
cd packages/hardhat

npx catapulta wallet

# Output:
# Wallet address: 0x6B193d5604e09f1737E33cFc4B06fb3f2C7fC3CE
# Private key appended to your .env file.
```

3. Get funds for your Ethereum address at the [Alchemy Sepolia faucet](https://sepoliafaucet.com/)

4. Setup your `CATAPULTA_API_KEY` into your .env from, generate one for free at [Catapulta dashboard](https://catapulta.sh)

 5. Run the command `hardhat init` to initialize hardhat before deployment.
 6. Deploy the contract into Sepolia testnet with Catapulta

```
catapulta deploy --network sepolia
```

```
#Output:

Catapulta.sh 🏏 Hardhat deployment (0.1.36)
===========================================
Project name: Ghost Deployments
Project URL: https://catapulta.sh/project/64e6272a59b37a3a4a7afb55
Deployment UUID: 6c7f65cb-52e0-459e-9b58-a5b3d5f296f2

📀 Building artifacts...

🗜  Compressing artifacts...

📤 Uploading artifacts to the Catapulta DB...

✅ Artifacts uploaded successfully.

📡 Broadcasting deployments to Catapulta Gateway RPC:

📜 Running Hardhat script: yarn run hardhat --network catapulta-6c7f65c2-52e0-459e-9b58-a5b3d5f296f2 deploy

deploying "YourContract"
 (tx: 0x9f4532ec9c34fed74d8295d0991d9935be194e582616a0660b6c51154204bf88)...
: deployed at 0xF31540a002a49bda9963caAcCeF3e25d0a09810e with 534015 gas

📝 Updated TypeScript contract definition file on ../nextjs/generated/deployedContracts.ts

✅ Deployment successfully broadcasted

- Etherscan verification request sent. Check the dashboard for keeping track verifications. If contracts are not verified in 10 minutes, contact support at Discord.

💾 Artifacts stored at:
- https://users-artifacts.s3.eu-west-1.amazonaws.com/6c7f65cb-52e0-459e-9b52-a5b3d5f296f2-deployment-artifacts/artifacts.zip

📸 Check your deployment report at:
 - https://catapulta.sh/project/64e6272a59b37a3a4a7afb55/op/6c7f25cb-52e0-459e-9b58-a5b3d5f296f2
```

6. Check the deployment report at the Catapulta UI, and enjoy delegated Etherscan verification without any extra configs or Etherscan API keys.

![e6uSRe8e](https://github.com/catapulta-sh/catapulta-scaffold-eth-2/assets/11179847/9a2d14d6-34ee-4cc9-9d69-5c4433249ac3)



## Quickstart

To get started with Scaffold-ETH 2, follow the steps below:

1. Clone this repo & install dependencies

```
git clone https://github.com/scaffold-eth/scaffold-eth-2.git
cd scaffold-eth-2
yarn install
```

2. Run a local network in the first terminal:

```
yarn chain
```

This command starts a local Ethereum network using Hardhat. The network runs on your local machine and can be used for testing and development. You can customize the network configuration in `hardhat.config.ts`.

3. On a second terminal, deploy the test contract:

```
yarn deploy
```

This command deploys a test smart contract to the local network. The contract is located in `packages/hardhat/contracts` and can be modified to suit your needs. The `yarn deploy` command uses the deploy script located in `packages/hardhat/deploy` to deploy the contract to the network. You can also customize the deploy script.

4. On a third terminal, start your NextJS app:

```
yarn start
```

Visit your app on: `http://localhost:3000`. You can interact with your smart contract using the contract component or the example ui in the frontend. You can tweak the app config in `packages/nextjs/scaffold.config.ts`.

Run smart contract test with `yarn hardhat:test`

- Edit your smart contract `YourContract.sol` in `packages/hardhat/contracts`
- Edit your frontend in `packages/nextjs/pages`
- Edit your deployment scripts in `packages/hardhat/deploy`

## Documentation

Visit our [docs](https://docs.scaffoldeth.io) to learn how to start building with Scaffold-ETH 2.

To know more about its features, check out our [website](https://scaffoldeth.io).

## Contributing to Scaffold-ETH 2

We welcome contributions to Scaffold-ETH 2!

Please see [CONTRIBUTING.MD](https://github.com/scaffold-eth/scaffold-eth-2/blob/main/CONTRIBUTING.md) for more information and guidelines for contributing to Scaffold-ETH 2.
