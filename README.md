# DASH Documentation
The following pages document the research and discovery performed by William Merfalen. Resources are linked where possible. Code is referenced using Github.

# Author
William  Merfalen

# What is DASH?
DASH is a type of cryptocurrency that utilizes a P2P network to distribute and manage a public ledger. The code is based on Bitcoin and has been heavily modified. DASH uses what's called [Master Nodes](MASTERNODES.md) and [Full Nodes](FULLNODES.md) to communicate with the network. 

# Blockchain fundamentals
1) [Blockchain Fundamentals](BLOCKCHAIN.md)
2) [

# Coinbase
- The first transaction in a block must be a coinbase transaction

# Transactions
- Allow users to spend duffs
- The input of one transaction is the output of a previous transaction
- A transaction may have multiple outputs
  - Such as sending to multiple addresses
- UTXO: Unspent Transaction Output
  - For a payment to be valid, it must only use UTXO’s as inputs. For obvious reasons
- Spent transaction output
  - The opposite of a UTXO. 
- If outputs exceed inputs, transaction will be rejected
- If inputs exceed outputs, the difference may be claimed as a transaction fee by the miner who created the block containing that transaction


## TXIDs (Transaction Identifiers)
- The hash of a signed transaction
- A sha256d hash of a transaction

## Outputs
- Contain two fields
  1) A value
    - Amount of Duffs to send
  2) A pubkey script
    - The conditions that must be passed in order for the duffs to be spent
- Outputs serve as inputs to subsequent transactions
- Outputs are tied to TXIDs

## Duffs
- One DASH is equal to 100,000,000 Duffs



