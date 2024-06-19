# MyToken Solidity Smart Contract


This Solidity program is a basic smart contract called My Token which is used for creating and managing tokens. It has some basic functions like mint
and burn which is used to create,add and burn custom cryptocurrency tokens.

## DESCRIPTION:
This program is a simple contract written in Solidity, for developing smart contracts which creates custom tokens. The contract defines a smart contract named Mytoken with public variables Tokenname, Tokenabbreviation, and total supply. It allows for minting and burning of tokens, and maintains a balance mapping for addresses. This contract serves as foundation for creating and managing tokens using mint and burn function.

## STEPS:
### 1.Navigate the Remix Compiler, create a new file by clicking on the "+" icon in the left-hand sidebar. Save the file with a .sol extension 

### 2.Execute the below code in it:

### CODE:

// SPDX-License-Identifier: MIT
pragma solidity 0.8.18;

/*
       REQUIREMENTS
    1. Your contract will have public variables that store the details about your coin (Token Name, Token Abbrv., Total Supply)
    2. Your contract will have a mapping of addresses to balances (address => uint)
    3. You will have a mint function that takes two parameters: an address and a value. 
       The function then increases the total supply by that number and increases the balance 
       of the “sender” address by that amount
    4. Your contract will have a burn function, which works the opposite of the mint function, as it will destroy tokens. 
       It will take an address and value just like the mint functions. It will then deduct the value from the total supply 
       and from the balance of the “sender”.
    5. Lastly, your burn function should have conditionals to make sure the balance of "sender" is greater than or equal 
       to the amount that is supposed to be burned.
*/

contract MyToken {

    // public variables here
    string public TokenName = "PARTH";
    string public tokenAbbrv = "PAR";
    uint public totalSupply = 0;

    // mapping variable here
    mapping(address => uint) public balances;

    // mint function
    function mint(address _address, uint _value) public {
        totalSupply += _value;
        balances[_address] += _value;
    }

    // burn function
    function burn(address _address, uint _value) public {
        if (balances[_address] >= _value) {
            totalSupply -= _value;
            balances[_address] -= _value;
        }
    }
}

### 3.Compile and Deploy:
Click on the "Solidity Compiler" tab in the left-hand sidebar.

Once the code is compiled, click on the "Deploy & Run Transactions" tab in the left-hand sidebar.

### 4.Interact with the Contract:

Once the contract is deployed, you can interact with it by calling the mint and burn functions.

To mint tokens, call the mint function with the desired address and value.
Example: mint(0xYourAddress, 100);

To burn tokens, call the burn function with the desired address and value, ensuring the address has a sufficient balance.
Example: burn(0xYourAddress, 50);

## Author
PARTH MEHTA










