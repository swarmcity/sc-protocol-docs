## <a name="getHashtagList"></a>getHashtagList

Returns the list of hashtags interesting for the user, based on geolocation.

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