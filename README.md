# donate3

# Project Name

🧧Donate3

# Introduction in short

Donate3 is a public good that offers a simple and convenient multi-chain donation tool, aggregating donor and recipient data. It enables public goods and creators to set up donations in just 5 minutes. Additionally, it is a highly scalable public good project that serves as infrastructure to support the construction of web3 public goods.

# Teams

| Github                                     | Avatar                                                             | Email                         |
| ------------------------------------------ | ------------------------------------------------------------------ | ----------------------------- |
| [0xhardman](https://github.com/0xhardman)  | ![0xhardman](https://avatars.githubusercontent.com/u/47655472?v=4) | 1142783160@qq.com             |
| [T](https://github.com/tangminjie)         | ![](https://avatars.githubusercontent.com/u/66615553?v=4)          | tangminjie130@gmail.com       |
| [stephenhe](https://github.com/hefansuper) | ![](https://avatars.githubusercontent.com/u/32589107?v=4)          | programmerstephenhe@gmail.com |
| [wwei](https://github.com/wwei-github)     | ![](https://avatars.githubusercontent.com/u/46670626?v=4)          | ww418047394@gmail.com         |

# Bounty Detail

## Boutnty Goal

**Make a Dapp That Slaps, No Cap**

## What Consensys Products We Used

### Infura

Donate3 is multi-chain donation tool. Our backend need to read donation data from different chains to calculate how much donation the donator donated and how much donation the recipient received. We need to aggregate these data to provide users with a better donation data query experience. **Infura** provides us with an unparalleled experience and a wealth of endpoint choices, including Layer1's eth and polygon mainnet, testnet, and Layer2's linea, optimism, arb almost perfectly covering Donate3's perfection need. At the same time, the **Infura Web3 API** also provides us with a large amount of free quota, which perfectly supports our need to query the contract update every five minutes per chain every day.

Related Code：

- [RPC_MAP iN backend](./backend/src/config/index.ts)
- [RPC_MAP used when deployed contract](./contract/.env.example)

### Linea

#### Thing You Want to Know

#### Link to Contract

[Contract Lineascan](https://lineascan.build/address/0x3a42ddc676f6854730151750f3dbd0ebfe3c6cd3)

[Contract Blockscout](https://explorer.linea.build/address/0x3a42DDc676F6854730151750f3dBD0ebFE3c6CD3)

#### Config In hardhat

[hardhat config](./contract/hardhat.config.ts)
[wallet config](./sdk/src/Donate3/chains/linea.ts)

### Metamask SDK

see in youtube link, mainly connect the wallet

# Description

## Background

Public goods are available for public use, cannot be excluded from the use of others, one person's use will not reduce the use of other people, non-competitive and non-exclusive. In real life, for example, parks, libraries, museums, etc., these facilities are usually provided by the government or public organizations to meet the basic needs and interests of the public.

In the context of decentralization, users' demand for public goods still exists, and there are also a large number of organizations building public goods, such as: [LXDAO](https://lxdao.io/), [WTFAcademy](https://www.wtf.academy/), [GreenPill](https://greenpill.network/), etc. These organizations have created a large number of excellent public goods works: [MyFirstLayer2](https://layer2.myfirst.io/), [MyNFT](https://myfirstnft.info/), [Solidity 101](https://www.wtf.academy/solidity-start) Benefactor web3 community, attracting more people to become web3 users.

However, our web3 world does not have a government or public organization to maintain public goods, which makes it difficult to maintain a large number of good public goods without financial support. Our team believes that the responsibility for public goods in the web3 world returns to web3 users, and we also believe that web3 users have a strong will to support public goods that benefit them, and the way to do so is through donations.

## Pain Points

Nowadays, most donations are done by transferring money directly to an address, but this way of donating faces the following problems. For example:

1. Not secure enough. The wallet of the project side is often a secure wallet, with different addresses on different chains, or only supports a specific few chains, so it is easy for donors to choose the wrong network, and users also need to carry out complex cross-chain operations to ensure that the donation is delivered.

2. Not convenient enough. Donor recipients need to put a lot of effort into designing donation components or pages.

3. Lack of interaction and proof. In a regular donation, only one transfer record is generated on the chain, and it is difficult for outsiders to distinguish from the thousands of transactions that the transaction is actually a donation, expressing someone's recognition of some public good.

4. High cost. A typical donation product in web2, buymeacoffee, usually costs around 5$ for a single donation, but a donation of around 2$ in gas is made on layer1.

## Our Solution

Donate3 solves the above problems with the following Features:

1. Accept multi-chain donations. In the product, we differentiate between two types of addresses to accept donations: EOA and Safe Account, if the user chooses EOA, it means that the recipient's address is the same in different chains, and the donor can donate to the same chain in different chains. If users choose Safe Account, it means that the donor's address is different in different chains. Users can configure different addresses. This ensures that donations are safely deposited into the account.

2. Simple Configuration. Donate3 provides a perfect and simple configuration page, which takes only 5 min for donors to customize the donation components and pages in an aesthetically pleasing and easy-to-access way. Donate components can be quickly integrated into front-end projects. The donation page can provide an informative page for donors to know more about the recipients and thus be more willing to donate.

3. EAS-based Attestation With Data Statistics. We designed a Donate schema, users donate through Donate3, our smart contract will create an EAS([Ethereum Attestation Service](https://attest.sh/)) certificate for the donor at the same time, recording the donor's address, donation currency, amount and other information. This is a certificate of honor for the donor and a basis for the recipient to express their gratitude. Donate3 also keeps statistics on donations based on EAS and events, so that giving and receiving can be seen at a glance.

4. Low cost & Easy Use. Donate3's contract is also deployed on Linea Network to encourage users to use Linea to save cost. At the same time Donate3 integrates Metamask SDK to make donation behavior unhindered.

Donate3 hopes to build a more prosperous web3 world by linking public goods builders and users in the web3 world through the simple act of donation.

# Future Plans

1. Update Contract: Support Donation of ERC20 token.
2. Marketing Promotion: Find real users to use our products to create a Donate3 ecosystem.
3. EIP Standard Application. Donate3 is a opensource project, and we hope to formulate donation standards to help the prosperous ecology of public goods.
4. Financing: We expect that public goods will become the largest network traffic entrance of web3, and Donate3 hopes to link the public goods ecology and seek certain commercial value from it.

# Tech Stack

1. Website

- Frame: nextjs
- Wallet Interact: wagmi
- Wallet connect: metamask sdk
- UI coponent:mui
- User config data storage: img3, IPFS

2. Backend:

- Frame: nestjs
- ORM: prisma
- Web3 API:Infura

3. SDK: React Native

4. contract:

- Frame: hardhat
- RPC: infura

# Step to run Locally

```bash
# install all git submodule
git submodule update --init --recursive
```

Backend:

```bash
cd ./backend
cp .env.example .env

# fill DATABASE_URL=postgresql://xxxx@localhost:5432/donate3
# fill INFURA_APIKEY=***************************

yarn install
yarn prisma
yarn start:dev
# wait 5 minutes to async data
```

Website:

```bash
cd ../
cd ./website
cp .env.example .env

yarn install
yarn build
yarn start
```

Now you can try all feature of Donate3.
You can also try run SDK:

```bash
cd ../
cd sdk
yarn install
yarn run dev
```

If you want to deploy your own contract:

```bash
cd ../
cd caontract

cp .env.example .env
# fill the api key and scan key
yarn install

npx hardhat run scripts/deploy.ts --network {YOUR_NETWORK}
npx hardhat verify {DEPLOYED_ADDRESS} --network {YOUR_NETWORK} ETH

```

# Demo Link

https://www.donate3.xyz/

# 3-minute Pitch Video

https://youtu.be/dCRKt1hYGWs
