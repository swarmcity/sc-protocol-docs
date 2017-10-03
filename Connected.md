## <a name="getHashtagList"></a>getHashtagList

Returns the list of hashtags interesting for the user, based on geolocation.

### Data

Call:

```

{
	geohash: <String>,
	// Time range?	
}
```

Returns:

```
/**
 * Represents the list of hashtags
 * @response
 * @param {boolean} success - If the request was successful or not
 * @param {string} contractaddr - The address of the hashtag 
 * @param {string} name - The hashtag name 
 * @param {number} balance - The balance in in wei or smallest erc20 denomination
 * @param {number} children - The number of hashtag children / on chain
 */
{ 
	contractaddr: <String> {
		name: <String>, 
		balance: <Number>,
		children: <Number>
	},
       ...
}
```

### Client
Client implementation

```
sends request to node

function getHashtagList() {
}
``` 

### Worker
Worker implementeation

```
gets hashtags from firebase 
```

- health reporting
- 