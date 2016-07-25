# New instant streaming apis

## DevAPI: https://apidev21.dropininc.com

## ProdAPI: https://apiprod21.dropininc.com/

## StagAPI: https://apistaging21.dropininc.com/


### API key is required for every call to server, adding the below key/value pair to header

```javascript
{apikey: xxxxx}
```



### Request stream

```javascript
POST /instantstream/request?notify=xxxx
```


#### Body

```javascript
{
  phone: '12312312',
  email: 'abc@xyz.com',
  deviceAddress: 'xxxx', //optional, only mobile needs to provide this
  deviceType: 'android', //or ios, optional, only mobile needs to provide this
  bundleId: 'xxxx', //optional, only mobile needs to provide this
}
```

#### Queries

```javascript
{
 notify: true //whether to notify the dealer about the stream
}
```

### Start stream 

```javascript
POST /instantstream/start/:token //the token is returned by calling the above request api
```

#### Body

```javascript
{
  "role":['viewer', 'dealer'], //who start the stream? optional, default is viewer
  deviceAddress: 'xxxx', //optional, only mobile needs to provide this
  deviceType: 'android', //or ios, optional, only mobile needs to provide this
  bundleId: 'xxxx', //optional, only mobile needs to provide this
}
```


### Cancel stream

```javascript
POST /instantstream/cancel/:token //the token is returned by calling the above request api
```

#### Body

```javascript
{
"role":['viewer', 'dealer'] //who stop the stream, optional, default is viewer
}
```


### Stop stream

```javascript
POST /instantstream/stop/:token //the token is returned by calling the above request api
```


#### Body

```javascript
{
"role":['viewer', 'dealer'] //who stop the stream?
}
```


### Get stream by tokenikd

```javascript
GET /instantstream/get/:token //the token is returned by calling the above request api
```


### Save chat in streaming

```javascript
POST /instantstream/savechat/:token //the token is returned by calling the above request api
```

#### Body

```javascript
{
"role":['viewer', 'dealer'] //who chat in the stream?,
"message": "xxxxx"
}
```


### Get chat in streaming

```javascript
GET /instantstream/getchat/:token //the token is returned by calling the above request api
```



## Socket

### Authentication for Pusher service URL (called by Pusher SDK)

```javascript
POST /notifications/authchannel
```

#### Body

```javascript
{
"socket_id":"xxx",
"channel_name":"xxxx"
}
```

