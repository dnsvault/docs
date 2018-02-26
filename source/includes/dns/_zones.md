## Zones (status, show & update)

### List all Zones
You may list collection of zones using this action.

```shell
curl --include \
     --header "Content-Type: application/json" \
     --header "Authorization: Token iwwTXK54aahsosrx5JK7hkTe" \
  'http://www.dnsvault.net/api/v1/nodes/2/dns/views/11/zones'
```

> The above command returns JSON structured like this:

```json
[
    {
        "id": 147,
        "view_id": 11,
        "view_name": "default",
        "zone_name": "dnsv.my",
        "zone_type": "master",
        "kind": "default",
        "serial_number": null,
        "allow_transfer": "off",
        "allow_query": "off",
        "allow_update": "off",
        "also_notify": "off",
        "notify_source": "off",
        "description": null,
        "status": "active",
        "position": 3,
        "created_at": "2018-02-22T04:19:43.794Z",
        "updated_at": "2018-02-22T04:19:43.794Z"
    },
    {
        "id": 146,
        "view_id": 11,
        "view_name": "default",
        "zone_name": "local.my",
        "zone_type": "master",
        "kind": "default",
        "serial_number": null,
        "allow_transfer": "off",
        "allow_query": "off",
        "allow_update": "off",
        "also_notify": "off",
        "notify_source": "off",
        "description": null,
        "status": "active",
        "position": 2,
        "created_at": "2018-02-22T03:59:19.956Z",
        "updated_at": "2018-02-22T03:59:19.956Z"
    },
    {
        "id": 145,
        "view_id": 11,
        "view_name": "default",
        "zone_name": "localhost.my",
        "zone_type": "master",
        "kind": "default",
        "serial_number": "3",
        "allow_transfer": "off",
        "allow_query": "off",
        "allow_update": "off",
        "also_notify": "off",
        "notify_source": "off",
        "description": "",
        "status": "active",
        "position": 1,
        "created_at": "2018-02-22T03:56:06.753Z",
        "updated_at": "2018-02-23T09:12:47.659Z"
    }
]
```

This endpoint get list of zones.

#### HTTP Request

`GET http://www.dnsvault.net/api/v1/nodes/:node_id/dns/views/:view_id/zones`

#### URL Parameters

Parameter | Description
--------- | -----------
Node_id | The ID of the zone's node to retrieve
View_id | The ID of the zone's view to retrieve

### Create Zone

You may create a zone using this action. It takes a JSON object containing a parameters.

```shell
curl --include \
     --request POST \
     --header "Content-Type: application/json" \
     --header "Authorization: Token iwwTXK54aahsosrx5JK7hkTe" \
     --data-binary "{
    \"zone\" :
    {
        \"zone_name\" : \"dnsvault.my\",
        \"kind\" : \"rpz\"
    },
    \"soa\" : 
    {
        \"data\" : \"ns1. admin.dnsvault.net. 1 10800 3600 604800 86400\", 
        \"kind\" : \"SOA\", 
        \"domain\" : \"dnsvault.my\", 
        \"read_only\" : true
    },
    \"nameservers\": 
    [{
        \"data\" : \"ns1\",
        \"kind\" : \"NS\", 
        \"domain\" : \"dnsvault.my\", 
        \"read_only\" : true, 
        \"primary\" : true, 
        \"glue\" : false, 
        \"ipv4\" : \"nil\", 
        \"ipv6\" : \"nil\"
    }]
}" \
'http://www.dnsvault.net/api/v1/nodes/2/dns/views/11/zones'
```

> The above command returns JSON structured like this:

```json
{
    "id": 148,
    "view_id": 11,
    "view_name": "default",
    "zone_name": "dnsvault.my",
    "zone_type": "master",
    "kind": "default",
    "serial_number": "3",
    "allow_transfer": "off",
    "allow_query": "off",
    "allow_update": "off",
    "also_notify": "off",
    "notify_source": "off",
    "description": "",
    "status": "active",
    "position": 4,
    "created_at": "2018-02-22T03:56:06.753Z",
    "updated_at": "2018-02-23T09:12:47.659Z"
}
```

This endpoint create a zone.

#### HTTP Request

`POST http://www.dnsvault.net/api/v1/nodes/:node_id/dns/views/:view_id/zones`

#### URL Parameters

Parameter | Description
--------- | -----------
Node_id | The ID of the zone's node to retrieve
View_id | The ID of the zone's view to retrieve

#### Required Parameters

Parameter | Description
--------- | -----------
Zone | Zone details
SOA | SOA details
Nameservers | Nameserver details

### Show Zone

You may list a zone using this action.

```shell
curl --include \
     --header "Authorization: Token iwwTXK54aahsosrx5JK7hkTe" \
  'http://www.dnsvault.net/api/v1/nodes/2/dns/views/11/zones/148'
```

> The above command returns JSON structured like this:

```json
{
    "id": 148,
    "view_id": 11,
    "view_name": "default",
    "zone_name": "dnsvault.my",
    "zone_type": "master",
    "kind": "default",
    "serial_number": "3",
    "allow_transfer": "off",
    "allow_query": "off",
    "allow_update": "off",
    "also_notify": "off",
    "notify_source": "off",
    "description": "",
    "status": "active",
    "position": 4,
    "created_at": "2018-02-22T03:56:06.753Z",
    "updated_at": "2018-02-23T09:12:47.659Z"
}
```

This endpoint get list of zones.

#### HTTP Request

`GET http://www.dnsvault.net/api/v1/nodes/:node_id/dns/views/:view_id/zones/:id`

#### URL Parameters

Parameter | Description
--------- | -----------
Node_id | The ID of the zone's node to retrieve
View_id | The ID of the zone's view to retrieve
Id | The ID of the zone to retrieve

### Show Zone Status

### Update Zone Status

### Delete Zone

You may delete a zone using this action.

```shell
curl --include \
     --request DELETE \
     --header "Content-Type: application/json" \
     --header "Authorization: Token iwwTXK54aahsosrx5JK7hkTe" \
  'http://www.dnsvault.net/api/v1/nodes/2/dns/views/11/zones/148'
```

 The above command returns JSON structured like this:

```json
{
    "id": 148,
    "view_id": 11,
    "view_name": "default",
    "zone_name": "dnsvault.my",
    "zone_type": "master",
    "kind": "default",
    "serial_number": "3",
    "allow_transfer": "off",
    "allow_query": "off",
    "allow_update": "off",
    "also_notify": "off",
    "notify_source": "off",
    "description": "",
    "status": "active",
    "position": 4,
    "created_at": "2018-02-22T03:56:06.753Z",
    "updated_at": "2018-02-23T09:12:47.659Z"
}
```

This endpoint delete a zone.

#### HTTP Request

`DELETE http://www.dnsvault.net/api/v1/nodes/:node_id/dns/views/:view_id/zones/:id`

#### URL Parameters

Parameter | Description
--------- | -----------
Node_id | The ID of the zone's node to retrieve
View_id | The ID of the zone's view to retrieve
Id | The ID of the zone to delete
