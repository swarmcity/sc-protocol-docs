## <a name="Hashtags"></a>Hashtags

Returns the list of hashtags interesting for the user, based on geolocation.

### Data format

**Subscribe:**

```
/**
 * Represents the hashtags request
 * @request
 * @param {boolean} success - If the request was successful or not
 */


{
	channel: 'hashtags'
}

```


**Returns:**

```
{ 
	success: <Boolean>,
	subscription: <String>
}
```

---

**Unsubscribe:**

```
{ 	
	subscription: <String>
}
```

**Returns:** 

```
{ 
	success: <Boolean>,
	subscription: <String>
}
```

---

### Events

**onHashtagChanged**

```
/**
 * Represents the list of hashtags
 * @response
 * @param {boolean} success - If the request was successful or not
 * @param {string} contractAddress - The address of the hashtag 
 * @param {string} hashtagName - The hashtag name 
 * @param {string} hashtagBalance - The SWR balance in in wei or smallest erc20 denomination
 * @param {number} children - The number of hashtag children / on chain
 */
{ 
	contractAddress: <String> {
		hashtagName: <String>, 
		hashtagBalance: <String>,
		children: <Number>
	},
       ...
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
```



