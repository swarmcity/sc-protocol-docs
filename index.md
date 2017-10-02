# Swarm City base layer protocol spec 1.0

## Index
[Connection](#connecting)

- onconnect
- ondisconnect

User info
### <a name="head1234"></a>A Heading in this SO entry!
- [userbalances]()

Hashtag

- gethashtaglist
- gethashtagdetail
- createhashtag

Deal

- getdeallist
- getdealdetail
- createdeal

Chat

- messages subscribe
- messages unsubscribe

## [create an anchor](#anchors-in-markdown)

## Notes

### <a name="frontend"></a>Front-end

* boardwalk functionality will not be needed anymore when you have a storefront for a particular hashtag. So as long as a hashtag does not specify a storefront, it uses a boardwalk interface. Once it does, the boardwalk functionality does not apply anymore.

### <a name="solidity"></a>Contract Solidity
* a hashtag should have a datafield specifying which storesront it should use

## Node 

### <a name="connecting"></a>Connecting

Connect your websocket client to ```https://node.swarm.city```

Upon connecting , the server will emit a connected event 

emit: connected  
```
{
    socketid:'7d98f7g9d8f7g98d',
    serverversion: '0.0.1'
}
```

### Disconnect

When the server disconnects the socket it will emit a disconnect
emit: disConnected  
```
{
    socketid:'7d98f7g9d8f7g98d'
}
```

### Requests
on: **present**
function: getAccountInfo
```
{socketid: '7d98f7g9d8f7g98d',
 pubkey: '0x087vb9c7vc97b9c7b9cv7b9c7b',
 timeDate: 02343242342}
```

on: **getHashtagInfo**
emit **hashtagInfo**
```
{
    rep:
       { 
         '0x2222222': {
             name:'Pioneer', 
             balance: 20,
             deals: 30
         },
         '0x3333333': {
             name:'Need A Ride', 
             balance: 42,
             deals: 35
        }
       }
    SWT: 123,
    ETH: 456
}
```

on getRequests
```
{
 hashtag: 0x00,
 time : {
     start: <unix timestamp>
     end: <unix timestamp>
 },
 range : {
     start: <number>
     end: <number>
 },
 includePending: <boolean>,
 includeMyDeals: <true>
}

```
emits requestList
```
{
    myrequests: {
        initiated: [
            {
                id: <UUID>,
                description: <string>
                sf_data: {}
            }
    
        ]
        replied: [],
    },
    mydeals: {
        initiated: []
        replied: []            
    },
    mycompleteddeals: {
        initiated: []
        replied: []            
    },
    alldeals: []
    
}
```



* The goal is to show hashtags to the user they are most interested in and expose new hashtags they might be interested in.
* If we fail to provide a hashtag that is interesting we risk loosing the user.
* A user could be directed to create a hashtag if they cant find one they like and would stop the user abandoning the app
* Is distance and time the most relevent to discovery of a hashtag that interests the user?
* Would attaching the time the deal was made to each of the geohashes offer any advantage?
* The user maybe interested in a hashtag that has not had a deal done close their location and was last used 12 months ago.
* Can this scale with more hashtags and more requests, on a mobile?
* We cant do this on the node as we may not have the users geohash
* Searching for a hashtag may retun no results too often initially
* Categorisation of the hashtags may initially work and would allow us to guide the kind of hashtags we want users to make



## Client 
on 'connected'
emit: 'present'

```
{
    socketid: '7d98f7g9d8f7g98d',
    pubkey: '0x087vb9c7vc97b9c7b9cv7b9c7b'
}
```



## What If's
* client sends fake pub key??












***
***





## SHH topics
SHH topics are an array of topics - that can be combined to filter out relevant messages for your app. You can create a SHH filter to only capture the messages that are relevant for you.

```
[ 
    'swarmcity-v1'                 // version of the protocol
    'dealfortwo-request-create'    // type of message
    '<UUID>'                       // unique ID of message
    'u'                            // geohash order 1
    'sr'                           // geohash order 2
    'sr2'                          // geohash order 3
    'sr2y'                         // geohash order 4
]    
```




## makeDealForTwo
SHH payload : 

```
{
	type: 'dealfortwo-request-create'
	version: 1
	id: <REQUESTID>
	metadata: <IPFSHASH>
	signer: <pubkey>
	signature: <sig>
}
```
IPFS payload :

```
{
    version: 1
    type: 'deal'
    id: <REQUESTID>
    seeker: {
      username: self.identity.username,
      pubkey: self.identity.pubkey,
      avatarhash: self.identity.avatarhash,
    },
    offer: self.offermsg,
    offerhashtag: self.hashtagaddress,
    offertime: offerTime,
    offeramount: amount,
    offercreationtx: txhash,
    offercreationallowancetx: extratx.allowancetx,
}
```



## reply to a request

SHH payload: 
```
{
    type: 'dealfortwo-request-reply',
	version: 1
	id: <REPLYID>,
	requestid: <REQUESTID>,
	metadata: <IPFSHASH>,
	signer: <pubkey>
	signature: <sig>
}
```
IPFS payload

```
{
	type: 'reply'
	version: 1
	id: <REPLYID>,
	requestid: <REQUESTID>,
	hashtag: this.itemdata.hashtag,
	replyer: {
		avatarhash: this.identity.avatarhash,
		username: this.identity.username,
		pubkey: this.identity.pubkey
	},
	reply: this.replytext,
	replyamount: amount,
	replytime: Date.now()
}
```

## choose provider

SHH payload
```
{
    type: 'dealfortwo-select-provider',
    version: 1
    requestid: self.item.id,
    replyid: self.reply.id,
    metadata: <IPFSHASH>
    signer: <pubkey>
    signature: <sig>
}
```

METADATA

```
{
    // no metadata here yet
}
```

## deal funding

SSH payload

```
{
    type : "dealfortwo-provider-funding"
    id: "<offerid>"
    metadata: <IPFSHASH>
    signer: <pubkey>
    signature: <sig>
}
```

IPFS payload

```
{
    offerproviderfundingallowancetx : "<txid>"
    offerproviderfundingtx : "<txid>"
}
```

## Deal payout

TODO

## Deal conflict

TODO

## Deal resolve

TODO

