## <a name="Avatar"></a>Avatar

Get / set user avatar 

### Data format

**setAvatar:**

```
/**
 * Represents the hashtags request
 * @param {string} base64 - the base64 expression of the avatar
 * @request
 */

{
	base64: <String>
}

```

**Returns:**

```
/**
 * Represents the hashtagsItems response
 * @response
 * @param {number} response - The HTTP response code
 * @param {string} ipfsHash - The IPFS hash of the base64
 */
 
{ 
	ipfsHash: <String>
}
```

---

**getAvatar:**

```
/**
 * Represents the hashtags request
 * @param {string} ipfsHash - the IPFSHash of the avatar
 * @request
 */

{
	ipfsHasH: <String>
}

```

**Returns:**

```
/**
 * @response
 * @param {number} response - The HTTP response code
 * @param {string} base64 - The BASE64 of the avatar
 */
 
{ 
	base64: <String>
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



