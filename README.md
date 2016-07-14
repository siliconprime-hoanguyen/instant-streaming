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
POST /instantstream/request
```


#### Body

```javascript
none
```

### Start stream 

```javascript
POST /instantstream/start/:token //the token is returned by calling the above request api
```

#### Body

```javascript
{
"role":['viewer', 'dealer'] //who start the stream? optional, default is viewer
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


## Socket

### Authentication for Pusher service URL (called by Pusher SDK)

```javascript
POST /socket/auth
```

#### Body

```javascript
{
"socket_id":"xxx",
"channel_name":"xxxx"
}
```

