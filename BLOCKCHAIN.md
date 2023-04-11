# Blockchain fundamentals
A Blockchain is a series of blocks that are each tied to each other. 
The "chain" portion is facilitated by having each block tied to it's
previous block. The way this works is by having a each block also
include the cryptographic hash of the previous block. The hashing
of blocks means that it is very difficult to change a single block
because that would mean changing all following blocks after that.

## Block
- One or more transactions prefaced by a Block Header. 
- Blocks are protected by Proof of Work

## Block Header
- An 80-byte header prefacing the rest of a Block.
- Belongs to a single Block.
- Hashed repeatedly to create a Proof of Work
- The previous Block’s hash is stored in each Block header
  - No previous Block can be changed without also changing this Block’s header

## Block Version
- The version field in a Block Header indicates what validation rules to use

### Why versions matter
- 

## Block Height
- The distance between a block and the genesis block (block 0)

## Blockchain
- A chain of blocks, with each block tied to the block preceding it. 
- Provides protection against modification of previous transactions
- Is a public ledger
- Each full Node stores a copy of the blockchain
  - Is validated by that Node
  - When several nodes have the same blocks in their blockchain, they are considered to be In consensus

### Why it's difficult to change blocks
- A block consists of the previous block's hash, and is thus chained to that block
  - This means that in order to change a block, you'd have to modify the block that records it and all the following blocks

## Consensus
- When nodes have the same best blockchain, they are said to be in consensus
- There are Consensus Rules
  - Validation rules that Nodes must follow to stay in consensus

## Merkle Trees
- A Merkle Tree (or Hash Tree) is a special type of data structure where each leaf is the cryptographic hash of a data block
- The branches are labeled with a cryptographic hash of it’s child nodes
  - This makes it a good example of a “Cryptographic Commitment Scheme”

# Author
William  Merfalen
