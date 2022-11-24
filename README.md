# airdrop2holders
Utility script for Solana to efficiently airdrop a specified SPL Token to holders of a Candy Machine collection.

[![Donate](https://img.shields.io/badge/Donate-PayPal-green.svg)](https://www.paypal.com/donate/?hosted_button_id=KVTJPB8Z4DA8G)

## Features
- Automatically retrieve all **current** holders of NFTs from a Candy Machine V1 **or** V2 collection.
- Save on time and unnecessary gas fees by skipping transfers to the sender wallet and bundling transfers to holders who own multiple NFTs in the collection.
- Specify a list of wallets to airdrop to users other than a Metaplex collection
- Specify starting holder in case airdrop fails midway or sender wallet runs out of funds during airdrop.
- Automatically retry failed transactions (no more monitoring airdrops for errors).
- Blacklist wallets to prevent unwanted airdrops

## Dependencies
### [Python3](https://www.python.org/downloads/)
### [Solana CLI](https://docs.solana.com/cli/install-solana-cli-tools)
#### Installation
```
sh -c "$(curl -sSfL https://release.solana.com/stable/install)"
```
### [Metaboss](https://github.com/samuelvanderwaal/metaboss)
#### Installation
```
cargo install metaboss --locked
```
## Usage
**Ensure your Solana CLI config file is setup accordingly to the correct [sending wallet keypair](https://docs.solana.com/cli/transfer-tokens) and [environment](https://docs.solana.com/cli/choose-a-cluster) before continuing.**

```
python3 airdrop2holders [-h] [-s STARTATHOLDER] [--v2] [-l LIST] [-b BLACKLIST] [-f] candymachineid tokenamount tokenaddress
```
```
Required arguments:
candymachineid        The Candy Machine ID of the collection, the holders of which you want to airdrop to. If using a list instead, enter 'none'.
tokenamount           The number of tokens you want to airdrop to each holder.
tokenaddress          The token address of the token you wish to airdrop.

Optional arguments:
-h, --help            Show this help message and exit
-s, --startatholder STARTATHOLDER
                      The holder number that you want to start the airdrop at (useful if an airdrop fails midway and must be restarted).
--v2                  Use if your collection uses Candy Machine V2.
-l, --list LIST       Path to JSON file containing a list of wallet addresses - overrides NFT holders lookup
-b BLACKLIST, --blacklist BLACKLIST
                      Path to JSON file containing a blacklist of wallet addresses you do not wish to drop to
-f, --force FORCE     WARNING: SCRIPT WILL RUN WITHOUT SAFETY INPUTS. Will automatically refresh holders if no list is provided and retry failed transactions until they are successful.
```

### Example of list or blacklist JSON files
```
["wallet1", "wallet2", "wallet3"]
```
**Save with .json extension**

## Contact
**Twitter:** [@jonahjnewton](https://twitter.com/jonahjnewton)

**Email:** [jonah@jonahnewton.com.au](jonah@jonahnewton.com.au)

**Discord:** jjonahlowercase#4804


---
**If this script helped you at all, please consider donating to support the development and maintenance of future utilities!**

[![Donate](https://img.shields.io/badge/Donate-PayPal-green.svg)](https://www.paypal.com/donate/?hosted_button_id=KVTJPB8Z4DA8G)
