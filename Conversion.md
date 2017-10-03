## <a name="Conversion"></a>Conversion

Get conversion value  

### Data format

**getConversion:**

```
/**
 * Represents the conversion request
 * @param {string} fromTokenSymbol - the symbol of the erc20 token
 * @param {string} toTokenSymbol - the symbol of the erc20 token
 * @param {string} fromValue - the value of the erc20 token to be converted
 * @request
 */

{
	fromTokenSymbol: <String>, // 'SWT'
	fromValue: <String>,       // '0x'
	toTokenSymbol: <String>   //  'USD'
}

```

**Returns:**

```
/**
 * Represents the conversion response
 * @response
 * @param {number} response - The HTTP response code
 * @param {string} value - the value of the conversion rate
 * @param {number} validTillBlock - the conversion rate is valid till block number
 */
 
{ 
	response: <Number>,   
	value: <Number>,
	validTillBlock: <Number>
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



