## <a name="ProcessTX"></a> ProcessTX

Process a signed tx 
### Data format

**processTx:**

```
/**
 * Represents the processtx request
 * @param {string} signedTx - the signed transaction
 * @request
 */

{
	signedTx: <String>, // '0x...'
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
	txhash: <Number>
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



