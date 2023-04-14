
# Transactions
It's like an "Email with a value"
- Has a "To:"
- Has a "From:"
- Transactions go inside a Block
- master nodes will aggregate the txn
  - sign a block

## Inputs
- "From:"
- ASN-1 var-int
- number of inputs

## Outputs
- "To:"
- Sig hash type (1)
- Sequence
  - counts down
- Are coins
  - spent coins
  - unspent coins (UTXo's)
- Paying AJ Example:
  1. AJ can come up with an address
    - hash it down to 20 bytes long
      - ripemd160(sha256(pubkey))
  2. Take AJ's addr
    - decode that
    - get the pubkey hash
  3. Output contains
    1. who you're sending it to
    2. Your change address
    3. a ghost output (the network fee)
      - the sum of Inputs minus the sum of outputs
        - = network fee
    - other:
      - base units
      - lock script size
      - script to pay to a public key
        - locking rule
          - describes how the funds can be unlocked
    # BONUS TRIVIA:
      - pay2script
        - smart contract
        - you dont pay to an addr /pubkey hash
        - you pay to a script
        - when smart contract conditions are met, money is released
  4. Locktime
    - the earliest time or block
    - some future block and add that number to the current block height


# Staking
- put money in a place for a specific amount of time

1. look up all transactions which the addr was used
- where the txn has not been referenced as spent
- 

# Coin
1. pmt address
2. tx id
3. index in txn

## Raw txn
- the same as the other txn's
  - but:
    - no signature
    - no script

## Hashable txn
"Ready to sign txn"
- has previous lock script


## Fully signed txn
- gets published
- no lock script
- has signature script


# Blocks
- Have various types of "messages"

# Pubkey scripts
- ASM code
  - interpretter is embedded in MNO's/miners
  - (likely in `util/asmap.cpp`)
