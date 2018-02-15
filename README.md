# blocks-bruh
a simple blockchain(possibly)


Functions:
Node_control
The user must be able to control the node in some way. This is done by setting up a HTTP server.

Block_generate
To generate a block one must know the hash of the previous block and create the rest of the required content (= index, hash, data and timestamp). 
Block data is something that is provided by the end-user.

Block_hash
The block needs to be hashed to keep the integrity of the data. A SHA-256 is taken over the content of the block. 
It should be noted that this hash has nothing to do with “mining”, since there is no Proof Of Work problem to solve.

Block_storage
A in-memory Javascript array is used to store the blockchain.
The first block of the blockchain is always a so-called “genesis-block”, which is hard coded.

Blockstructure
Defines the structure of a block.To keep things as simple as possible i have included only the most necessary: index, timestamp, data, hash and previous hash.

Communication 
In order to establish communication,essential part of a node is to share and sync the blockchain with other nodes. 
The following rules are used to keep the network in sync.
    When a node generates a new block, it broadcasts it to the network
    When a node connects to a new peer it querys for the latest block
    When a node encounters a block that has an index larger than the current known block, it either adds the block the its current chain 
    or querys for the full blockchain.

Longest_chain
Solves conflict ie., There should always be only one explicit set of blocks in the chain at a given time.
In case of conflicts (e.g. two nodes both generate block number 72) we choose the chain that has the longest number of blocks.

Validate_block
At any given time we must be able to validate if a block or a chain of blocks are valid in terms of integrity.This is true especially
when we receive new blocks from other nodes and must decide whether to accept them or not.

Main.js 
To run the entire thing
