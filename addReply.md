## <a name="addReply"></a> addReply

Add a reply to an item 
### Data format

**createHashtag:**

```
/**
 * Represents the createHashtag request
 * @request
 * @param {number} response - The HTTP response code
 * @param {string} itemId - The id of the request
 * @param {string} name - The name of the replyer 
 * @param {string} avatar - The avatar of the replyer (base64)
 * @param {string} description - The textual string describing the reply
 * @param {string} location - The geohash where the request was posted
 * @param {string} value - The value in SWT (smallest denomination) */

{
	itemId: <String>,
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
 * Represents the addReply response
 * @response
 * @param {number} response - The HTTP response code
 */
 
{ 
	response: <Number>,   
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



