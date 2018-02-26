## Option Statement

### List all Statement

You may list collection of Option Statement using this action.

```shell
curl --include \
'http://www.dnsvault.net/api/v1/nodes/2/dns/options/1/statements'
```

> The above command returns JSON structured like this:

```json
[
    {
        "id": 1,
        "statement": "blackhole",
        "negate": false,
        "position": 0,
        "value_type": "ip_address",
        "value": "1.1.1.2",
        "status": "active",
        "port": 53,
        "read_only": false,
        "created_at": "2018-02-22T02:34:57.375Z",
        "updated_at": "2018-02-22T02:39:17.449Z"
    },
    {
        "id": 2,
        "statement": "blackhole",
        "negate": false,
        "position": 1,
        "value_type": "ip_address",
        "value": "1.1.1.1",
        "status": "active",
        "port": 53,
        "read_only": false,
        "created_at": "2018-02-21T06:35:57.118Z",
        "updated_at": "2018-02-22T02:39:17.448Z"
    }
]
```

This endpoint retrieves all statements.

#### HTTP Request

`GET http://www.dnsvault.net/api/v1/nodes/:node_id/dns/options/:option_id/statements`

#### URL Parameters

Parameter | Description
--------- | -----------
Node_id | The ID of the option statement's node to retrieve
Option_id | The ID of the option statement's option to retrieve

### Show Statement

You may option detail of a statement using this action.

```shell
curl --include \
'http://www.dnsvault.net/api/v1/nodes/2/dns/options/1/statements/1'
```

> The above command returns JSON structured like this:

```json
{
    "id": 1,
    "statement": "blackhole",
    "negate": false,
    "position": 0,
    "value_type": "ip_address",
    "value": "1.1.1.2",
    "status": "active",
    "port": 53,
    "read_only": false,
    "created_at": "2018-02-22T02:34:57.375Z",
    "updated_at": "2018-02-22T02:39:17.449Z"
}
```

This endpoint retrieves detail of a statement.

#### HTTP Request

`GET http://www.dnsvault.net/api/v1/nodes/:node_id/dns/options/:option_id/statements/:id`

#### URL Parameters

Parameter | Description
--------- | -----------
Node_id | The ID of the option statement's node to retrieve
Option_id | The ID of the option statement's option to retrieve
Id | The ID of the option statement to retrieve

### Create Statement

You may create a statement using this action. It takes a JSON object containing a parameters.

```shell
curl --include \
     --request POST \
     --header "Content-Type: application/json" \
     --data-binary "{
    \"statement\": \"blackhole\",
    \"type\": \"ip_address\",
    \"value\": \"192.0.0.0\"
}" \
'http://www.dnsvault.net/api/v1/nodes/2/dns/options/1/statements'
```

> The above command returns JSON structured like this:

```json
{
    "id": 3,
    "statement": "blackhole",
    "negate": false,
    "position": 0,
    "value_type": "ip_address",
    "value": "192.0.0.0",
    "status": "active",
    "port": 53,
    "read_only": false,
    "created_at": "2018-02-22T02:34:57.375Z",
    "updated_at": "2018-02-22T02:39:17.449Z"
}
```

This endpoint creates a statement.

#### HTTP Request

`POST http://www.dnsvault.net/api/v1/nodes/:node_id/dns/options/:option_id/statements`

#### URL Parameters

Parameter | Description
--------- | -----------
Node_id | The ID of the option statement's node to retrieve
Option_id | The ID of the option statement's option to retrieve

#### Required Parameters

Parameter | Description
--------- | -----------
statement | the option statement
type | Type of the statement
value | Value of the statement

Statement | type | Value
--------- | ---- | -----
listen-on | ip_address | IP Address value
listen-on-v6 | ip_address | IP Address value
blackhole | ip_address | IP Address value
 | acl | Acl Name
allow-recursion | ip_address | IP Address value
 | acl | Acl Name
forward | ip_address | IP Address value

### Delete a Statement

You may delete an statement using this action.

```shell
curl --include \
     --request DELETE \
'http://www.dnsvault.net/api/v1/nodes/2/dns/options/1/statements/3'
```

> The above command returns JSON structured like this:

```json
{
    "id": 3,
    "statement": "blackhole",
    "negate": false,
    "position": 0,
    "value_type": "ip_address",
    "value": "192.0.0.0",
    "status": "active",
    "port": 53,
    "read_only": false,
    "created_at": "2018-02-22T02:34:57.375Z",
    "updated_at": "2018-02-22T02:39:17.449Z"
}
```

This endpoint creates a statement.

`DELETE http://www.dnsvault.net/api/v1/nodes/:node_id/dns/options/:option_id/statements/:id`

#### URL Parameters

Parameter | Description
--------- | -----------
Node_id | The ID of the option statement's node to retrieve
Option_id | The ID of the option statement's option to retrieve
Id | The ID of the option statement to delete

### Sort Statement

You may sort statements using this action.

```shell
curl --include \
     --request PUT \
     --header "Content-Type: application/json" \
     --data-binary "{
    {
    \"id\": \"2\",
    \"position\" : \"0\"
    }
}" \
'http://www.dnsvault.net/api/v1/nodes/2/dns/options/1/statements/sort'
```

> The above command returns JSON structured like this:

```json
{
    "id": 2,
    "statement": "blackhole",
    "negate": false,
    "position": 0,
    "value_type": "ip_address",
    "value": "1.1.1.1",
    "status": "active",
    "port": 53,
    "read_only": false,
    "created_at": "2018-02-21T06:35:57.118Z",
    "updated_at": "2018-02-22T02:39:17.448Z"
},
{
    "id": 1,
    "statement": "blackhole",
    "negate": false,
    "position": 1,
    "value_type": "ip_address",
    "value": "1.1.1.2",
    "status": "active",
    "port": 53,
    "read_only": false,
    "created_at": "2018-02-22T02:34:57.375Z",
    "updated_at": "2018-02-22T02:39:17.449Z"
}
```

This endpoint sort a statement.

`PUT http://www.dnsvault.net/api/v1/nodes/:node_id/dns/options/:option_id/statements/sort`

#### URL Parameters

Parameter | Description
--------- | -----------
Node_id | The ID of the option statement's node to retrieve
Option_id | The ID of the option statement's option to retrieve