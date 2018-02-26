## Views

### Get All Views
You may list collection of view using this action. Default per page is 20 views, you can specify page and per_page parameters. e.g. http://srv1.dnsvault.net:3000/api/v1/views?page=1&per_page=20

```shell
curl --include \
     --header "Authorization: Token iwwTXK54aahsosrx5JK7hkTe" \
  'http://www.dnsvault.net/api/v1/nodes/2/dns/views'
```


> The above command returns JSON structured like this:

```json
[
    {
        "id": 50,
        "node_id": 2,
        "view_name": "cloudlocal",
        "description": "",
        "status": "active",
        "position": 0,
        "created_at": "2017-03-31T09:17:41.743Z",
        "updated_at": "2017-03-31T09:17:41.766Z"
    },
    {
        "id": 51,
        "node_id": 2,
        "view_name": "cloudint",
        "description": "",
        "status": "active",
        "position": 1,
        "created_at": "2017-03-31T09:17:55.173Z",
        "updated_at": "2017-03-31T09:17:55.192Z"
    },
    {
        "id": 56,
        "node_id": 2,
        "view_name": "huala",
        "description": "",
        "status": "active",
        "position": 2,
        "created_at": "2017-06-20T04:27:19.146Z",
        "updated_at": "2017-06-20T04:27:19.205Z"
    }
]
```

This endpoint get list of views.

#### HTTP Request

`GET http://www.dnsvault.net/api/v1/nodes/:node_id/dns/views`

#### URL Parameters

Parameter | Description
--------- | -----------
Node_id | The ID of the view's node to retrieve

### Get a View

```shell
curl --include \
     --header "Authorization: Token iwwTXK54aahsosrx5JK7hkTe" \
  'http://www.dnsvault.net/api/v1/nodes/2/dns/views/56'
```


> The above command returns JSON structured like this:

```json
{
    "id": 56,
    "node_id": 2,
    "view_name": "huala",
    "description": "",
    "status": "active",
    "position": 2,
    "created_at": "2017-06-20T04:27:19.146Z",
    "updated_at": "2017-06-20T04:27:19.205Z"
}
```

This endpoint get details of a view.

#### HTTP Request

`GET http://www.dnsvault.net/api/v1/nodes/:node_id/dns/views/:id`

#### URL Parameters

Parameter | Description
--------- | -----------
Node_id | The ID of the view's node to retrieve
Id | The ID of the views to retrieve

### Create View

```shell
curl --include \
     --request POST \
     --header "Content-Type: application/json" \
     --data-binary "{
    \"view\": {
        \"view_name\": \"dnsv\",
        \"description\": \"This is for internal network\"
    }
}" \
  'http://www.dnsvault.net/api/v1/nodes/2/dns/views'
```


> The above command returns JSON structured like this:

```json
{
    "id": 57,
    "node_id": 2,
    "view_name": "dnsv",
    "description": "This is for internal network",
    "status": "active",
    "position": 3,
    "created_at": "2017-06-20T04:27:19.146Z",
    "updated_at": "2017-06-20T04:27:19.205Z"
}
```

This endpoint create a views.

#### HTTP Request

`POST http://www.dnsvault.net/api/v1/nodes/:node_id/dns/views`

#### URL Parameters

Parameter | Description
--------- | -----------
Node_id | The ID of the view's node to retrieve

#### Required Parameters

Parameter | Description
--------- | -----------
view_name | View Name
description | Description of the view

### Update View

```shell
curl --include \
     --request PUT \
     --header "Content-Type: application/json" \
     --data-binary "{
    \"view\": {
        \"view_name\": \"dnsv\",
        \"description\": \"This is for external view\"
    }
}" \
  'http://www.dnsvault.net/api/v1/nodes/2/dns/views/57'
```


> The above command returns JSON structured like this:

```json

{
    "id": 57,
    "node_id": 2,
    "view_name": "dnsv",
    "description": "This is for external view",
    "status": "active",
    "position": 3,
    "created_at": "2017-06-20T04:27:19.146Z",
    "updated_at": "2017-06-20T04:27:19.205Z"
}
```

This endpoint update a views.

#### HTTP Request

`PUT http://www.dnsvault.net/api/v1/nodes/:node_id/dns/views/:id`

#### URL Parameters

Parameter | Description
--------- | -----------
Node_id | The ID of the view's node to retrieve
Id | The ID of the view to retrieve

#### Required Parameters

Parameter | Description
--------- | -----------
view_name | View Name
description | Description of a View

### Delete View

```shell
curl --include \
     --request DELETE \
     --header "Authorization: Token iwwTXK54aahsosrx5JK7hkTe" \
  'http://www.dnsvault.net/api/v1/nodes/2/dns/views/57'
```


> The above command returns JSON structured like this:

```json
{
    "id": 57,
    "node_id": 2,
    "view_name": "dnsv",
    "description": "This is for external view",
    "status": "active",
    "position": 3,
    "created_at": "2017-06-20T04:27:19.146Z",
    "updated_at": "2017-06-20T04:27:19.205Z"
}

```

This endpoint delete a view.

#### HTTP Request

`DELETE http://www.dnsvault.net/api/v1/nodes/:node_id/dns/views/:id`

#### URL Parameters

Parameter | Description
--------- | -----------
Node_id | The ID of the view's node to retrieve
Id | The ID of the view to delete

### Sort Statement

You may sort statements using this action.

```shell
curl --include \
     --request PUT \
     --header "Content-Type: application/json" \
     --data-binary "{
    {
    "id": "56",
    "position" : "0"
    }
}" \
'http://www.dnsvault.net/api/v1/nodes/2/dns/views/sort'
```

> The above command returns JSON structured like this:

```json
{
    "id": 56,
    "node_id": 2,
    "view_name": "huala",
    "description": "",
    "status": "active",
    "position": 0,
    "created_at": "2017-06-20T04:27:19.146Z",
    "updated_at": "2017-06-20T04:27:19.205Z"
},
{
    "id": 50,
    "node_id": 2,
    "view_name": "cloudlocal",
    "description": "",
    "status": "active",
    "position": 1,
    "created_at": "2017-03-31T09:17:41.743Z",
    "updated_at": "2017-03-31T09:17:41.766Z"
},
{
    "id": 51,
    "node_id": 2,
    "view_name": "cloudint",
    "description": "",
    "status": "active",
    "position": 2,
    "created_at": "2017-03-31T09:17:55.173Z",
    "updated_at": "2017-03-31T09:17:55.192Z"
}
```

This endpoint sort a statement.

`PUT http://www.dnsvault.net/api/v1/nodes/:node_id/dns/views/sort`

#### URL Parameters

Parameter | Description
--------- | -----------
Node_id | The ID of the option statement's node to retrieve
