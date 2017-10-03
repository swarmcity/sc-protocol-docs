## <a name="Chat"></a> Chat

Subscribes to the chatconversation for a specific hashtagitem.

### Data format

**Subscribe:**

```
/**
 * Represents the chat conversation request
 * @param {string} channel - the channel to subscribe to: 'chat'
 * @param {string} itemId - the hashtag item id
 * @param {string} publicKey - the user's public key
 * @param {number} pagination - Start from chatmsg nr. x
 */

{
	channel: <String>,
	itemId: <String>,
	publicKey: <String>
}
```

**Returns:**

```
/**
 * Represents the hashtagsItems response
 * @response 
 * @param {number} response - The HTTP response code
 * @param {string} subscriptionId - String generated on server
 * @param {string} itemId - The id of the message
 * @param {array} itemsData - an array of OnChatSubscribe objects
 * @param {string} name - The name of the msg sender
 * @param {string} avatar - The image of the msg sender
 * @param {string} message - The description of the chatmessage
 * @param {string} file - The title of the chatmessage
 * @param {string} dateTime - The timestamp for this chatmessage
 * @param {boolean} read - Read / unread status for this chatmessage
 * @param {string} partnerKey - the public key of your chat partner

 */
 
{ 
	response: <Number>,   
	subscriptionId: <String>,
	partnerKey: <String>,
	itemsData: [{
		itemId: <String>,
		title: <String>,
		description: <String>,
		avatar: <String>,
		name: <String>,
		link: <String>,
		dateTime: <String>
		read: <Boolean>	
		},
		{
		itemId: <String>,
		title: <String>,
		description: <String>,
		avatar: <String>,
		name: <String>,
		link: <String>,
		dateTime: <String>
		read: <Boolean>
		},
		{
		itemId: <String>,
		title: <String>,
		description: <String>,
		avatar: <String>,
		name: <String>,
		link: <String>,
		dateTime: <String>
		read: <Boolean>	
		}
		...
]
}
```

chatSubscribe will be exectued

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
 * Represents the notifications response
 * @response
 * @param {number} response - The HTTP response code
 */
{ 
	response: <Number>
}
```

---

### Events

**chatChanged**

```
/**
 * Represents the list of chatmsgs
 * @response {object}
 * @param {number} response - The HTTP response code
 * @param {string} itemId - The id of the msg
 * @param {string} description - The description of the notification
 * @param {string} title - The title of the notification
 * @param {string} link - The link / route for this notification
 * @param {string} dateTime - The timestamp for this notification
 * @param {boolean} read - Read / unread status for this notification
 * @param {string} operation - The operation of the hashtag change (added, removed, updated)
 */
 {
	 operation: <String>,
	 data: {
		itemId: <String>,
	 	title: <String>,
		description: <String>,
		avatar: <String>,
		name: <String>,
		link: <String>,
		dateTime: <String>
		read: <Boolean>	
	}
}
```

**chatSubscribe**

```
/**
 * Represents the list of chatmsgs
 * @response {array} 
 * @param {number} response - The HTTP response code
 * @param {string} operation - The id of the chatmsg
 * @param {string} itemData - The data of the chatmsg
 * @param {string} itemId - The id of the chatmsg
 * @param {string} name - The name of the msg sender
 * @param {string} avatar - The image of the msg sender
 * @param {string} message - The description of the chatmessage
 * @param {string} file - The title of the chatmessage
 * @param {string} dateTime - The timestamp for this chatmessage
 * @param {boolean} read - Read / unread status for this chatmessage
 */
[{
		itemId: <String>,
		title: <String>,
		description: <String>,
		avatar: <String>,
		name: <String>,
		file: <String>,
		link: <String>,
		dateTime: <String>
		read: <Boolean>
		},
		itemId: <String>,
		title: <String>,
		description: <String>,
		avatar: <String>,
		name: <String>,
		file: <String>,
		link: <String>,
		dateTime: <String>
		read: <Boolean>
		},
		itemId: <String>,
		title: <String>,
		description: <String>,
		avatar: <String>,
		name: <String>,
		file: <String>,
		link: <String>,
		dateTime: <String>
		read: <Boolean>
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

- will only respond with 100 msgs / most recent msg last
subscribe to topic / get blocks in / ...

```



