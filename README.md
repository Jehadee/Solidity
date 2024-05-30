MyToken Contract
Overview
The MyToken contract is a simple ERC-20 token implementation on the Ethereum blockchain. It allows for the creation, minting, and burning of tokens.

Variables
tokenName: The name of the token.
tokenAbbrv: The abbreviation of the token.
totalSupply: The total supply of tokens.
balanceOf: A mapping of addresses to their corresponding token balances.
Constructor
The constructor initializes the token with a given name, abbreviation, and total supply. It also sets the initial balance of the contract creator to the total supply.

Functions
mint
mint(address _to, uint256 _value): Mints _value tokens to the address _to. The function checks if the sender has sufficient balance before minting.
burn
burn(address _from, uint256 _value): Burns _value tokens from the address _from. The function checks if the sender has sufficient balance before burning.
License
This contract is licensed under the MIT License.

Version
Solidity version: 0.8.18
