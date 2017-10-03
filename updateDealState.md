## <a name="updateDealState"></a> updateDealState 

Process a chatmsg 
### Data format

**createChatmsg:**

```
/**
 * @request
 * Represents the updateDealState request
 * @param {string} itemId - The name of the msg sender
 * @param {string} operation - The image of the msg sender
 * @param {string} signedtx - The description of the chatmessage
 */

{
	itemId: <String>,
	operation: <String>,
	signedtx: <String>,
}

```

**Returns:**

```
/**
 * Represents the chatmsg response
 * @response
 * @param {number} response - The HTTP response code
 * @param {string} txhash - The txhash / receipt
 */
 
{ 
	response: <Number>,
	txhash: <String>  
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



