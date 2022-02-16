## Immutability
After deploying a contract to Ethereum, it’s immutable, it can never be modified or updated again.

If there's a flaw in your contract code, there's no way for you to patch it later. You would have to tell your users to start using a different smart contract address that has the fix. This is also a feature of smart contracts. The code is law. 

## Making Contracts Ownable
To give owner some special previliges over others we can make contract ownable.

### OpenZeppelin's Ownable contract
OpenZeppelin is a library of secure and community-vetted smart contracts that you can use in your own DApps. 
Easiest method to make a contract ownable inherit the Ownable contract from the OpenZeppelin library  by first copying it in your sol file.

So the Ownable contract basically does the following:

1. When a contract is created, its constructor sets the owner to msg.sender (the person who deployed it)
2. It adds an onlyOwner modifier, which can restrict access to certain functions to only the owner
3. It allows you to transfer the contract to a new owner

**Constructors**: constructor() is a constructor, which is an optional special function that has the same name as the contract. It will get executed only one time, when the contract is first created.
```
constructor() internal {
	_owner = msg.sender;
	emit OwnershipTransferred(address(0), _owner);
}
```

## Function modifiers
Modifiers are kind of half-functions that are used to modify other functions, usually to check some requirements prior to execution.

A function modifier looks just like a function, but uses the keyword *modifier* instead of the keyword *function*. And it can't be called directly like a function can — instead we can attach the modifier's name at the end of a function definition to change that function's behavior.
### Modifier Definition
```
modifier onlyOwner() {
	require(isOwner());
	_;
}
```

### Modifier Calling
It is added to the starting of the function by adding it to the function definition. When control reaches the *_;* in the modifier it jumps back to the calling function.
```
function transferOwnership(address newOwner) public onlyOwner {
    _transferOwnership(newOwner);
}
```
OnlyOwner is the function modifier.