# Network Resolvers 

## List all Resolvers

You may list collection of Network Resolvers using this action. Default per page is 20.

```shell
curl --include \
'http://www.dnsvault.net/api/v1/nodes/1/network/resolvers'
```

> The above command returns JSON structured like this:

```json
[
    {
        "id": 1,
        "content": "1.1.1.1",
        "typ": "ipv4",
        "category": "nameserver",
        "created_at": "2018-02-20T02:32:55.799Z",
        "updated_at": "2018-02-20T02:32:55.799Z"
    },
    {
        "id": 2,
        "content": "1.1.1.100",
        "typ": "ipv4",
        "category": "nameserver",
        "created_at": "2018-02-20T02:34:57.982Z",
        "updated_at": "2018-02-20T02:34:57.982Z"
    }
]
```

This endpoint retrieves all Network Resolvers.

### HTTP Request

`GET http://www.dnsvault.net/api/v1/nodes/:node_id/network/resolvers`

## Create Network Resolvers

You may create a Network Resolvers using this action. It takes a JSON object containing a parameters.

```shell
curl --include \
     --request POST \
     --header "Content-Type: application/json" \
     --data-binary "{
    \"typ\": \"ipv4\",
    \"content\": \"1.1.1.1\"
}" \
'http://www.dnsvault.net/api/v1/nodes/1/network/resolvers'
```

> The above command returns JSON structured like this:

```json
{
    "id": 3,
    "node_id": 26,
    "content": "1.1.1.1",
    "category": "nameserver",
    "typ": "ipv4",
    "position": null,
    "created_at": "2018-02-20T02:39:58.253Z",
    "updated_at": "2018-02-20T02:39:58.253Z"
}
```

This endpoint creates an Network Resolvers

### HTTP Request

`POST http://www.dnsvault.net/api/v1/nodes/:node_id/network/resolvers`

## Show Network Resolvers

You may list collection of Network Resolvers using this action. Default per page is 20.

```shell
curl --include \
'http://www.dnsvault.net/api/v1/nodes/1/network/resolvers/3'
```

> The above command returns JSON structured like this:

```json
{
    "id": 3,
    "node_id": 26,
    "content": "1.1.1.1",
    "category": "nameserver",
    "typ": "ipv4",
    "position": null,
    "created_at": "2018-02-20T02:39:58.253Z",
    "updated_at": "2018-02-20T02:39:58.253Z"
}
```

This endpoint retrieves an Network Resolvers.

### HTTP Request

`GET http://www.dnsvault.net/api/v1/nodes/:node_id/network/resolvers/:id`

## Update Network Resolvers

```shell
curl --include \
     --request PUT \
     --header "Content-Type: application/json" \
     --data-binary "{
    \"route\": {
        \"typ\": \"ipv4\",
        \"content\": \"1.1.1.2\"
    }
}" \
  'http://www.dnsvault.net/api/v1/nodes/1/network/resolvers/3'
```


> The above command returns JSON structured like this:

```json
{
    "id": 3,
    "node_id": 26,
    "content": "1.1.1.2",
    "category": "nameserver",
    "typ": "ipv4",
    "position": null,
    "created_at": "2018-02-20T02:39:58.253Z",
    "updated_at": "2018-02-20T02:39:58.253Z"
}
```

This endpoint update a Network Resolvers.

### HTTP Request

`PUT http://www.dnsvault.net/api/v1/nodes/:node_id/network/resolvers/:interface_id/aliases/:id`

## Delete Network Resolvers

```shell
curl --include \
     --request DELETE \
     --header "Authorization: Token iwwTXK54aahsosrx5JK7hkTe" \
  'http://www.dnsvault.net/api/v1/nodes/1/network/resolvers/2'
```


> The above command returns JSON structured like this:

```json
{
    "id": 3,
    "node_id": 26,
    "content": "1.1.1.2",
    "category": "nameserver",
    "typ": "ipv4",
    "position": null,
    "created_at": "2018-02-20T02:39:58.253Z",
    "updated_at": "2018-02-20T02:39:58.253Z"
}
```

This endpoint delete a Network Resolvers.

### HTTP Request

`DELETE http://www.dnsvault.net/api/v1/nodes/:node_id/network/resolvers/:id`