# Step to run locally in Donate3-Solana

```bash
# install all git submodule
git submodule update --init --recursive
```

donate3-website-new:

```bash
cd ../
cd ./website
cp .env.example .env

yarn install
yarn build
yarn start
```

Now you can try all feature of Donate3-Solana.
You can also try run SDK:

```bash
cd ../
cd sdk
yarn install
yarn run dev
```

💡 If you want to deploy your own contract:

```bash
cd ../
cd caontract

cp .env.example .env
# fill the api key and scan key
yarn install

npx hardhat run scripts/deploy.ts --network {YOUR_NETWORK}
npx hardhat verify {DEPLOYED_ADDRESS} --network {YOUR_NETWORK} ETH

```
