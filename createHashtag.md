## <a name="createHashtag"></a> createHashtag

Create a new hashtag 
### Data format

**createHashtag:**

```
/**
 * Represents the createHashtag request
 * @request
 * @param {number} response - The HTTP response code
 * @param {string} hashtagName - the name of the hashtag contract
 * @param {string} hashtagDescription - The description of the hashtag
 * @param {string} hastagMaintainer - The public key of the hashtag maintainer
 * @param {string} hastagContact - Array with contact information
 * @param {string} contactName - The name of the contact ('Twitter')
 * @param {string} contactLink - The link to the contact info ('https://twitter.com/NeedARideSupport') 
 */

{
		hashtagName: <String>,
		hashtagDescription: <String>,
		hashtagMaintainer: <String>,
		hashtagContact: [
			{
				contactName: <String>,
				contactLink: <String>
			},
			{
				contactName: <String>,
				contactLink: <String>
			},

}

```

**Returns:**

```
/**
 * Represents the processtx response
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



