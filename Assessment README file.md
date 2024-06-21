ETH PROOF: Beginner EVM Course Assessment

The ETH PROOF: Beginner EVM Course by Metacrafters is a detailed introduction to Web3.0 and Solidity, the language for creating smart contracts on the Ethereum blockchain. The course teaches key ideas about decentralized applications, blockchain technology, and the Ethereum Virtual Machine (EVM). Through practical exercises and projects, participants learn how to create, deploy, and use smart contracts. The goal is to provide beginners with the basic skills needed to understand and contribute to the growing Web3 world.
Description
The final test for the ETH PROOF: Beginner EVM Course requires creating a Solidity smart contract that works like a basic cryptocurrency token. This test checks how well you understand and can use the key Solidity concepts taught in the course. Here are the tasks you need to complete for the assessment:
Requirements
Public Variables: Create public variables to store the token details: Token Name, Token Abbreviation, and Total Supply.
Address Balances Mapping: Implement a mapping to track the balances of addresses (address => uint).
Mint Function: Develop a mint function that accepts an address and a value. This function increases the total supply by the given value and credits the specified address with the same amount.
Burn Function: Create a burn function that takes an address and a value. This function decreases the total supply by the specified value and deducts the same amount from the address's balance.
Conditional Checks in Burn Function: Ensure the burn function includes conditionals to check that the sender's balance is sufficient to burn the requested amount of tokens.
Getting Started
Installing
We used Remix IDE to compile and run our code.

Executing Program
To execute our program, you need to copy the code and paste it into Remix. After pasting it, you need to hit the Compile Button and compile the code. Next, we will deploy and run transactions.

How to Run the Program
To execute our program, you need to copy the code and paste it into Remix. After pasting it, you need to hit the Compile Button and compile the code. Next, we will deploy and run transactions.

Author
Lavisha

Contact Information
Lavisha: lavishab.0096@gmail.com

License
This project is licensed under the Metacrafters.

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
    string public tokenName = "SizzlinShine";
    string public tokenAbbrv = "SS";
    uint public totalSupply = 0;

    // mapping variable here
    mapping(address => uint) public balances;

    // mint function
    function mint (address _address, uint _value)public {
        totalSupply += _value;
        balances[_address] += _value;
    }
    // burn function
    function burn (address _address, uint _value) public {
        if(balances[_address] >= _value){
        totalSupply -= _value;
        balances[_address] -= _value;
        }
    }
}
