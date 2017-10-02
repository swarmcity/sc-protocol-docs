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
## <a name="connected"></a>Connected
Connecting to socket.io, listen to event "connected"

Returns:

```
{ 
	version: <String>
}
```

---
## <a name="userbalance"></a>UserBalance

Subscribe:

```
{
	channel: 'UserBalance',
	args: {
		pubkey: <String>
	}
}
```

Returns:

```
{ 
	success: <Boolean>,
	balance: <Number>,
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

**onBalanceChanged**

```
{
	pubkey: <String>,
	balance: <Number>
}
```


---

## <a name="getHashtagList"></a>getHashtagList

Returns the list of hashtags interesting for the user, based on geolocation.

Call:

```
{
	geohash: <String>,
	// Time range?	
}
```

Returns:

```
{ 
	'0x...': {
		name:'Pioneer', 
		balance: 20,
		deals: 30
	},
	'0x...': {
		name:'NeedARide', 
		balance: 20,
		deals: 30
	},
	'0x...': {
		name:'NeedToShop', 
		balance: 20,
		deals: 30
	}
}
```

---

## <a name="getDealList"></a>getDealList

Call:

```
{
	args: {
		filter: {
			user: <String>,
			hashtag: <String>,
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
	'0x...': {
		Data
	},
	'0x...': {
		Data
	},
	'0x...': {
		Data
	}
}
```
---

## <a name="Deals"></a>Deals

Subscribe:

```
{
	channel: 'Deals',
	args: {
		filter: {
			user: <String>,
			dealfilter: <Array> // an array of dealIDs, default "all"
			hashtag: <String>,
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

**onDealUpdated**

```
{
	key: DealID
	data: {dealData}
}
```

---
