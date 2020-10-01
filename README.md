# Invoice.build app development
This repo is a high-level repo for setting up the development environment for the [invoice.build](https://invoice.build) app and all it's dependent services.

## Getting started
Clone this repo and move into the newly created directory.
```bash
git clone https://github.com/Invoice-build/app-dev.git invoice-build && cd invoice-build
```

Initiate the submodules and make sure they're up to date.
```bash
git submodule init && git submodule update
```

Set up the api database and seed it with the supported tokens.
```bash
docker-compose run api rails db:setup
```

Add your own environment variables to the api service in docker-compose.yml. You will need to signup to [Etherscan](https://etherscan.io/apis) and [Infura](https://infura.io/) to get your API keys.
```yml
  ETHERSCAN_API_KEY: <your_key_here>
  INFURA_PROJECT_ID: <your_id_here>
  INFURA_PROJECT_SECRET: <your_secret_here>
  JWT_SECRET: <your_secret_here>
```
Optional, a secret for JWT_SECRET can be generated by running `docker-compose run api rake secret`.

Spin up the app.
```bash
docker-compose up
```

Once all the services are finished building, open [http://localhost:3000](http://localhost:3000) in your browser.
