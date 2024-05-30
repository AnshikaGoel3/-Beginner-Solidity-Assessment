# Create a Token
In this Project, we are simply creating a token

## Description
We  will start by creating a contract that have the following:
1. Public variables to store Token Name, Token Abbreviation, Total Supply
2. Mapping of addresses to balances
3. A function to mint the tokens
4. A function to burn the tokens(both these functions have parameters address and value)
5. The burn function should also have a if statement to ensure that the value to be burned is smaller than or equal to the account's balance.

## Getting Started
### Executing Program
To execute this project we have used Remix IDE (https://remix.ethereum.org/)
1. Firstly create a new file and name it using .sol extension since the language used is Solidity.
2.  now code this:
   ```javascript
// SPDX-License-Identifier: MIT
pragma solidity ^0.8.18;

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
    string public token_name = "ABC";
    string public token_abbreviation = "MTA";
    uint public total_supply = 0;

    // mapping variable here
    mapping(address => uint) public balances;

    // mint function
    function mint(address add, uint value) public {
        total_supply += value;
        balances[add] += value;
    }
    // burn function
    function burn(address add, uint value) public {
        if(balances[add] >= value) {
        total_supply -= value;
        balances[add] -= value;
        }
    }

}
```
4. In this code we have completed all the requirements of the project.
5. To test it:
   firstly, compile the code and then deploy it, after that call functios and check if it working properly.
   To do this we have compile and deploy options on the left sidebar of the IDE.
   
