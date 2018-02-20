# Network Interface (update)

## List all Interface

You may list collection of Network Interface using this action. Default per page is 20.

```shell
curl --include \
'http://www.dnsvault.net/api/v1/nodes/1/network/interfaces'
```

> The above command returns JSON structured like this:

```json
[
    {
        "id": 9,
        "interface": "net2",
        "hostname": null,
        "ipv4_address": "192.168.0.100",
        "ipv4_subnetmask": "255.255.255.10",
        "ipv4_gateway": null,
        "ipv6_address": "1.1.1.1",
        "created_at": "2018-02-02T04:47:52.596Z",
        "updated_at": "2018-02-13T09:49:41.002Z"
    },
    {
        "id": 7,
        "interface": "net0",
        "hostname": null,
        "ipv4_address": "1.32.55.10",
        "ipv4_subnetmask": "255.255.255.100",
        "ipv4_gateway": null,
        "ipv6_address": "2001:ABCD:EFGH:1243",
        "created_at": "2018-02-02T04:47:52.548Z",
        "updated_at": "2018-02-13T10:43:21.496Z"
    },
    {
        "id": 8,
        "interface": "net1",
        "hostname": null,
        "ipv4_address": "201.32.56.654",
        "ipv4_subnetmask": "255.255.255.0",
        "ipv4_gateway": null,
        "ipv6_address": null,
        "created_at": "2018-02-02T04:47:52.575Z",
        "updated_at": "2018-02-13T06:31:48.507Z"
    }
]
```

This endpoint retrieves all Network Interface.

### HTTP Request

`GET http://www.dnsvault.net/api/v1/nodes/:node_id/network/interfaces`

#### URL Parameters

Parameter | Description
--------- | -----------
Node_id | The ID of the network interface's node to retrieve

## Show Network Interface

You may list collection of Network Interface using this action. Default per page is 20.

```shell
curl --include \
'http://www.dnsvault.net/api/v1/nodes/1/network/interfaces/9'
```

> The above command returns JSON structured like this:

```json
{
    "id": 9,
    "interface": "net2",
    "hostname": null,
    "ipv4_address": "192.168.0.100",
    "ipv4_subnetmask": "255.255.255.10",
    "ipv4_gateway": null,
    "ipv6_address": "1.1.1.1",
    "created_at": "2018-02-02T04:47:52.596Z",
    "updated_at": "2018-02-13T09:49:41.002Z"
}
```

This endpoint retrieves an Network Interface.

### HTTP Request

`GET http://www.dnsvault.net/api/v1/nodes/:node_id/network/interfaces/:id`

#### URL Parameters

Parameter | Description
--------- | -----------
Node_id | The ID of the network interface's node to retrieve
Id | The ID of the network interface to retrieve

## Update Network Interface (required param)

```shell
curl --include \
     --request PUT \
     --header "Content-Type: application/json" \
     --data-binary "{
    \"option\": {
        \"hostname\": \"net3\",
        \"ipv4_address\": \"192.168.0.111\",
        \"ipv4_subnetmask\": \"255.255.255.100\",
        \"ipv4_gateway\": \"null\",
        \"ipv6_address\": \"1.1.1.2\"

    }
}" \
  'http://www.dnsvault.net/api/v1/nodes/1/network/interfaces/9'
```


> The above command returns JSON structured like this:

```json
{
    "id": 9,
    "interface": "net2",
    "hostname": "net3",
    "ipv4_address": "192.168.0.111",
    "ipv4_subnetmask": "255.255.255.100",
    "ipv4_gateway": null,
    "ipv6_address": "1.1.1.2",
    "created_at": "2018-02-02T04:47:52.596Z",
    "updated_at": "2018-02-13T09:49:41.002Z"
}
```

This endpoint update a Network Interface.

### HTTP Request

`PUT http://www.dnsvault.net/api/v1/nodes/:node_id/network/interfaces/:id`

#### URL Parameters

Parameter | Description
--------- | -----------
Node_id | The ID of the network interface's node to retrieve
Id | The ID of the network interface to delete

