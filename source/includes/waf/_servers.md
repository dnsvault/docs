## Servers

### List All Waf Servers


```shell
curl --include \
     --header "Authorization: Token iwwTXK54aahsosrx5JK7hkTe" \
  'http://www.dnsvault.net/api/v1/nodes/2/waf/server'
```

> The above command returns JSON structured like this:

```json
[
    {
        "id": 1,
        "node_id": 2,
        "template_id": 16,
        "host_id": 1,
        "ssl_mode": null,
        "servers": [
            {
                "server": "1.1.1.1",
                "status": "active",
                "weightage": "1"
            }
        ],
        "created_at": "2018-02-22T10:11:21.815Z",
        "updated_at": "2018-02-22T10:11:21.815Z"
    },
    {
        "id": 2,
        "node_id": 2,
        "template_id": 16,
        "host_id": 1,
        "ssl_mode": null,
        "servers": [
            {
                "server": "1.1.1.1",
                "status": "active",
                "weightage": "1"
            }
        ],
        "created_at": "2018-02-23T03:22:50.251Z",
        "updated_at": "2018-02-23T03:22:50.251Z"
    }
]
```

This endpoint retrieves all template.

##### HTTP Request

`GET http://www.dnsvault.net/api/v1/nodes/:node_id/waf/server`

##### URL Parameters

Parameter | Description
--------- | -----------
Node_id | The ID of the waf server's node to retrieve


### Show Waf Server 


```shell
curl --include \
     --header "Authorization: Token iwwTXK54aahsosrx5JK7hkTe" \
  'http://www.dnsvault.net/api/v1/nodes/2/waf/server/1'
```

> The above command returns JSON structured like this:

```json
{
    "id": 1,
    "node_id": 2,
    "template_id": 16,
    "host_id": 1,
    "ssl_mode": null,
    "servers": [
        {
            "server": "1.1.1.1",
            "status": "active",
            "weightage": "1"
        }
    ],
    "created_at": "2018-02-22T10:11:21.815Z",
    "updated_at": "2018-02-22T10:11:21.815Z"
}
```

This endpoint retrieve details of an waf server.

##### HTTP Request

`GET http://www.dnsvault.net/api/v1/nodes/:node_id/waf/server/:id`

##### URL Parameters

Parameter | Description
--------- | -----------
Node_id | The ID of the waf server's node to retrieve
Id | The ID of the waf server to retrieve

### Create Waf Server

You may create an waf server using this action. It takes a JSON object containing a parameters.

```shell
curl --include \
     --request POST \
     --header "Content-Type: application/json" \
     --data-binary "{
    \"node_id\": \"2\",
    \"host_id\": \"1\",
    \"template_id\": \"16\",
    \"servers\": 
    [{
        \"server\": \"1.1.1.1\",
        \"status\": \"active\",
        \"weightage\": \"1\"
    }]
}" \
'http://www.dnsvault.net/api/v1/nodes/2/waf/server'
```

> The above command returns JSON structured like this:

```json
{
    "id": 3,
    "node_id": 2,
    "template_id": 16,
    "host_id": 1,
    "ssl_mode": null,
    "servers": [
        {
            "server": "1.1.1.1",
            "status": "active",
            "weightage": "1"
        }
    ],
    "created_at": "2018-02-22T10:11:21.815Z",
    "updated_at": "2018-02-22T10:11:21.815Z"
}
```

This endpoint creates an waf server.

##### HTTP Request

`POST http://www.dnsvault.net/api/v1/nodes/:node_id/waf/server`

##### URL Parameters

Parameter | Description
--------- | -----------
Node_id | The ID of the waf server's node to retrieve

##### Required Arguments

Parameter | Description
--------- | -----------
Node_id | Node ID of the waf server node to retrieve
Host_id | Active host ID that are assigned to WAF
Template_id | Template ID of the waf server to retrieve
Server | Value of server address
Status | Active or Inactive
Weightage | Position of the server

### Update Server

```shell
curl --include \
     --request PUT \
     --header "Content-Type: application/json" \
     --data-binary "{
    \"template\": {
        \"node_id\": \"2\",
        \"host_id\": \"1\",
        \"template_id\": \"16\",
        \"servers\": 
        [{
            \"server\": \"192.0.0.0\",
            \"status\": \"active\",
            \"weightage\": \"1\"
        }]
    }
}" \
  'http://www.dnsvault.net/api/v1/nodes/2/waf/server/3'
```


> The above command returns JSON structured like this:

```json
{
    "id": 3,
    "node_id": 2,
    "template_id": 16,
    "host_id": 1,
    "ssl_mode": null,
    "servers": [
        {
            "server": "192.0.0.0",
            "status": "active",
            "weightage": "1"
        }
    ],
    "created_at": "2018-02-22T10:11:21.815Z",
    "updated_at": "2018-02-22T10:11:21.815Z"
}
```

This endpoint update a template.

##### HTTP Request

`PUT http://www.dnsvault.net/api/v1/nodes/:node_id/waf/server/:id`

Parameter | Description
--------- | -----------
Node_id | The ID of the waf server's node to retrieve
Id | The ID of the waf server to retrieve

##### Required Arguments

Parameter | Description
--------- | -----------
Node_id | Node ID of the waf server node to retrieve
Host_id | Active host ID that are assigned to WAF
Template_id | Template ID of the waf server to retrieve
Server | Value of server address
Status | Active or Inactive
Weightage | Position of the server

### Delete Server

```shell
curl --include \
     --request DELETE \
     --header "Authorization: Token iwwTXK54aahsosrx5JK7hkTe" \
  'http://www.dnsvault.net/api/v1/nodes/2/waf/server/3'
```


> The above command returns JSON structured like this:

```json
{
    "id": 3,
    "node_id": 2,
    "template_id": 16,
    "host_id": 1,
    "ssl_mode": null,
    "servers": [
        {
            "server": "192.0.0.0",
            "status": "active",
            "weightage": "1"
        }
    ],
    "created_at": "2018-02-22T10:11:21.815Z",
    "updated_at": "2018-02-22T10:11:21.815Z"
}
```

This endpoint delete a waf server.

##### HTTP Request

`DELETE http://www.dnsvault.net/api/v1/nodes/:node_id/waf/server/:id`

##### URL Parameters

Parameter | Description
--------- | -----------
Node_id | The ID of the waf server's node to retrieve
Id | The ID of the waf server to delete



