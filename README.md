# Token 

## Overview

The `CustomToken` contract is a simple ERC-20 token implementation on the Ethereum blockchain. It extends the functionality of the OpenZeppelin ERC20, ERC20Burnable, and Ownable contracts. The token supports standard ERC-20 features such as transfers, approvals, and burns, along with additional functionalities for minting tokens, burning tokens, and sending tokens with an associated message.

## Smart Contract Details

### Contract Name

`CustomToken`

### Solidity Version

The contract is implemented in Solidity version ^0.8.17.

### License

The smart contract is licensed under the MIT License.

```solidity
// SPDX-License-Identifier: MIT
```

## Contract Features

1. **Token Creation:**
   - The contract is designed to create a new ERC-20 token with a specified name, symbol, initial supply, and initial owner.

2. **Token Minting:**
   - The owner of the contract can mint additional tokens and assign them to a specified address.

   ```solidity
   function mintTokens(address legatee, uint256 totalSum) external onlyOwner
   ```

3. **Token Burning:**
   - Token holders can burn a certain amount of their own tokens.

   ```solidity
   function burnTokens(uint256 totalSum) external
   ```

4. **Token Transfer:**
   - The contract supports the standard ERC-20 transfer functionality.

   ```solidity
   function transfer(address legatee, uint256 totalSum) public virtual override returns (bool)
   ```

5. **Send Tokens with Message:**
   - Users can send tokens to a recipient along with an associated message.

   ```solidity
   function sendTokensWithMessage(address recipient, uint256 amount, string memory message) external returns (bool)
   ```

   An event `TokensSentWithMessage` is emitted when tokens are sent with a message.

   ```solidity
   event TokensSentWithMessage(address indexed sender, address indexed recipient, uint256 amount, string message);
   ```

## Getting Started

1. **Installation:**
   - Ensure you have the necessary Solidity compiler version (^0.8.17) installed.

2. **Deployment:**
   - Deploy the `CustomToken` contract to the Ethereum blockchain, specifying the token name, symbol, initial supply, and initial owner.

3. **Interacting with the Contract:**
   - Utilize the provided functions such as `mintTokens`, `burnTokens`, `transfer`, and `sendTokensWithMessage` to manage the token.

## Examples

### Token Deployment

```solidity
CustomToken myToken = new CustomToken("MyToken", "MTK", 1000000, msg.sender);
```

### Minting Tokens

```solidity
myToken.mintTokens(addressToMint, 50000);
```

### Burning Tokens

```solidity
myToken.burnTokens(20000);
```

### Transferring Tokens

```solidity
myToken.transfer(anotherAddress, 1000);
```

### Sending Tokens with Message

```solidity
myToken.sendTokensWithMessage(receiverAddress, 500, "Thanks for your support!");
```

## License

This smart contract is licensed under the MIT License. See the [LICENSE](./LICENSE) file for details.


