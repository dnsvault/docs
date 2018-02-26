## Blacklists

### List All Blacklist


```shell
curl --include \
     --header "Authorization: Token iwwTXK54aahsosrx5JK7hkTe" \
  'http://www.dnsvault.net/api/v1/nodes/2/waf/templates/1/blacklists'
```

> The above command returns JSON structured like this:

```json
[
    {
        "id": 1,
        "address": "1.1.1.2",
        "kind": "ip",
        "status": null,
        "created_at": "2018-02-21T03:40:07.439Z",
        "updated_at": "2018-02-21T03:40:07.439Z"
    },
    {
        "id": 2,
        "address": "1.1.1.72",
        "kind": "ip",
        "status": null,
        "created_at": "2018-02-21T03:31:28.878Z",
        "updated_at": "2018-02-21T03:41:42.345Z"
    }
]
```

This endpoint retrieves all blacklist.

##### HTTP Request

`GET http://www.dnsvault.net/api/v1/nodes/:node_id/waf/templates/:template_id/blacklists`

##### URL Parameters

Parameter | Description
--------- | -----------
Node_id | The ID of the waf blacklist's node to retrieve
Template_id | The ID of the waf blacklist's template to retrieve


### Show Blacklist 


```shell
curl --include \
     --header "Authorization: Token iwwTXK54aahsosrx5JK7hkTe" \
  'http://www.dnsvault.net/api/v1/nodes/2/waf/templates/1/blacklists/2'
```

> The above command returns JSON structured like this:

```json
{
  "id": 2,
  "address": "1.1.1.72",
  "kind": "ip",
  "status": null,
  "created_at": "2018-02-21T03:31:28.878Z",
  "updated_at": "2018-02-21T03:41:42.345Z"
}
```

This endpoint retrieve details of an waf blacklists.

##### HTTP Request

`GET http://www.dnsvault.net/api/v1/nodes/:node_id/waf/templates/:template_id/blacklists/:id`

##### URL Parameters

Parameter | Description
--------- | -----------
Node_id | The ID of the waf blacklist's node to retrieve
Template_id | The ID of the waf blacklist's template to retrieve
Id | The ID of the waf blacklists to retrieve

### Create Blacklist

You may create an waf blacklists using this action. It takes a JSON object containing a parameters.

```shell
curl --include \
     --request POST \
     --header "Content-Type: application/json" \
     --data-binary "{
    \"address\": \"172.0.0.0\"
}" \
'http://www.dnsvault.net/api/v1/nodes/2/waf/templates/1/blacklists'
```

> The above command returns JSON structured like this:

```json
{
  "id": 3,
  "address": "172.0.0.0",
  "kind": "ip",
  "status": null,
  "created_at": "2018-02-21T03:31:28.878Z",
  "updated_at": "2018-02-21T03:41:42.345Z"
}
```

This endpoint creates an waf blacklists.

##### HTTP Request

`POST http://www.dnsvault.net/api/v1/nodes/:node_id/waf/templates/:template_id/blacklists`

##### URL Parameters

Parameter | Description
--------- | -----------
Node_id | The ID of the waf blacklist's node to retrieve
Template_id | The ID of the waf blacklist's template to retrieve

##### Required Arguments

Parameter | Description
--------- | -----------
Address | Ip address of the waf blacklist

### Update Blacklist

```shell
curl --include \
     --request PUT \
     --header "Content-Type: application/json" \
     --data-binary "{
    \"blacklist\": {
        \"address\": \"172.0.0.1\"
    }
}" \
  'http://www.dnsvault.net/api/v1/nodes/2/waf/templates/1/blacklists/3'
```


> The above command returns JSON structured like this:

```json
{
  "id": 3,
  "address": "172.0.0.1",
  "kind": "ip",
  "status": null,
  "created_at": "2018-02-21T03:31:28.878Z",
  "updated_at": "2018-02-21T03:41:42.345Z"
}
```

This endpoint update a blacklist.

##### HTTP Request

`PUT http://www.dnsvault.net/api/v1/nodes/:node_id/waf/templates/:template_id/blacklists/:id`

##### URL Parameters

Parameter | Description
--------- | -----------
Node_id | The ID of the waf blacklist's node to retrieve
Template_id | The ID of the waf blacklist's template to retrieve
Id | The ID of the waf blacklists to retrieve

##### Required Arguments

Parameter | Description
--------- | -----------
Address | Ip address of the waf blacklist

### Delete Blacklists

```shell
curl --include \
     --request DELETE \
     --header "Authorization: Token iwwTXK54aahsosrx5JK7hkTe" \
  'http://www.dnsvault.net/api/v1/nodes/2/waf/templates/1/blacklists/3'
```


> The above command returns JSON structured like this:

```json
{
  "id": 3,
  "address": "172.0.0.1",
  "kind": "ip",
  "status": null,
  "created_at": "2018-02-21T03:31:28.878Z",
  "updated_at": "2018-02-21T03:41:42.345Z"
}
```

This endpoint delete a waf blacklists.

##### HTTP Request

`DELETE http://www.dnsvault.net/api/v1/nodes/:node_id/waf/templates/:template_id/blacklists/:id`

##### URL Parameters

Parameter | Description
--------- | -----------
Node_id | The ID of the waf blacklist's node to retrieve
Template_id | The ID of the waf blacklist's template to retrieve
Id | The ID of the waf blacklists to retrieve
