## <a name="balance"></a>Balance

Subscribe:

```
/**
 * Represents a users balance request
 * @request
 * @param {number} response - The HTTP response code
 * @param {array} tokens - An array of tokens
 * @param {string} tokenContractAddress - A token address (0x...)
 * @param {string} pubkey - A public key (0x...)
 */
{
	channel: 'balance',
	args: {
		pubkey: pubkey <String>,
		tokens: [ tokenContractAddress <String>, {tokenContractAddress <String>,..]
	}
}
```

Returns:

```
/**
 * Represents a users balance
 * @response
 * @param {number} response - The HTTP response code
 * @param {array} balances - An array of tokens and their balance
 * @param {string} pubkey - A public key (0x...)
 * @param {array} data - an array of balance objects
* @param {string} tokenSymbol - The token's short name
 * @param {string} tokenName - The token's long name ('Swarm City Token', 'NeedARide', 'Ether')
 * @param {string} tokenContractAddress - A token address (0x...)
 * @param {string} balance - in wei or smallest erc20
 * @param {string} subscription - the socket connection id
 */
 {
 	response: <Number>,   
	subscriptionId: <String>,
 	data: [
{
	pubkey: <String>,   // 0x... public key
	tokenContractAddress: <String>,   // 0x... token address
	tokenSymbol: <String>,    // 'SWT', the token short
	tokenName: <String>,    // 'Swarm City Token', the token long
	balance: <String>  // in wei or smallest erc20 denomination
},
{
	pubkey: <String>,   // 0x... public key
	tokenContractAddress: <String>,   // 0x... token address
	tokenSymbol: <String>,    // 'SWT', the token short
	tokenName: <String>,    // 'Swarm City Token', the token long
	balance: <String>  // in wei or smallest erc20 denomination
},
...
]
 }
 

```

Unsubscribe:

```
{ 	
	subscription: <String>   // socketid
}
```

Returns:

```
{ 
 	response: <Number>   
}
```

Events: 

**onBalanceSubscribe**

```
/**
 * Represents a users balance
 * @response
 * @param {number} response - The HTTP response code
 * @param {string} pubkey - A public key (0x...)
 * @param {string} tokenSymbol - The token's short name
 * @param {string} tokenName - The token's long name ('Swarm City Token', 'NeedARide', 'Ether')
 * @param {string} tokenContractAddress - A token address (0x...)
 * @param {string} balance - in wei or smallest erc20
 */
 {
 	response: <Number>,   
	subscriptionId: <String>,
 	data: [
{
	pubkey: <String>,   // 0x... public key
	tokenContractAddress: <String>,   // 0x... token address
	tokenSymbol: <String>,    // 'SWT', the token short
	tokenName: <String>,    // 'Swarm City Token', the token long
	balance: <String>  // in wei or smallest erc20 denomination
},
{
	pubkey: <String>,   // 0x... public key
	tokenContractAddress: <String>,   // 0x... token address
	tokenSymbol: <String>,    // 'SWT', the token short
	tokenName: <String>,    // 'Swarm City Token', the token long
	balance: <String>  // in wei or smallest erc20 denomination
},
...
]
 }
```

---

**onBalanceChanged**

```
/**
 * Represents a users balance
 * @response
 * @param {number} response - The HTTP response code
 * @param {string} pubkey - A public key (0x...)
 * @param {string} tokenSymbol - The token's short name
 * @param {string} tokenName - The token's long name ('Swarm City Token', 'NeedARide', 'Ether')
 * @param {string} tokenContractAddress - A token address (0x...)
 * @param {string} balance - in wei or smallest erc20
 */
{
	pubkey: <String>,   // 0x... public key
	tokenContractAddress: <String>,   // 0x... token address
	tokenSymbol: <String>,    // 'SWT', the token short
	tokenName: <String>,    // 'Swarm City Token', the token long
	balance: <String>  // in wei or smallest erc20 denomination
}
```


---

### Client
```
// Insert Sponnet's unit test function
```

### Worker
```
// Insert Sponnet's unit test function
subscribe to topic / get blocks in / ...

```




