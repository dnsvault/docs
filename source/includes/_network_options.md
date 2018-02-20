# Network Options

## List all Options

You may list collection of Network Options using this action. Default per page is 20.

```shell
curl --include \
'http://www.dnsvault.net/api/v1/nodes/1/network/options'
```

> The above command returns JSON structured like this:

```json
[
    {
        "id": 22,
        "statement": "nameserver2",
        "statement_value": "8.8.4.90",
        "status": 0,
        "category": null,
        "description": null,
        "created_at": "2018-02-02T04:47:52.414Z",
        "updated_at": "2018-02-02T04:47:52.414Z"
    },
    {
        "id": 25,
        "statement": "snmp_location",
        "statement_value": "somewhere dnsvault snmp",
        "status": 0,
        "category": null,
        "description": null,
        "created_at": "2018-02-02T04:47:52.485Z",
        "updated_at": "2018-02-02T04:47:52.485Z"
    },
    {
        "id": 26,
        "statement": "snmp_contact_info",
        "statement_value": "help@dnsvault.net",
        "status": 0,
        "category": null,
        "description": null,
        "created_at": "2018-02-02T04:47:52.502Z",
        "updated_at": "2018-02-02T04:47:52.502Z"
    }
]
```

This endpoint retrieves all Network Options.

### HTTP Request

`GET http://www.dnsvault.net/api/v1/nodes/:node_id/network/options`

#### URL Parameters

Parameter | Description
--------- | -----------
Node_id | The ID of the network option's node to retrieve

## Show Network Options

You may list collection of Network Options using this action. Default per page is 20.

```shell
curl --include \
'http://www.dnsvault.net/api/v1/nodes/1/network/options/22'
```

> The above command returns JSON structured like this:

```json
{
    "id": 22,
    "statement": "nameserver2",
    "statement_value": "8.8.4.90",
    "status": 0,
    "category": null,
    "description": null,
    "created_at": "2018-02-02T04:47:52.414Z",
    "updated_at": "2018-02-02T04:47:52.414Z"
}
```

This endpoint retrieves an Network Options.

### HTTP Request

`GET http://www.dnsvault.net/api/v1/nodes/:node_id/network/options/:id`

#### URL Parameters

Parameter | Description
--------- | -----------
Node_id | The ID of the network option's node to retrieve
Id | The ID of the network option to retrieve

## Update Network Options

```shell
curl --include \
     --request PUT \
     --header "Content-Type: application/json" \
     --data-binary "{
    \"option\": {
        \"statement_value\": \"help@dnsvault.net\"
    }
}" \
  'http://www.dnsvault.net/api/v1/nodes/1/network/options/22'
```


> The above command returns JSON structured like this:

```json
{
    "id": 22,
    "statement": "nameserver2",
    "statement_value": "help@dnsvault.net",
    "status": 0,
    "category": null,
    "description": null,
    "created_at": "2018-02-02T04:47:52.414Z",
    "updated_at": "2018-02-02T04:47:52.414Z"
}
```

This endpoint update a Network Options.

### HTTP Request

`PUT http://www.dnsvault.net/api/v1/nodes/:node_id/network/options/:id`

#### URL Parameters

Parameter | Description
--------- | -----------
Node_id | The ID of the network option's node to retrieve
Id | The ID of the network option to retrieve

#### Required Parameters

Parameter | Description
--------- | -----------
statement_value | The statement value of the network option
