# Auction Smart Contract

A Leo-based smart contract implementation of a decentralized auction system on Aleo.

## Overview

This smart contract enables a trustless auction system where users can place bids, and an auctioneer can determine and finalize the winning bid. Built using Leo, Aleo's programming language for zero-knowledge applications.

## Features

- 🔒 **Secure Bidding**: Users can submit encrypted bids
- 🏆 **Winner Resolution**: Automated highest bid selection
- ✅ **Auction Finalization**: Transparent winner confirmation
- 🔐 **Privacy Preserved**: Zero-knowledge proofs ensure bid privacy

## Prerequisites

- Leo Programming Language
- Aleo Development Environment

## Installation

1. Install Leo:
```bash
curl -sSf https://leo-lang.org/install.sh | sh
```

2. Create new auction project:
```bash
leo new auction
cd auction
```

## Contract Structure

### Bid Record
The contract uses a `Bid` record with the following fields:
- `owner`: Address of the bid owner
- `bidder`: Address of the bidding user
- `amount`: Bid amount
- `is_winner`: Winner status flag

## Usage

### Place a Bid
```bash
leo execute place_bid <bidder_address> <amount>
```

### Resolve Highest Bid
```bash
leo execute resolve "{ owner: <auctioneer_address>, 
                      bidder: <bidder1_address>, 
                      amount: <amount1>, 
                      is_winner: false }" \
                    "{ owner: <auctioneer_address>, 
                      bidder: <bidder2_address>, 
                      amount: <amount2>, 
                      is_winner: false }"
```

### Finalize Auction
```bash
leo execute finish "{ owner: <auctioneer_address>, 
                     bidder: <winner_address>, 
                     amount: <winning_amount>, 
                     is_winner: false }"
```

## Deployment

Deploy to Aleo Testnet:
```bash
leo deploy
```

## Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Author

**Ibrahim**  
*Last Updated: March 2025*

---

🌟 For more information about Leo and Aleo, visit [leo-lang.org](https://leo-lang.org)