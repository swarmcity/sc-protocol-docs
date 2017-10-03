## <a name="createItem"></a> createItem

Create a new item on a hashtag 
### Data format

**createItem:**

```
/**
 * Represents the object request for createItem
 * @request 
 * @param {number} response - The HTTP response code
 * @param {string} contractAddress - The address of the hashtag 
* @param {string} name - The name of the requester 
 * @param {string} avatar - The avatar of the requester (base64)
 * @param {string} description - The textual string describing the request
 * @param {string} location - The geohash where the request was posted
 * @param {string} value - The value in SWT (smallest denomination)
 */
{
	contractAddress: <String>,
	name: <String>, 
	avatar: <String>,
	description: <String>,
	location: <String>,
	value: <String>
}

```

**Returns:**

```
/**
 * Represents the response
 * @response
 * @param {number} response - The HTTP response code
 * @param {txhash} the txhash receipt
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



