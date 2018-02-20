# Network Vlans

## List all Vlans

You may list collection of Network Vlans using this action. Default per page is 20.

```shell
curl --include \
'http://www.dnsvault.net/api/v1/nodes/1/network/vlans'
```

> The above command returns JSON structured like this:

```json
[
    {
        "id": 1,
        "node_id": 26,
        "interface_id": 3,
        "vlan_name": "dnsvault",
        "vlan_interface": null,
        "vid": 1,
        "ipv4_address": null,
        "ipv4_subnetmask": null,
        "ipv4_gateway": null,
        "ipv6_address": null,
        "ipv6_prefix": null,
        "ipv6_gateway": null,
        "state": false,
        "note": "",
        "created_at": "2018-02-12T06:21:57.020Z",
        "updated_at": "2018-02-12T06:21:57.020Z"
    }
]
```

This endpoint retrieves all Network Vlans.

### HTTP Request

`GET http://www.dnsvault.net/api/v1/nodes/:node_id/network/vlans`

## Create Network Vlans

You may create a Network Vlans using this action. It takes a JSON object containing a parameters.

```shell
curl --include \
     --request POST \
     --header "Content-Type: application/json" \
     --data-binary "{
    \"interface_id\": \"3\",
    \"vlan_name\": \"localdns\",
    \"vid\": \"1\",
    \"state\": \"false\",
    \"note\": \"null\"
}" \
'http://www.dnsvault.net/api/v1/nodes/1/network/vlans'
```

> The above command returns JSON structured like this:

```json
{
    "id": 2,
    "node_id": 26,
    "interface_id": 3,
    "vlan_name": "localdns",
    "vlan_interface": null,
    "vid": 1,
    "ipv4_address": null,
    "ipv4_subnetmask": null,
    "ipv4_gateway": null,
    "ipv6_address": null,
    "ipv6_prefix": null,
    "ipv6_gateway": null,
    "state": false,
    "note": "",
    "created_at": "2018-02-12T06:21:57.020Z",
    "updated_at": "2018-02-12T06:21:57.020Z"
}
```

This endpoint creates an Network Vlans

### HTTP Request

`POST http://www.dnsvault.net/api/v1/nodes/:node_id/network/vlans`

## Show Network Vlans

You may list collection of Network Vlans using this action. Default per page is 20.

```shell
curl --include \
'http://www.dnsvault.net/api/v1/nodes/1/network/vlans/2'
```

> The above command returns JSON structured like this:

```json
{
    "id": 2,
    "node_id": 26,
    "interface_id": 3,
    "vlan_name": "localdns",
    "vlan_interface": null,
    "vid": 1,
    "ipv4_address": null,
    "ipv4_subnetmask": null,
    "ipv4_gateway": null,
    "ipv6_address": null,
    "ipv6_prefix": null,
    "ipv6_gateway": null,
    "state": false,
    "note": "",
    "created_at": "2018-02-12T06:21:57.020Z",
    "updated_at": "2018-02-12T06:21:57.020Z"
}
```

This endpoint retrieves an Network Vlans.

### HTTP Request

`GET http://www.dnsvault.net/api/v1/nodes/:node_id/network/vlans/:id`

## Update Network Vlans

```shell
curl --include \
     --request PUT \
     --header "Content-Type: application/json" \
     --data-binary "{
    \"vlan\": {
        \"interface_id\": \"4\",
        \"vlan_name\": \"localdns\",
        \"vid\": \"1\",
        \"state\": \"false\",
        \"note\": \"update\"
    }
}" \
  'http://www.dnsvault.net/api/v1/nodes/1/network/vlans/2'
```


> The above command returns JSON structured like this:

```json
{
    "id": 2,
    "node_id": 26,
    "interface_id": 4,
    "vlan_name": "localdns",
    "vlan_interface": null,
    "vid": 1,
    "ipv4_address": null,
    "ipv4_subnetmask": null,
    "ipv4_gateway": null,
    "ipv6_address": null,
    "ipv6_prefix": null,
    "ipv6_gateway": null,
    "state": false,
    "note": "update",
    "created_at": "2018-02-12T06:21:57.020Z",
    "updated_at": "2018-02-12T06:21:57.020Z"
}
```

This endpoint update a Network Vlans.

### HTTP Request

`PUT http://www.dnsvault.net/api/v1/nodes/:node_id/network/vlans/:interface_id/aliases/:id`

## Delete Network Vlans

```shell
curl --include \
     --request DELETE \
     --header "Authorization: Token iwwTXK54aahsosrx5JK7hkTe" \
  'http://www.dnsvault.net/api/v1/nodes/1/network/vlans/2'
```


> The above command returns JSON structured like this:

```json
{
    "id": 2,
    "node_id": 26,
    "interface_id": 4,
    "vlan_name": "localdns",
    "vlan_interface": null,
    "vid": 1,
    "ipv4_address": null,
    "ipv4_subnetmask": null,
    "ipv4_gateway": null,
    "ipv6_address": null,
    "ipv6_prefix": null,
    "ipv6_gateway": null,
    "state": false,
    "note": "",
    "created_at": "2018-02-12T06:21:57.020Z",
    "updated_at": "2018-02-12T06:21:57.020Z"
}
```

This endpoint delete a Network Vlans.

### HTTP Request

`DELETE http://www.dnsvault.net/api/v1/nodes/:node_id/network/vlans/:id`