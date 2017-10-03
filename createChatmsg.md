## <a name="createChatmsg"></a> createChatmsg 

Process a chatmsg 
### Data format

**createChatmsg:**

```
/**
 * @request
 * Represents the chatmsg request
 * @param {string} name - The name of the msg sender
 * @param {string} avatar - The image of the msg sender
 * @param {string} message - The description of the chatmessage
 * @param {string} file - The title of the chatmessage
 * @param {string} dateTime - The timestamp for this chatmessage
 * @param {string} partnerKey - the public key of your chat partner
 */

{
	title: <String>,
	description: <String>,
	avatar: <String>,
	name: <String>,
	file: <String>,
	link: <String>,
	dateTime: <String>
	read: <Boolean>
}

```

**Returns:**

```
/**
 * Represents the chatmsg response
 * @response
 * @param {number} response - The HTTP response code
 */
 
{ 
	response: <Number>  
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
will trigger chatChanged()
```



