# Swarm City Protocol
#### Version 0.0.1

## Index

#### Connection
- [Connected](#connected)

#### Subscriptions
- [UserBalance](#userbalance)
- [Deals](#Deals)

#### Calls

- [getHashtagList](#getHashtagList)
- [getDealList](#getDealList)

---
STRUCT

/**
 * Represents a users balance
 * @response
 * @param {boolean} success - If the request was successful or not
 * @param {number} balance - The balance in in wei or smallest erc20 denomination
 * @param {string} subscription - The socket id
 */
{ 
    success: <Boolean>, 
    balance: <Number>,  
    subscription: <String> 
}


---

## <a name="getUserRep"></a>getUserRep

Call:

```
{
	pubkey: <String>		// 0x...	
}
```

Returns:

```
{ 
	'0x...': {
		SWR: <String>, 	// 'NeedARide'
		Balance: <Number>  // smallest denomination (1e18)
	},
	'0x...': {
		SWR: <String>, 	// 'NeedToShop'
		Balance: <Number>  // smallest denomination (1e18)
	},
	'0x...': {
		SWR: <String>, 	// 'SwarmBnB'
		Balance: <Number>  // smallest denomination (1e18)
	}
}
```

---

## <a name="Hashtags"></a>Hashtags

Subscribe:

```
{
	channel: 'Hashtags',
	args: {
		filter: {
			user: <String>,
			hashtagfilter: <Array> // an array of hashtags, default "all"
			geolocation: <String>,
			timerange: { 
				from: <DateTime>, 
				to: <DateTime> 
			}
		}
	}
}
```

Returns:

```
{ 
	success: <Boolean>,
	subscription: <String>
}
```


Unsubscribe:

```
{ 	
	subscription: <String>
}
```

Returns:

```
{ 
	success: <Boolean>
}
```

Events: 

**onHashtagUpdated**

```
{
	key: DealID
	data: {hashtagData}
}
```

---



---
