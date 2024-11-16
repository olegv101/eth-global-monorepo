# eth-global-monorepo
'Monorepo' for ease of submission, original repo's linked below.

--------------------------------

## Getting Started with the TEE (Backend)
First install and run docker desktop, make sure it is the most up to date version 4.35+ (it may error if not)

Create the .env with the private key
`cp .env.example .env`

Run the TEE Attestation Simulator:

```bash
docker run --rm -p 8090:8090 phalanetwork/tappd-simulator:latest
```

Next, download the dependencies with `yarn`

```shell
yarn
```

Build the docker image
```shell
docker build -t your-dapp:latest .
```

After the build is successful, run your docker image to connect to the TEE Attestation Simulator
> NOTE: Your docker image hash will be different than the one listed below.
```shell
docker run --rm -p 3000:3000 your-dapp:latest
```

To make sure everything works
- Go to http://localhost:3000/
- Grab a tweet id from twitter, ie `1582121408548651009` from https://x.com/ParadigmEng420/status/1582121408548651009
- Enter it hit sign transaction
- check the logs of docker, it should give some accurate tweet view count, ignore the rest
- it should look something like this:
https://app.warp.dev/block/pPDCeaUu2Efx454vIOxYSq

--------------------------------
## All Linked Repos

- Frontend UI: (https://github.com/olegv101/eth-bangkok-gtm) - npm i && npm run dev
- Backend: (https://github.com/olegv101/eth-bangkok-gtm-tee) - tee
- Smart Contracts: (https://github.com/olegv101/eth-bangkok-oleg-contracts) - solidity smart contracts
