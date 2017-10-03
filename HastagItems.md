## <a name="HashtagItems"></a>HashtagItems

Returns the list of items in a specific hashtag.

### Data format

**Subscribe:**

```
/**
 * Represents the hashtags request
 * @param {string} channel - the channel to subscribe to: 'hashtagitems'
 * @request
 */

{
	channel: <String>,
	contractAddress: <String>
}

```


**Returns:**

```
/**
 * Represents the hashtagsItems response
 * @response
 * @param {number} response - The HTTP response code
 * @param {string} subscriptionId - String generated on server
 * @param {array} itemsData - an array of OnHashtagItemsSubscribe objects
 * @param {string} hashtagName - the name of the hashtag contract
 * @param {object} hashtagData - the meta data of the hashtag contract
 * @param {string} hashtagDescription - The description of the hashtag
 * @param {number} hashtagItems - The number of hashtag items / deals on chain
 * @param {string} hastagMaintainer - The public key of the hashtag maintainer
 * @param {string} hastagContact - Array with contact information
 * @param {string} contactName - The name of the contact ('Twitter')
 * @param {string} contactLink - The link to the contact info ('https://twitter.com/NeedARideSupport')
 */
 
{ 
	response: <Number>,   
	subscriptionId: <String>,
	hashtagData: {
		hashtagMaintainer: <String>,
		hashtagName: <String>,
		hashtagDescription: <String>,
		hashtagItems: <Number>,
		hashtagContact: [
			{
				contactName: <String>,
				contactLink: <String>
			},
			{
				contactName: <String>,
				contactLink: <String>
			},
			...
		]
	},
	itemsData: 
	[ 
	itemId: <String> {
		name: <String>, 
		avatar: <String>,
		balance: <String>,
		description: <String>,
		dateTime: <String>,
		location: <String>,
		value: <String>
	},
	itemId: <String> {
		name: <String>, 
		avatar: <String>,
		balance: <String>,
		description: <String>,
		dateTime: <String>,
		location: <String>,
		value: <String>
	},
	itemId: <String> {
		name: <String>, 
		avatar: <String>,
		balance: <String>,
		description: <String>,
		dateTime: <String>,
		location: <String>,
		value: <String>
	}
   ...
]
}
```

hashtagItemsSubscribe will be exectued

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


**hashtagsItemsSubscribe**


 {
                    DealID: '1317d4c60a2fc3f1d586d2ca9d66b52f80a013c9',
                },
                
                
                

```
/**
 * Represents the list of hashtagsitems
 * @response {array}
 * @param {number} response - The HTTP response code
 * @param {string} itemId - The id of the request
 * @param {string} name - The name of the requester 
 * @param {string} avatar - The avatar of the requester (base64)
 * @param {string} balance - The reputation balance for the hashtag of the requester
 * @param {string} description - The textual string describing the request
 * @param {string} dateTime - The time and date the request was made
 * @param {string} location - The geohash where the request was posted
 * @param {string} value - The value in SWT (smallest denomination)
 */
[ 
	itemId: <String> {
		name: <String>, 
		avatar: <String>,
		balance: <String>,
		description: <String>,
		dateTime: <String>,
		location: <String>,
		value: <String>
	},
	itemId: <String> {
		name: <String>, 
		avatar: <String>,
		balance: <String>,
		description: <String>,
		dateTime: <String>,
		location: <String>,
		value: <String>
	}
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



