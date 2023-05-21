# Tokens_project
Creating a Token in solidity 
# Token.sol

This Solidity project is a simple program that is really basic overview of how a Token works and what are it's basic functions.It basically helps us to develop and test our basic knowledge of solidity programming by using state variables , mappings , functions and coonditional statements .

## Description

This program depicts a contract written in Solidity , a programming language used for developing smart contracts on the Ethereum blockchain .We have used the 0.8.18 version of the language . This program is a basic and minimal representation of the working of tokens in a blockchain . Here we have created our own first token and coded two functions "Mint" and "burn" that are used to control the supply of the token and the balances of the addresses of the users

## Getting Started 

Now we will discuss the structure and functionality of the program .

### State Variables 

We have used three state variables here to define the name , abbreviation and total supply of the token .
```
string public tokenName = "Virat";
string public tokenAbbvr = "Vir";
uint public totalSupply = 0;
```

### Mapping 

A mapping is used which maps from addresses to numbers to store the token balance of the addresses of the users .
```
mapping(address => uint) public balances;
```

### Functions 

"Mint" functions is used to supply the tokens to the blockchain and to the wallet addresses . It takes two parameters an address and a numeric value(should be positive) . The numeric value represents the number of tokens to be added to the total supply and to add the tokens to the specific wallet address .
```
function mint(address _address , uint _value) public {
    totalSupply += _value;
    balances[_address] += _value;
}
```

"Burn" function is used to burn the tokens from the supply chain . It also takes two parameters , address and a numeric value where value is used to deduct the number of tokens from the wallet address .
```
function burn(address _address, uint _value) public {
    if (balances[_address] >= _value){
        totalSupply -= _value;
        balances[_address] -= _value;
    }
}
```
