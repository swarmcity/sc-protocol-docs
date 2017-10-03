## <a name="Hashtags"></a>Hashtags

Returns the list of hashtags.

### Data format

**Subscribe:**

```
/**
 * Represents the hashtags request
 * @param {string} channel - the channel to subscribe to: 'hashtags'
 * @request
 */

{
	channel: <String>
}

```


**Returns:**

```
/**
 * Represents the hashtags response
 * @response
 * @param {number} response - The HTTP response code
 * @param {string} subscriptionId - String generated on server
 * @param {array} data - an array of OnHashtagSubscribe objects
 * @param {string} contractAddress - The address of the hashtag 
 * @param {string} hashtagName - The hashtag name 
 * @param {string} hashtagBalance - The SWR balance in in wei or smallest erc20 denomination
 * @param {number} hashtagItems - The number of hashtag items / deals on chain
 */
 
{ 
	response: <Number>,   
	subscriptionId: <String>,
	data: 
	[ 
		contractAddress: <String> {
			hashtagName: <String>, 
			hashtagBalance: <String>,
			hashtagItems: <Number>
		},
		contractAddress: <String> {
			hashtagName: <String>, 
			hashtagBalance: <String>,
			hashtagItems: <Number>
		},
		contractAddress: <String> {
			hashtagName: <String>, 
			hashtagBalance: <String>,
			hashtagItems: <Number>
		},
	   ...
	]
}
```

OnHashtagSubscribe will be exectued

---

**Unsubscribe:**

```
/**
 * Represents the unsubscribe request
 * @request
 * @param {string} subscriptionId - String generated on server
 */
{ 	
	subscriptionId: <String>
}
```

**Returns:** 

```
/**
 * Represents the hashtags response
 * @response
 * @param {number} response - The HTTP response code
 */
{ 
	response: <Number>
}
```

---

### Events

**hashtagsChanged**

```
/**
 * Represents the list of hashtags
 * @response {array}
 * @param {number} response - The HTTP response code
 * @param {string} contractAddress - The address of the hashtag 
 * @param {string} hashtagName - The hashtag name 
 * @param {string} hashtagBalance - The SWR balance in in wei or smallest erc20 denomination
 * @param {number} hashtagItems - The number of hashtag items / deals on chain
 * @param {string} operation - The operation of the hashtag change (added, removed, updated)
 */
 [
	 {
		 operation: <String>,
		 data: {
			contractAddress: <String> {
				hashtagName: <String>, 
				hashtagBalance: <String>,
				hashtagItems: <Number>
			}
		}
	},
	{
		 operation: <String>,
		 data: {
			contractAddress: <String> {
				hashtagName: <String>, 
				hashtagBalance: <String>,
				hashtagItems: <Number>
			}
		}
	},
	...
]
```


**hashtagsSubscribe**

```
/**
 * Represents the list of hashtags
 * @response {array}
 * @param {number} response - The HTTP response code
 * @param {string} contractAddress - The address of the hashtag 
 * @param {string} hashtagName - The hashtag name 
 * @param {string} hashtagBalance - The SWR balance in in wei or smallest erc20 denomination
 * @param {number} hashtagItems - The number of hashtag items / deals on chain
 */
[ 
	contractAddress: <String> {
		hashtagName: <String>, 
		hashtagBalance: <String>,
		hashtagItems: <Number>
	},
	contractAddress: <String> {
		hashtagName: <String>, 
		hashtagBalance: <String>,
		hashtagItems: <Number>
	},
	contractAddress: <String> {
		hashtagName: <String>, 
		hashtagBalance: <String>,
		hashtagItems: <Number>
	},
   ...
]
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



