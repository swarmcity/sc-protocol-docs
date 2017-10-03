## <a name="balance"></a>Balance

Subscribe:

```
/**
 * Represents a users balance request
 * @request
 * @param {boolean} success - If the request was successful or not
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
 * @param {boolean} success - If the request was successful or not
 * @param {array} balances - An array of tokens and their balance
 * @param {string} pubkey - A public key (0x...)
 * @param {string} tokenSymbol - The token's short name
 * @param {string} tokenName - The token's long name ('Swarm City Token', 'NeedARide', 'Ether')
 * @param {string} tokenContractAddress - A token address (0x...)
 * @param {string} balance - in wei or smallest erc20
 * @param {string} subscription - the socket connection id
 */
{ 
    success: <Boolean>,
    pubkey: <String>, 
    balances: [
    	{ tokenSymbol: <String>, tokenName: <String>, tokenContractAddress: <String>, balance: <String> },
    	{ tokenSymbol: <String>, tokenName: <String>, tokenContractAddress: <String>, balance: <String> },
    	{ tokenSymbol: <String>, tokenName: <String>, tokenContractAddress: <String>, balance: <String> } 
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
	success: <Boolean>  // true or false
}
```

Events: 

**onBalanceChanged**

```
/**
 * Represents a users balance
 * @response
 * @param {boolean} success - If the request was successful or not
 * @param {string} pubkey - A public key (0x...)
 * @param {string} short - tokenSymbol - The token's short name
 * @param {string} long - tokenName - The token's long name ('Swarm City Token', 'NeedARide', 'Ether')
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
