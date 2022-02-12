# Storage, Visibility and Interface

## Storage vs Memory - Data Storage Location in Smart Contracts

**Storage** refers to variables stored permanently on the blockchain. **Memory** variables are temporary, and are erased between external function calls to your contract.

State variables (variables declared outside of functions) are by default storage and written permanently to the blockchain, while variables declared inside functions are memory and will be cleared when the function call ends.

Creating a new variable of the same type, making it storage and equating it to a state variable will make it a pointer to the state variable. Doing the same thing but making the local varible memory creates a copy of the state variable.

## Function Visibility
### Internal and External 
Solidity has two more types of visibility for functions: internal and external.

Internal is the same as private, except that it's also accessible to contracts that inherit from this contract.

External is similar to public, except that these functions can only be called outside the contract.

For declaring internal or external functions, the syntax is the same as private and public.

## Interacting with other contracts
For our contract to talk to another contract on the blockchain swe need to define an interface.

This is like defining a contract, with a few differences. We're only declaring the functions we want to interact with. The function definition of that function is not defined only a _;_ is added to end of function first line.

So it kind of looks like a contract skeleton. This is how the compiler knows it's an interface.

```
contract NumberInterface {
  function getNum(address _myAddress) public view returns (uint);
}
```

## Using the Interface
```
address NumberInterfaceAddress = 0xab38... 
NumberInterface numberContract = NumberInterface(NumberInterfaceAddress);
```
The address of the user is entered and then numberContract points to that contract on the blockchain.

## Obtaining values for function returning multiple Values
There are two ways:
1. When all the values are needed.
   ```
   (a, b, c) = multipleReturns();
   ```
2. When only some values are needed.
   ```
   (, b, c) = multipleReturns();
   ```