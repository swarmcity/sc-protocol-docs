## <a name="getHashtagList"></a>getHashtagList

Returns the list of hashtags interesting for the user, based on geolocation.

Call:

```
/**
 * Represents the hashtags request
 * @request
 * @param {boolean} success - If the request was successful or not
 * @param {string} geohash - The user's geolocation. When not available, return worldwide
 */
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


