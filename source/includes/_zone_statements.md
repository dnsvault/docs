# Zone Statement

## List all Zone Statement

You may list collection of Zone Statement using this action.

```shell
curl --include \
'http://www.dnsvault.net/api/v1/nodes/2/dns/views/51/zones/1/statements'
```

> The above command returns JSON structured like this:

```json
[
    {
        "id": 1,
        "statement": "match-clients",
        "negate": false,
        "position": 0,
        "value_type": "ip_address",
        "value": "1.1.1.1",
        "status": "active",
        "port": 53,
        "read_only": false,
        "created_at": "2017-07-11T03:50:18.530Z",
        "updated_at": "2017-07-11T03:50:18.530Z"
    }
]
```

This endpoint retrieves all statements.

### HTTP Request

`GET http://www.dnsvault.net/api/v1/nodes/:node_id/dns/views/:view_id/zones/:zone_id/statements`

## Show Zone Statement

You may view detail of a statement using this action.

```shell
curl --include \
'http://www.dnsvault.net/api/v1/nodes/2/dns/views/51/zones/1/statements/1'
```

> The above command returns JSON structured like this:

```json
{
    "id": 1,
    "statement": "match-clients",
    "negate": false,
    "position": 0,
    "value_type": "ip_address",
    "value": "1.1.1.1",
    "status": "active",
    "port": 53,
    "read_only": false,
    "created_at": "2017-07-11T03:50:18.530Z",
    "updated_at": "2017-07-11T03:50:18.530Z"
}
```

This endpoint retrieves detail of a statement.

### HTTP Request

`GET http://www.dnsvault.net/api/v1/nodes/:node_id/dns/views/:view_id/zones/:zone_id/statements/:id`

## Create Zone Statement

You may create a statement using this action. It takes a JSON object containing a parameters.

```shell
curl --include \
     --request POST \
     --header "Content-Type: application/json" \
     --data-binary "{
    \"type\": \"ip_address\",
    \"value\": \"12.1.1.1\",
    \"negate\": \"false\"
}" \
'http://www.dnsvault.net/api/v1/nodes/2/dns/views/51/zones/1/statements'
```

> The above command returns JSON structured like this:

```json
{
    "id": 5,
    "node_id": 2,
    "statementable_id": 52,
    "statementable_type": "Dns::Zone",
    "statement": "allow-query",
    "position": 0,
    "value_type": "ip_address",
    "value": "12.1.1.1",
    "port": 53,
    "negate": false,
    "status": "active",
    "read_only": false,
    "created_at": "2017-07-11T08:54:25.603Z",
    "updated_at": "2017-07-11T08:54:25.603Z"
}
```

This endpoint creates a statement.

### HTTP Request

`POST http://www.dnsvault.net/api/v1/nodes/:node_id/dns/views/:view_id/zones/:zone_id/statements`

## Delete a Zone Statement

You may delete an statement using this action.

```shell
curl --include \
     --request DELETE \
'http://www.dnsvault.net/api/v1/nodes/2/dns/views/1/zones/22/statements/1'
```

> The above command returns JSON structured like this:

```json
{
    "id": 1,
    "node_id": 2,
    "statementable_id": 51,
    "statementable_type": "Dns::View",
    "statement": "match-clients",
    "position": 0,
    "value_type": "ip_address",
    "value": "1.1.1.1",
    "port": 53,
    "negate": false,
    "status": "active",
    "read_only": false,
    "created_at": "2017-07-11T03:50:18.530Z",
    "updated_at": "2017-07-11T03:50:18.530Z"
}
```

This endpoint creates a statement.

`DELETE http://www.dnsvault.net/api/v1/nodes/:node_id/dns/views/:view_id/zones/:zone_id/statements/:id`

## Delete multiple zone statements

You may delete multiple statements using this action.

```shell
curl --include \
     --request DELETE \
     --data-binary "{
    \"statements\": \"[6,7]\"
}" \
'http://www.dnsvault.net/api/v1/nodes/2/dns/views/1/zones/2/statements/1'
```

> The above command returns JSON structured like this:

```json
[{
    "id": 1,
    "node_id": 2,
    "statementable_id": 51,
    "statementable_type": "Dns::View",
    "statement": "match-clients",
    "position": 0,
    "value_type": "ip_address",
    "value": "1.1.1.1",
    "port": 53,
    "negate": false,
    "status": "active",
    "read_only": false,
    "created_at": "2017-07-11T03:50:18.530Z",
    "updated_at": "2017-07-11T03:50:18.530Z"
}]
```

This endpoint delete multiple statement.

`DELETE http://www.dnsvault.net/api/v1/nodes/:node_id/dns/views/:view_id/zones/:zone_id/statements`


## Sort Zone Statement

You may sort statements using this action.

```shell
curl --include \
     --request PUT \
     --header "Content-Type: application/json" \
     --data-binary "{
    \"statement\": [
        {
             \"statement_id\": 3
        },
        {
             \"position\": 0 
        }
    ]
}" \
'http://www.dnsvault.net/api/v1/nodes/2/dns/views/1/zones/12/statements/sort'
```

> The above command returns JSON structured like this:

```json
[{
    "id": 1,
    "node_id": 2,
    "statementable_id": 51,
    "statementable_type": "Dns::View",
    "statement": "match-clients",
    "position": 0,
    "value_type": "ip_address",
    "value": "1.1.1.1",
    "port": 53,
    "negate": false,
    "status": "active",
    "read_only": false,
    "created_at": "2017-07-11T03:50:18.530Z",
    "updated_at": "2017-07-11T03:50:18.530Z"
}]
```

This endpoint sort a statement.

`PUT http://www.dnsvault.net/api/v1/nodes/:node_id/dns/views/:view_id/zones/:zone_id/statements/sorts`

## Sort multiple zone statement

You may sort statements using this action.

```shell
curl --include \
     --request POST \
     --header "Content-Type: application/json" \
     --data-binary "{
    \"statement\": [
        {
             \"statement_id\": 3
        },
        {
             \"position\": 0 
        }
    ]
}" \
'http://www.dnsvault.net/api/v1/nodes/2/dns/views/1/zones/22/statements/sort'
```

> The above command returns JSON structured like this:

```json
[{
    "id": 1,
    "node_id": 2,
    "statementable_id": 51,
    "statementable_type": "Dns::View",
    "statement": "match-clients",
    "position": 0,
    "value_type": "ip_address",
    "value": "1.1.1.1",
    "port": 53,
    "negate": false,
    "status": "active",
    "read_only": false,
    "created_at": "2017-07-11T03:50:18.530Z",
    "updated_at": "2017-07-11T03:50:18.530Z"
}]
```

This endpoint sort multiple statement.

`POST http://www.dnsvault.net/api/v1/nodes/:node_id/dns/views/:view_id/zones/:zone_id/statements/sorts`
