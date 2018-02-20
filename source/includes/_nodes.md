# Nodes

## Get All Nodes


```shell
curl --include \
     --header "Authorization: Token iwwTXK54aahsosrx5JK7hkTe" \
  'http://www.dnsvault.net/api/v1/nodes'
```

> The above command returns JSON structured like this:

```json
[
    {
        {
            "id": 5,
            "node_name": "elastic2.dnsvault.net",
            "description": null,
            "created_at": "2016-06-22T16:10:10.602Z",
            "updated_at": "2016-06-22T16:10:10.602Z",
            "tag": "agent",
            "fingerprint": "64:9E:06:F0:0C:AB:0F:63:2B:0D:DC:C6:E2:DF:BE:33:8F:69:3C:A0:99:D8:1F:65:76:AE:EA:DA:C6:64:12:3F",
            "fingerprint_algorithm": "SHA256"
        }
    }
]
```

This endpoint retrieves all nodes.

### HTTP Request

`GET http://www.dnsvault.net/api/v1/nodes`

### URL Parameters

Parameter | Description
--------- | -----------
Id | The ID of the node to retrieve

## Get a Node


```shell
curl --include \
     --header "Authorization: Token iwwTXK54aahsosrx5JK7hkTe" \
  'http://www.dnsvault.net/api/v1/nodes/2'
```


> The above command returns JSON structured like this:

```json
{
  "id": 2,
  "node_name": "elastic2.dnsvault.net",
  "description": null,
  "created_at": "2016-06-22T16:10:10.602Z",
  "updated_at": "2016-06-22T16:10:10.602Z",
  "tag": "agent",
  "fingerprint": "64:9E:06:F0:0C:AB:0F:63:2B:0D:DC:C6:E2:DF:BE:33:8F:69:3C:A0:99:D8:1F:65:76:AE:EA:DA:C6:64:12:3F",
  "fingerprint_algorithm": "SHA256"
}
```

This endpoint retrieves a node.

### HTTP Request

`GET http://www.dnsvault.net/api/v1/nodes/:id`

### URL Parameters

Parameter | Description
--------- | -----------
Id | The ID of the node to retrieve

## Delete a Node
```shell
curl --include \
     --header "Authorization: Token iwwTXK54aahsosrx5JK7hkTe" \
     --request DELETE \
  'http://www.dnsvault.net/api/v1/nodes/2'
```


> The above command returns JSON structured like this:

```json
{
  "success": {
    "7005": "Node has been deleted"
  }
}
```

This endpoint delete a node.

### HTTP Request

`DELETE http://www.dnsvault.net/api/v1/nodes/:id`

### URL Parameters

Parameter | Description
--------- | -----------
Id | The ID of the node to delete

## List all Certs

```shell
curl --include \
     --header "Authorization: Token iwwTXK54aahsosrx5JK7hkTe" \
  'http://www.dnsvault.net/api/v1/nodes/certificates'
```


> The above command returns JSON structured like this:

```json
[
  {
    "status": "+",
    "node": "elastic3.dnsvault.net",
    "algorithm": "(SHA256)",
    "hash": "BB:52:BC:9B:EF:3F:19:40:D0:C4:21:7E:F2:F7:5F:9B:80:06:33:5D:86:CB:DB:3C:D7:7D:50:38:ED:E1:51:4B"
  },
  {
    "status": "+",
    "node": "test01.me.my",
    "algorithm": "(SHA256)",
    "hash": "EA:0D:3B:D8:B3:15:D1:91:5E:D5:4E:C3:FE:6A:C6:D8:41:C4:E9:11:60:33:4D:DE:40:AF:2D:72:05:D0:A8:0D"
  }
]
```

This endpoint get list of certificates.

### HTTP Request

`GET http://www.dnsvault.net/api/v1/nodes/certificates`

## List all Nodes Requests

```shell
curl --include \
     --header "Authorization: Token iwwTXK54aahsosrx5JK7hkTe" \
  'http://www.dnsvault.net/api/v1/nodes/node_request'
```


> The above command returns JSON structured like this:

```json
[
  {
    "status": "?",
    "name": "elastic2.dnsvault.net",
    "algorithm": "(SHA256)",
    "fingerprint": "B8:FD:D2:8F:33:B1:FF:AC:5F:60:0A:DA:70:66:09:87:EA:B7:4C:14:8D:0F:4F:B0:67:60:69:83:9E:48:78:15"
  }
]
```

This endpoint get list of node request.

### HTTP Request

`GET http://www.dnsvault.net/api/v1/nodes/node_request`

## Accept Node Request

```shell
curl --include \
     --request PUT \
     --header "Content-Type: application/json" \
     --header "Authorization: Token iwwTXK54aahsosrx5JK7hkTe" \
     --data-binary "{
    \"node_name\": \"elastic2.dnsvault.net\"
}" \
  'http://www.dnsvault.net/api/v1/nodes/accept'
```


> The above command returns JSON structured like this:

```json
[
  {
    "status": "?",
    "name": "elastic2.dnsvault.net",
    "algorithm": "(SHA256)",
    "fingerprint": "B8:FD:D2:8F:33:B1:FF:AC:5F:60:0A:DA:70:66:09:87:EA:B7:4C:14:8D:0F:4F:B0:67:60:69:83:9E:48:78:15"
  }
]
```

This endpoint get list of node request.

### HTTP Request

`PUT http://www.dnsvault.net/api/v1/nodes/accept`


## Reject Node Request

```shell
curl --include \
     --request PUT \
     --header "Content-Type: application/json" \
     --header "Authorization: Token iwwTXK54aahsosrx5JK7hkTe" \
     --data-binary "{
    \"node_name\": \"elastic2.dnsvault.net\"
}" \
  'http://www.dnsvault.net/api/v1/nodes/reject'
```

> The above command returns JSON structured like this:

```json
[
  {
    "status": "?",
    "name": "elastic2.dnsvault.net",
    "algorithm": "(SHA256)",
    "fingerprint": "B8:FD:D2:8F:33:B1:FF:AC:5F:60:0A:DA:70:66:09:87:EA:B7:4C:14:8D:0F:4F:B0:67:60:69:83:9E:48:78:15"
  }
]
```

This endpoint get list of node request.

### HTTP Request

`PUT http://www.dnsvault.net/api/v1/nodes/reject`
