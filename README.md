# DASH Documentation
The following pages document the research and discovery performed by William Merfalen. Resources are linked where possible. Code is referenced using Github.

# Author
William  Merfalen

# Block
- One or more transactions prefaced by a Block Header. 
- Blocks are protected by Proof of Work

# Block Header
- An 80-byte header prefacing the rest of a Block.
- Belongs to a single Block.
- Hashed repeatedly to create a Proof of Work
- The previous Block’s hash is stored in each Block header
  - No previous Block can be changed without also changing this Block’s header

# Block Version
- The version field in a Block Header indicates what validation rules to use

# Block Height
- The distance between a block and the genesis block (block 0)

# Blockchain
- A chain of blocks, with each block tied to the block preceding it. 
- Provides protection against modification of previous transactions
- Is a public ledger
- Each full Node stores a copy of the blockchain
  - Is validated by that Node
  - When several nodes have the same blocks in their blockchain, they are considered to be In consensus

Consensus
When nodes have the same best blockchain, they are said to be in consensus
There are Consensus Rules
Validation rules that Nodes must follow to stay in consensus

Merkle Trees
A Merkle Tree (or Hash Tree) is a special type of data structure where each leaf is the cryptographic hash of a data block
The branches are labeled with a cryptographic hash of it’s child nodes
This makes it a good example of a “Cryptographic Commitment Scheme”

Coinbase
The first transaction in a block must be a coinbase transaction

Transactions
Allow users to spend duffs
The input of one transaction is the output of a previous transaction
A transaction may have multiple outputs
Such as sending to multiple addresses
UTXO: Unspent Transaction Output
For a payment to be valid, it must only use UTXO’s as inputs. For obvious reasons
Spent transaction output
The opposite of a UTXO. 
If outputs exceed inputs, transaction will be rejected
If inputs exceed outputs, the difference may be claimed as a transaction fee by the miner who created the block containing that transaction


TXIDs (Transaction Identifiers)
The hash of a signed transaction
A sha256d hash of a transaction

Outputs
Contain two fields
1) A value
Amount of Duffs to send
2) A pubkey script
The conditions that must be passed in order for the duffs to be spent
Outputs serve as inputs to subsequent transactions
Outputs are tied to TXIDs

Duffs
One DASH is equal to 100,000,000 Duffs



