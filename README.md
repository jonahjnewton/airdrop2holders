# airdrop2holders
Utility script to airdrop a specified SPL Token to holders of a Candy Machine collection.

## Features
- Automatically retrieve all **current** holders of NFTs from a Candy Machine V1 **or** V2 collection.
- Reduce unnecessary gas fees by skipping transfers to the same account.
- Specified starting holder in case airdrop fails midway.
- Automatically retry failed transactions (no more monitoring airdrops for errors).

## Requirements
### [Python3](https://www.python.org/downloads/)
### [Solana CLI](https://docs.solana.com/cli/install-solana-cli-tools)
#### Installation
```
sh -c "$(curl -sSfL https://release.solana.com/stable/install)"
```
### [Metaboss](https://github.com/samuelvanderwaal/metaboss)
#### Installation
```
cargo install metaboss
```
## Usage
```
python3 airdrop2holders [-h] [-s STARTATHOLDER] [--v2] candymachineid tokenamount tokenaddress
```
```
  Required arguments:
  candymachineid        The Candy Machine ID for a collection, the holders of which you want to airdrop to.
  tokenamount           The number of tokens you want to airdrop to each holder.
  tokenaddress          The token address of the token you wish to airdrop.
  
  Optional arguments:
  -h, --help            Show this help message and exit
  -s STARTATHOLDER, --startatholder STARTATHOLDER
                        The holder number that you want to start the airdrop at (useful if an airdrop fails and must be restarted).
  --v2                  Use if your collection uses Candy Machine V2.
```
