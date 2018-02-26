## View Statement

### List all Statement

You may list collection of View Statement using this action.

```shell
curl --include \
'http://www.dnsvault.net/api/v1/nodes/2/dns/views/51/statements'
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

#### HTTP Request

`GET http://www.dnsvault.net/api/v1/nodes/:node_id/dns/views/:view_id/statements`

#### URL Parameters

Parameter | Description
--------- | -----------
Node_id | The ID of the view statement's node to retrieve
View_id | The ID of the view statement's view to retrieve

### Show Statement

You may view detail of a statement using this action.

```shell
curl --include \
'http://www.dnsvault.net/api/v1/nodes/2/dns/views/51/statements/1'
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

#### HTTP Request

`GET http://www.dnsvault.net/api/v1/nodes/:node_id/dns/views/:view_id/statements/:id`

#### URL Parameters

Parameter | Description
--------- | -----------
Node_id | The ID of the view statement's node to retrieve
View_id | The ID of the view statement's view to retrieve
Id | The ID of the view statement to retrieve

### Create Statement

You may create a statement using this action. It takes a JSON object containing a parameters.

```shell
curl --include \
     --request POST \
     --header "Content-Type: application/json" \
     --data-binary "{
    \"statement\": \"match-clients\",
    \"value_type\": \"ip_address\",
    \"value\": \"172.0.0.0\"
}" \
'http://www.dnsvault.net/api/v1/nodes/2/dns/views/51/statements'
```

> The above command returns JSON structured like this:

```json
{
    "id": 2,
    "statement": "match-clients",
    "negate": false,
    "position": 1,
    "value_type": "ip_address",
    "value": "172.0.0.0",
    "status": "active",
    "port": 53,
    "read_only": false,
    "created_at": "2017-07-11T03:50:18.530Z",
    "updated_at": "2017-07-11T03:50:18.530Z"
}
```

This endpoint creates a statement.

#### HTTP Request

`POST http://www.dnsvault.net/api/v1/nodes/:node_id/dns/views/:view_id/statements`

#### URL Parameters

Parameter | Description
--------- | -----------
Node_id | The ID of the view statement's node to retrieve
View_id | The ID of the view statement's view to retrieve

#### Required Parameters

Parameter | Description
--------- | -----------
Statement |Name of the Statement
Value_type | Value type of the statement
Value | value of the statement

Statement | Value_type | Value
--------- | ---------- | -----
match_clients | ip_address | IP Address value
 | key | Key Value
 | geo | Geolocation Value
match_destinations | ip_address | IP Address value
recursion | boolean | Yes or No
allow-recursion | ip_address | IP Address value

### Delete a Statement

You may delete an statement using this action.

```shell
curl --include \
     --request DELETE \
'http://www.dnsvault.net/api/v1/nodes/2/dns/views/51/statements/1'
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

This endpoint creates a statement.

`DELETE http://www.dnsvault.net/api/v1/nodes/:node_id/dns/views/:view_id/statements/:id`

#### URL Parameters

Parameter | Description
--------- | -----------
Node_id | The ID of the view statement's node to retrieve
View_id | The ID of the view statement's view to retrieve
Id | The ID of the view statement to delete

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
'http://www.dnsvault.net/api/v1/nodes/2/dns/views/sort'
```

> The above command returns JSON structured like this:

```json
{
    "id": 2,
    "statement": "match-clients",
    "negate": false,
    "position": 0,
    "value_type": "ip_address",
    "value": "172.0.0.0",
    "status": "active",
    "port": 53,
    "read_only": false,
    "created_at": "2017-07-11T03:50:18.530Z",
    "updated_at": "2017-07-11T03:50:18.530Z"
},
{
    "id": 1,
    "statement": "match-clients",
    "negate": false,
    "position": 1,
    "value_type": "ip_address",
    "value": "1.1.1.1",
    "status": "active",
    "port": 53,
    "read_only": false,
    "created_at": "2017-07-11T03:50:18.530Z",
    "updated_at": "2017-07-11T03:50:18.530Z"
}
```

This endpoint sort a statement.

`PUT http://www.dnsvault.net/api/v1/nodes/:node_id/dns/views/sort`

#### URL Parameters

Parameter | Description
--------- | -----------
Node_id | The ID of the option statement's node to retrieve

