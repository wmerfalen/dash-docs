


# WIF
Wallet Import Format
- Private key
- Base 58
  - Removing characters that are similar-looking
  - Base X - encoding scheme

- Version of coin
- Compression byte
- private key
- checksum

- 0xcc prefix

private end


# Address
- 0x4c prefix
- Pubkey hash
  - sha256 of public key
  - then run ripemd160 on it
- Payment address
- Pay addr
- x value prefixed with either `02` or `03`
  - if Y value is even or odd 

public end

testnet
- 0xef (priv)
- 0x8c (pub)



# HD Key
- lossless keys
- Hierarchical deterministic (sp?)
- based on seed
  - recovery phrase
  - 

# Recovery phrase
- uses custom encoding
  - Base2048
    - made by bitcoin
    - all recovery phrases based on list of 2048 words

## zoomonic
- 12 word phrase
- recovery phrase

## catmonic
- looks random
- is a test fixture


# PBKDF2
- Turn recovery phrase into seed
- seed 256 bits
- phrase 128 bits


# HD Wallet seed
- take seed
- recursively processed
## Example
```
  m/44'/5'/0'0
```
- if has an apostrophe, means it's a hardened path
- the `44` means it's `BIP44`
- the `5` corresponds to DASH
- the `0` is the account (or wallet)
  - or "contact"
  - Account is always zero
  - hardened value
- only has 4 components
- XKey path
  - is what you would share with someone else
  - final component
    - is "usage"
    - final component is always zero: `/5'/0'/0` (last zero)
    - use case for making it 1
      - for a change address
- Would give the XPub to someone
  - if you wanted to be paid
- Would not the XPrv to anyone
  - if you wanted to share account
    - only reason to give that person your XPrv
      - (private XKey)
      - (private eXtended Key)
# HD XKey Path
  - An account or contact
  - can generate 31 bits worth of addresses
  - path is either hardened or public
    - apostrophe means hardened
  - bip 44
    - it is hardened until it is public
  - 1 remaining component which is the address index

# HD Path
https://github.com/dashhive/DashHD.js#hd-x-key
https://github.com/dashhive/dash-tools#glossary
- describes a schema (or path) to an address
- which seed are you using?
- what path to that address?
  - you can think of it like a user name
- You can increment the address index
  - this will allow you to pay to another address for the same user's XPub
- other person only knows the depth
- wallet is depth zero
- bip 44 - depth 1
- coin key - depth 2
- acct key - depth 3
- xkey - depth 4
- pmt address - depth 5

- HD Key path is index
  - auto-increment

loop:
- take the seed
- use the index
- generate the salt
- loop

- it's deterministic
  - each hash depends on the previous hash

- you would give someone your XPub
  
- root
  - `m`
  - always an `m`
- coin key
  - `5`
    - DASH
  - `0`
    - testnet
- account
- xkey
  - xprv
  - xpub
    - base 58 check encoding
    - the phrase "xprv" and "xpub" are actually encoded into the key
  - tnet
  - tpub
    - same thing but on testnet
-address key
  - last 2 components are considered to be public
- All use XKey format
- cannot create hardened value from a public xkey
- xpub
  - type of xkey
- public extended key
- private extended key

- root seed
- root chain code
- every other revolution of the algorithm
  - seed refers to the seed of that path
- index 5
  - switch encoding algorithm

# Address key path
- all 5 components after the `m`
- WIF 
  - generated from xprv
  - decodes it
    - runs algorithm
  - address key index
  - produces another x key
  - encode in base 58 check
- generated based on previous depths like any other key path
- you can sign with an xprv
- anyone with an xpub could know if signature was valid

- Take the seed to generate the master key

- local copy of blockchain 
  - used to verify the address you created isn't already taken
