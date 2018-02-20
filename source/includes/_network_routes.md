# Network Routes (create & update)

## List all Routes

You may list collection of Network Routes using this action. Default per page is 20.

```shell
curl --include \
'http://www.dnsvault.net/api/v1/nodes/1/network/routes'
```

> The above command returns JSON structured like this:

```json
[
    {
        "id": 3,
        "node_id": 26,
        "typ": "ipv6",
        "route_name": "dnsv",
        "ip_address": "12.12.12.11",
        "ipv4_subnetmask": "",
        "ipv6_prefix": "",
        "gateway": "",
        "interface": "",
        "note": "",
        "created_at": "2018-02-13T03:56:30.855Z",
        "updated_at": "2018-02-13T03:56:30.855Z"
    },
    {
        "id": 1,
        "node_id": 26,
        "typ": "ipv4",
        "route_name": "local",
        "ip_address": "12.12.12.11",
        "ipv4_subnetmask": "24",
        "ipv6_prefix": "5",
        "gateway": "192.168.0.1",
        "interface": "a",
        "note": "",
        "created_at": "2018-02-09T05:22:00.273Z",
        "updated_at": "2018-02-13T09:28:46.777Z"
    },
    {
        "id": 2,
        "node_id": 26,
        "typ": "ipv6",
        "route_name": "sub",
        "ip_address": "2001:ABCD:EFGH",
        "ipv4_subnetmask": "",
        "ipv6_prefix": "64",
        "gateway": "2001::1",
        "interface": "etho",
        "note": "",
        "created_at": "2018-02-12T04:14:55.150Z",
        "updated_at": "2018-02-13T09:29:45.475Z"
    }
]
```

This endpoint retrieves all Network Routes.

### HTTP Request

`GET http://www.dnsvault.net/api/v1/nodes/:node_id/network/routes`

#### URL Parameters

Parameter | Description
--------- | -----------
Node_id | The ID of the network route's node to retrieve

## Create Network Routes (required params)

You may create a Network Routes using this action. It takes a JSON object containing a parameters.

```shell
curl --include \
     --request POST \
     --header "Content-Type: application/json" \
     --data-binary "{
    \"typ\": \"ipv4\",
    \"route_name\": \"localdns\",
    \"ip_address\": \"192.168.0.111\",
    \"ipv4_subnetmask\": \"255.255.255.100\",
    \"ipv6_prefix\": \"null\",
    \"getaway\": \"null\",
    \"interface\": \"null\",
    \"note\": \"null\"
}" \
'http://www.dnsvault.net/api/v1/nodes/1/network/routes'
```

> The above command returns JSON structured like this:

```json
{
    "id": 4,
    "node_id": 26,
    "typ": "ipv4",
    "route_name": "localdns",
    "ip_address": "192.168.0.111",
    "ipv4_subnetmask": "255.255.255.100",
    "ipv6_prefix": null,
    "gateway": null,
    "interface": null,
    "note": null,
    "created_at": "2018-02-14T07:39:14.968Z",
    "updated_at": "2018-02-14T07:39:14.968Z"
}
```

This endpoint creates an Network Routes

### HTTP Request

`POST http://www.dnsvault.net/api/v1/nodes/:node_id/network/routes`

#### URL Parameters

Parameter | Description
--------- | -----------
Node_id | The ID of the network route's node to retrieve

## Show Network Routes

You may list collection of Network Routes using this action. Default per page is 20.

```shell
curl --include \
'http://www.dnsvault.net/api/v1/nodes/1/network/routes/4'
```

> The above command returns JSON structured like this:

```json
{
    "id": 4,
    "node_id": 26,
    "typ": "ipv4",
    "route_name": "localdns",
    "ip_address": "192.168.0.111",
    "ipv4_subnetmask": "255.255.255.100",
    "ipv6_prefix": null,
    "gateway": null,
    "interface": null,
    "note": null,
    "created_at": "2018-02-14T07:39:14.968Z",
    "updated_at": "2018-02-14T07:39:14.968Z"
}
```

This endpoint retrieves an Network Routes.

### HTTP Request

`GET http://www.dnsvault.net/api/v1/nodes/:node_id/network/routes/:id`

#### URL Parameters

Parameter | Description
--------- | -----------
Node_id | The ID of the network route's node to retrieve
Id | The ID of the network route to retrieve

## Update Network Routes (required params)

```shell
curl --include \
     --request PUT \
     --header "Content-Type: application/json" \
     --data-binary "{
    \"route\": {
        \"typ\": \"ipv4\",
        \"route_name\": \"localhost\",
        \"ip_address\": \"192.168.0.111\",
        \"ipv4_subnetmask\": \"255.255.255.100\",
        \"ipv6_prefix\": \"null\",
        \"getaway\": \"null\",
        \"interface\": \"null\",
        \"note\": \"update\"
    }
}" \
  'http://www.dnsvault.net/api/v1/nodes/1/network/routes/4'
```


> The above command returns JSON structured like this:

```json
{
    "id": 4,
    "node_id": 26,
    "typ": "ipv4",
    "route_name": "localhost",
    "ip_address": "192.168.0.111",
    "ipv4_subnetmask": "255.255.255.100",
    "ipv6_prefix": null,
    "gateway": null,
    "interface": null,
    "note": "update",
    "created_at": "2018-02-14T07:39:14.968Z",
    "updated_at": "2018-02-14T07:39:14.968Z"
}
```

This endpoint update a Network Routes.

### HTTP Request

`PUT http://www.dnsvault.net/api/v1/nodes/:node_id/network/routes/:interface_id/aliases/:id`

#### URL Parameters

Parameter | Description
--------- | -----------
Node_id | The ID of the network route's node to retrieve
Interface_id | The ID of the network route's node to retrieve
Id | The ID of the network route to retrieve

## Delete Network Routes

```shell
curl --include \
     --request DELETE \
     --header "Authorization: Token iwwTXK54aahsosrx5JK7hkTe" \
  'http://www.dnsvault.net/api/v1/nodes/1/network/routes/4'
```


> The above command returns JSON structured like this:

```json
{
    "id": 4,
    "node_id": 26,
    "typ": "ipv4",
    "route_name": "localhost",
    "ip_address": "192.168.0.111",
    "ipv4_subnetmask": "255.255.255.100",
    "ipv6_prefix": null,
    "gateway": null,
    "interface": null,
    "note": "update",
    "created_at": "2018-02-14T07:39:14.968Z",
    "updated_at": "2018-02-14T07:39:14.968Z"
}
```

This endpoint delete a Network Routes.

### HTTP Request

`DELETE http://www.dnsvault.net/api/v1/nodes/:node_id/network/routes/:id`

#### URL Parameters

Parameter | Description
--------- | -----------
Node_id | The ID of the network route's node to retrieve
Interface_id | The ID of the network route's node to retrieve
Id | The ID of the network route to delete