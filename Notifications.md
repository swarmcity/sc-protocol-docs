## <a name="Notifications"></a> Notifications

Subscribes to the list of notifications for a specific user.

### Data format

**Subscribe:**

```
/**
 * Represents the notifications request
 * @param {string} channel - the channel to subscribe to: 'notifications'
 * @param {string} deviceId - the user's UUID per device
 * @param {string} publicKey - the user's public key
 */

{
	channel: <String>,
	deviceId: <String>,
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
 * @param {string} itemId - The id of the notification
 * @param {array} itemsData - an array of OnNotificationsSubscribe objects
 * @param {string} description - The description of the notification
 * @param {string} title - The title of the notification
 * @param {string} link - The link / route for this notification
 * @param {number} dateTime - The unix epoch for this notification
 * @param {boolean} read - Read / unread status for this notification
 */
 
{ 
	response: <Number>,   
	subscriptionId: <String>,
	itemsData: [{
		itemId: <String>,
		title: <String>,
		description: <String>,
		link: <String>,
		dateTime: <Number>
		read: <Boolean>
		},
		{
		itemId: <String>,
		title: <String>,
		description: <String>,
		link: <String>,
		dateTime: <Number>
		read: <Boolean>
		},
		{
		itemId: <String>,
		title: <String>,
		description: <String>,
		link: <String>,
		dateTime: <Number>
		read: <Boolean>
		},
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

**notificationChanged**

```
/**
 * Represents the list of hashtags
 * @response {array}
 * @param {number} response - The HTTP response code
 * @param {string} itemId - The id of the notification
 * @param {string} description - The description of the notification
 * @param {string} title - The title of the notification
 * @param {string} link - The link / route for this notification
 * @param {string} dateTime - The timestamp for this notification
 * @param {boolean} read - Read / unread status for this notification
 * @param {string} operation - The operation of the hashtag change (added, removed, updated)
 */
 [
	 {
		 operation: <String>,
		 data: {
		 	itemId: <String>,
			title: <String>,
			description: <String>,
			link: <String>,
			dateTime: <String>
			read: <Boolean>		
		}
	},
	{
		 operation: <String>,
		 data: {
		 	itemId: <String>,
			title: <String>,
			description: <String>,
			link: <String>,
			dateTime: <String>
			read: <Boolean>		
		}
	},
	...
]
```


**notificationsSubscribe**

```
/**
 * Represents the list of hashtagsitems
 * @response {array}
 * @param {number} response - The HTTP response code
 * @param {string} itemId - The id of the notification
 * @param {string} description - The description of the notification
 * @param {string} title - The title of the notification
 * @param {string} link - The link / route for this notification
 * @param {string} dateTime - The timestamp for this notification
 * @param {boolean} read - Read / unread status for this notification
 */
[{
		title: <String>,
		description: <String>,
		link: <String>,
		dateTime: <String>
		read: <Boolean>
		},
		{
		title: <String>,
		description: <String>,
		link: <String>,
		dateTime: <String>
		read: <Boolean>
		},
		{
		title: <String>,
		description: <String>,
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
subscribe to topic / get blocks in / ...

```



