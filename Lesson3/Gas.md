# Gas

## Gas — the fuel Ethereum DApps run on
In Solidity, your users have to pay every time they execute a function on your DApp using a currency called gas. Users buy gas with Ether (the currency on Ethereum), so your users have to spend ETH in order to execute functions on your DApp.

How much gas is required to execute a function depends on how complex that function's logic is. Because running functions costs real money for your users, code optimization is much more important in Ethereum than in other programming languages. 

### Necessity of Gas
Ethereum is like a big, slow, but extremely secure computer. When you execute a function, every single node on the network needs to run that same function to verify its output — thousands of nodes verifying every function execution is what makes Ethereum decentralized, and its data immutable and censorship-resistant.

## Struct Packing
Normally there's no benefit to using these sub-types because Solidity reserves 256 bits of storage regardless of the uint size. 
But there's an exception to this: inside structs. Using a smaller-sized uint when possible will allow Solidity to pack these variables together to take up less storage. 
We can save space further by clustering similar data types together.

## Solidity TimeUnits
The variable now will return the current unix timestamp of the latest block (the number of seconds that have passed since January 1st 1970).

Solidity also contains the time units seconds, minutes, hours, days, weeks and years. These will convert to a uint of the number of seconds in that length of time. 

```
uint lastUpdated;
lastUpdated = now;
if(lastUpdated > now + 5 minutes)
{
	return(timePassed);
}
```

## View functions don't cost gas
view functions don't cost any gas when they're called externally by a user.

So marking a function with view tells web3.js that it only needs to query your local Ethereum node to run the function, and it doesn't actually have to create a transaction on the blockchain (which would need to be run on every single node, and cost gas).

If a view function is called internally from another function in the same contract that is not a view function, it will still cost gas. This is because the other function creates a transaction on Ethereum, and will still need to be verified from every node. 


## Storage is Expensive

One of the more expensive operations in Solidity is using storage — particularly writes.

This is because every time you write or change a piece of data, it’s written permanently to the blockchain. 

Declaring array in memory. Length should be specified.
```
uint[] memory values = new uint[](3);
```