# Getting Started

Make sure to install foundry: https://book.getfoundry.sh/getting-started/installation.
Then, build the project:

```bash
forge build
```

## Testing

To start testing, create a `Contract.t.sol` file in the `test` folder and write your tests.
Then, run the tests:

```bash
forge test
forge coverage
```

## Local Deployment

Start a local network:

```bash
anvil
```

Deploy the contract using the local network fork on http://localhost:8545:

```bash
forge script script/<file>.s.sol:<contract> --fork-url anvil --broadcast --private-key <anvil-private-key>
```

## Deployment

To deploy, create a new wallet keystore:

```bash
cast wallet import --interactive
# or
cast wallet new
```

Then, deploy the contract:

```bash
forge script script/<file>.s.sol:<script> --rpc-url base-sepolia --account <cast-account> --sender <address> --verify --verifier blockscout --verifier-url 'https://base-sepolia.blockscout.com/api/' --broadcast
```
