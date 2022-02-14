# airdrop2holders
Utility script for Solana to airdrop a specified SPL Token to holders of a Candy Machine collection.

[![Donate](https://img.shields.io/badge/Donate-PayPal-green.svg)](https://www.paypal.com/donate/?hosted_button_id=KVTJPB8Z4DA8G)

## Features
- Automatically retrieve all **current** holders of NFTs from a Candy Machine V1 **or** V2 collection.
- Reduce unnecessary gas fees by skipping transfers to the sender account.
- Specified starting holder in case airdrop fails midway or sender account runs out of funds.
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
**Ensure your Solana CLI config file is setup accordingly to the correct [sending account keypair](https://docs.solana.com/cli/transfer-tokens) and [environment](https://docs.solana.com/cli/choose-a-cluster) before continuing.**

```
python3 airdrop2holders [-h] [-s STARTATHOLDER] [--v2] [-l LIST] candymachineid tokenamount tokenaddress
```
```
Required arguments:
candymachineid        The Candy Machine ID of the collection, the holders of which you want to airdrop to. If using a list instead, enter 'none'.
tokenamount           The number of tokens you want to airdrop to each holder.
tokenaddress          The token address of the token you wish to airdrop.

Optional arguments:
-h, --help            Show this help message and exit
-s, --startatholder STARTATHOLDER
                      The holder number that you want to start the airdrop at (useful if an airdrop fails and must be restarted).
--v2                  Use if your collection uses Candy Machine V2.
-l, --list LIST       Path to JSON file containing a list of wallet addresses - overrides NFT holders lookup
-f, --force FORCE     WARNING: SCRIPT WILL RUN WITHOUT SAFETY INPUTS. Will automatically refresh holders if no list is provided and retry failed transactions until they are successful.
```

**If this project helped you at all, please consider donating to support the development and maintenance of future utilities!**

[![Donate](https://img.shields.io/badge/Donate-PayPal-green.svg)](https://www.paypal.com/donate/?hosted_button_id=KVTJPB8Z4DA8G)
