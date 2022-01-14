# Basics Of Solidity

## Creating a Contract

Every solidity program begins with a contract.


A contract is the fundamental building block of Ethereum applications — all variables and functions belong to a contract, and this will be the starting point of all your projects. Solidity is a statically typed programming language and all statements in it end with a ';'. To create a contract in solidity use the keyword - contract.

```
contract HelloWorld {
}
```

## Pragma
To specify which version of the solidity compiler should be used to compile the contract we use the keyword pragma at the beginning of the program file.

```
pragma solidity >=0.5.0 <0.6.0;
```
The above example use the solidity version of [0.5.0,0.6.0).

## State Variables

State variables are permanently stored in contract storage. This means they're written to the Ethereum blockchain. Variables have to be of a certain datatype. It is declared with the variable declaration.

```
<datatype> <variableName> = <value>;
```

Common Datatypes
1. uint
2. int 
3. string
4. structure
5. array


Most commonly used datatypes are uint (unsigned int), which is an alias for uint256 -> unsigned int with 256 bits.


## Mathematical Operators

1. Addition +
2. Subtraction -
3. Multiplication *
4. Division /
5. Modulus %
6. Exponentiation **


## Structure

Structures allow you to create more complicated data types that have multiple properties.

To create a new structure we use the struct keyword. 

```
struct Person {
  uint age;
  string name;
}
```

## Arrays

A set of variables of the same datatype is an array. The are 2 types of arrays in Solidity, Static array with fixed size, and Dynamic array with variable size.
You can also create array of structures.

**Public** arrays cane be read by other contracts but they cannot be written to. 
Syntax:
```
<datatype>[] public <array_name>;
```

## Manipulating Structures and arrays

### Creating new structure object
```
<structure_name>(parameter_val_1,parameter_val_2,...)
```

### Adding elements to Arrays
Using the push method we can add elements to the end of the array.
```
<array_name>.push(<val>)
```
## Functions

Functions are created using the keyword _function_ and arguments to the function can be passed both by value and reference. Passing by reference is direct.
```
function hello(string name){

}
```

But for passing a variable by value we have to add the memory keyword specifying that the variable has to be stored in the memory.
```
function hello(string memory name){

}
```

It is convention for function parameters to have the their names starting with '_'.

A function is made public with the public keyword placed after the function parameters definition.
```
function hello(string name) public {

}
```


### Private and Public functions

Private functions are those that can only be accessed within the contract that defines them. It add a layer of protection from malicious attacks.
By default, the Solidity functions are public. To make functions private, use the _private_ keyword after the function parameter declaration.
```
function hello(string name) private {

}
```

The convention is to name private functions starting with '_'.

### Return Values

To return values from function we use the _returns_ keyword to define the datatype of the returned object.
```
function hello(string name) private returns (string memory){

}
```

## Function Modifiers
To restrict and monitor the working of functions, function modifiers are used.

1. view -> Function is only viewing data and not modifying it.
2. pure -> Function is not accessing data for the state of the app.

The solidity compiler is able to identify if a functions should be considered as view/pure and will notify it.


## Typecasting in Solidity

Similar to Python to typecast a variable to another datatype, we wrap the variable in '()' and place the new datatype before the parenthesis.

```
<datatype>(<var_name>)
```

## Events

**Events** are a way for your contract to communicate that something happened on the blockchain to your app front-end, which can be 'listening' for certain events and take action when they happen.

```
event helloSent(string name);

function helloWorld(string name) public {
  emit hello(name);
}
```

This events trigger functions in the frontend.


## Interacting with Frontend

Using the JS package Web3.js developed by ethereum, smart contracts can interact with frontend applications.
