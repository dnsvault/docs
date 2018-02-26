## Alias (create & update)

### List all Alias

You may list collection of Network Alias using this action. Default per page is 20.

```shell
curl --include \
'http://www.dnsvault.net/api/v1/nodes/1/network/interfaces/9/aliases'
```

> The above command returns JSON structured like this:

```json
[
    {
        "id": 1,
        "interface_id": 9,
        "typ": "ipv6",
        "alias": null,
        "ip_address": "12.33.44.55",
        "ipv4_subnetmask": null,
        "ipv6_prefix": "65",
        "note": "",
        "created_at": "2018-02-09T05:17:35.430Z",
        "updated_at": "2018-02-09T05:17:35.430Z"
    },
    {
        "id": 2,
        "interface_id": 9,
        "typ": "ipv6",
        "alias": null,
        "ip_address": "12.33.44.55",
        "ipv4_subnetmask": null,
        "ipv6_prefix": "65",
        "note": "",
        "created_at": "2018-02-09T05:20:16.507Z",
        "updated_at": "2018-02-09T05:20:16.507Z"
    },
    {
        "id": 13,
        "interface_id": 9,
        "typ": "ipv4",
        "alias": null,
        "ip_address": "1.1.12.33",
        "ipv4_subnetmask": "255.255.255.0",
        "ipv6_prefix": null,
        "note": "",
        "created_at": "2018-02-13T07:03:31.599Z",
        "updated_at": "2018-02-13T07:03:31.599Z"
    }
]
```

This endpoint retrieves all Network Alias.

#### HTTP Request

`GET http://www.dnsvault.net/api/v1/nodes/:node_id/network/interfaces/:interface_id/aliases`

##### URL Parameters

Parameter | Description
--------- | -----------
Node_id | The ID of the network interface's node to retrieve
Interface_id | The ID of the network interface's node to retrieve

### Create Network Alias (required params)

You may create a Network Alias using this action. It takes a JSON object containing a parameters.

```shell
curl --include \
     --request POST \
     --header "Content-Type: application/json" \
     --data-binary "{
    \"typ\": \"ipv4\",
    \"alias\": \"null\",
    \"ipv4_address\": \"192.168.0.111\",
    \"ipv4_subnetmask\": \"255.255.255.100\",
    \"ipv6_prefix\": \"75\",
    \"note\": \"update\"
}" \
'http://www.dnsvault.net/api/v1/nodes/1/network/interfaces/9/aliases'
```

> The above command returns JSON structured like this:

```json
{
    "id": 1,
    "interface_id": 9,
    "typ": "ipv4",
    "alias": null,
    "ip_address": "192.168.0.111",
    "ipv4_subnetmask": "255.255.255.100",
    "ipv6_prefix": "75",
    "note": "update",
    "created_at": "2018-02-09T05:17:35.430Z",
    "updated_at": "2018-02-09T05:17:35.430Z"
}
```

This endpoint creates an Network Alias

##### URL Parameters

Parameter | Description
--------- | -----------
Node_id | The ID of the network interface's node to retrieve
Interface_id | The ID of the network interface's node to retrieve

### Show Network Alias

You may list collection of Network Alias using this action. Default per page is 20.

```shell
curl --include \
'http://www.dnsvault.net/api/v1/nodes/1/network/interfaces/9/aliases/1'
```

> The above command returns JSON structured like this:

```json
{
    "id": 1,
    "interface_id": 9,
    "typ": "ipv6",
    "alias": null,
    "ip_address": "12.33.44.55",
    "ipv4_subnetmask": null,
    "ipv6_prefix": "65",
    "note": "",
    "created_at": "2018-02-09T05:17:35.430Z",
    "updated_at": "2018-02-09T05:17:35.430Z"
}
```

This endpoint retrieves an Network Alias.

#### HTTP Request

`GET http://www.dnsvault.net/api/v1/nodes/:node_id/network/interfaces/:interface_id/aliases/:id`

##### URL Parameters

Parameter | Description
--------- | -----------
Node_id | The ID of the network interface's node to retrieve
Interface_id | The ID of the network interface's node to retrieve
Id | The ID of the network interface to retrieve

### Update Network Alias (required params)

```shell
curl --include \
     --request PUT \
     --header "Content-Type: application/json" \
     --data-binary "{
    \"alias\": {
        \"typ\": \"ipv4\",
        \"alias\": \"null\",
        \"ipv4_address\": \"192.168.0.111\",
        \"ipv4_subnetmask\": \"255.255.255.100\",
        \"ipv6_prefix\": \"75\",
        \"note\": \"update\"
    }
}" \
  'http://www.dnsvault.net/api/v1/nodes/1/network/interfaces/1'
```


> The above command returns JSON structured like this:

```json
{
    "id": 1,
    "interface_id": 9,
    "typ": "ipv4",
    "alias": null,
    "ip_address": "192.168.0.111",
    "ipv4_subnetmask": "255.255.255.100",
    "ipv6_prefix": "75",
    "note": "update",
    "created_at": "2018-02-09T05:17:35.430Z",
    "updated_at": "2018-02-09T05:17:35.430Z"
}
```

This endpoint update a Network Alias.

#### HTTP Request

`PUT http://www.dnsvault.net/api/v1/nodes/:node_id/network/interfaces/:interface_id/aliases/:id`

#### URL Parameters

Parameter | Description
--------- | -----------
Node_id | The ID of the network interface's node to retrieve
Interface_id | The ID of the network interface's node to retrieve
Id | The ID of the network interface to retrieve

### Delete Network Alias

```shell
curl --include \
     --request DELETE \
     --header "Authorization: Token iwwTXK54aahsosrx5JK7hkTe" \
  'http://www.dnsvault.net/api/v1/nodes/1/network/interfaces/9/aliases/1'
```


> The above command returns JSON structured like this:

```json
{
    "id": 1,
    "interface_id": 9,
    "typ": "ipv4",
    "alias": null,
    "ip_address": "192.168.0.111",
    "ipv4_subnetmask": "255.255.255.100",
    "ipv6_prefix": "75",
    "note": "update",
    "created_at": "2018-02-09T05:17:35.430Z",
    "updated_at": "2018-02-09T05:17:35.430Z"
}
```

This endpoint delete a Network Alias.

#### HTTP Request

`DELETE http://www.dnsvault.net/api/v1/nodes/:node_id/network/interfaces/:interface_id/aliases/:id`

##### URL Parameters

Parameter | Description
--------- | -----------
Node_id | The ID of the network interface's node to retrieve
Interface_id | The ID of the network interface's node to retrieve
Id | The ID of the network interface to delete