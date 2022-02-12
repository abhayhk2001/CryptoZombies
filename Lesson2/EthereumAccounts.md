# Ethereu Accounts and Interacting with them
## Ethereum Accounts

The Ethereum blockchain is made up of accounts, which is like bank accounts. An account has a balance of Ether, and you can send and receive Ether payments to other accounts. Each account has an address,which is a unique identifier that points to that account.

There are two datatypes to deal with Addresses in the Solidity:
1. _address_
2. _mapping_

Address keyword holds a __ bit hexvalue.

Mapping is similar to Python dictionary that it holds a ke value pair and is declared as:
```
mapping (<key_datatype> => <value_datatype>) <var_name>;
```

## _msg.sender_ Global Variable

Solidity provides access to certain global variables that are activated when the smart contract is executed by blockchain. _msg.sender_, is a global variable, which refers to the address of the person (or smart contract) who called the current function.

Using _msg.sender_ gives you the security of the Ethereum blockchain — the only way someone can modify someone else's data would be to steal the private key associated with their Ethereum address. 

## _require_ function

It is a error handling function, provided by Solidity to raise an error when the condition given to it is not true. 

```
require(<condition>)
```

# Inheritance of Contracts

Inheritance in smart contracts is used both for splitting a lon contract into modules or for actual object orientation.

In allows the inheriting class to get access to all public and protected data members and member functions of the super class.

```
contract HelloWorldChild is HelloWorldSuper {

}
```

## Importing code from a different Solidity file
```
import "<path>/file.sol";
```

