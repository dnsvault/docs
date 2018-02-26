## Whitelists

### List All Whitelists


```shell
curl --include \
     --header "Authorization: Token iwwTXK54aahsosrx5JK7hkTe" \
  'http://www.dnsvault.net/api/v1/nodes/2/waf/templates/1/whitelists'
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

This endpoint retrieves all whitelist.

##### HTTP Request

`GET http://www.dnsvault.net/api/v1/nodes/:node_id/waf/templates/:template_id/whitelists`

##### URL Parameters

Parameter | Description
--------- | -----------
Node_id | The ID of the waf whitelist's node to retrieve
Template_id | The ID of the waf whitelist's template to retrieve


### Show Whitelist 


```shell
curl --include \
     --header "Authorization: Token iwwTXK54aahsosrx5JK7hkTe" \
  'http://www.dnsvault.net/api/v1/nodes/2/waf/templates/1/whitelists/2'
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

This endpoint retrieve details of an waf whitelists.

##### HTTP Request

`GET http://www.dnsvault.net/api/v1/nodes/:node_id/waf/templates/:template_id/whitelists/:id`

##### URL Parameters

Parameter | Description
--------- | -----------
Node_id | The ID of the waf whitelist's node to retrieve
Template_id | The ID of the waf whitelist's template to retrieve
Id | The ID of the waf whitelists to retrieve

### Create Whitelist

You may create an waf whitelists using this action. It takes a JSON object containing a parameters.

```shell
curl --include \
     --request POST \
     --header "Content-Type: application/json" \
     --data-binary "{
    \"address\": \"172.0.0.0\"
}" \
'http://www.dnsvault.net/api/v1/nodes/2/waf/templates/1/whitelists'
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

This endpoint creates an waf whitelists.

##### HTTP Request

`POST http://www.dnsvault.net/api/v1/nodes/:node_id/waf/templates/:template_id/whitelists`

##### URL Parameters

Parameter | Description
--------- | -----------
Node_id | The ID of the waf whitelist's node to retrieve
Template_id | The ID of the waf whitelist's template to retrieve

##### Required Arguments

Parameter | Description
--------- | -----------
Address | Ip address of the waf whitelist

### Update Whitelist

```shell
curl --include \
     --request PUT \
     --header "Content-Type: application/json" \
     --data-binary "{
    \"whitelist\": {
        \"address\": \"172.0.0.1\"
    }
}" \
  'http://www.dnsvault.net/api/v1/nodes/2/waf/templates/1/whitelists/3'
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

This endpoint update a whitelist.

##### HTTP Request

`PUT http://www.dnsvault.net/api/v1/nodes/:node_id/waf/templates/:template_id/whitelists/:id`

##### URL Parameters

Parameter | Description
--------- | -----------
Node_id | The ID of the waf whitelist's node to retrieve
Template_id | The ID of the waf whitelist's template to retrieve
Id | The ID of the waf whitelists to retrieve

##### Required Arguments

Parameter | Description
--------- | -----------
Address | Ip address of the waf whitelist

### Delete Whitelist

```shell
curl --include \
     --request DELETE \
     --header "Authorization: Token iwwTXK54aahsosrx5JK7hkTe" \
  'http://www.dnsvault.net/api/v1/nodes/2/waf/templates/1/whitelists/3'
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

This endpoint delete a waf whitelists.

##### HTTP Request

`DELETE http://www.dnsvault.net/api/v1/nodes/:node_id/waf/templates/:template_id/whitelists/:id`

##### URL Parameters

Parameter | Description
--------- | -----------
Node_id | The ID of the waf whitelist's node to retrieve
Template_id | The ID of the waf whitelist's template to retrieve
Id | The ID of the waf whitelists to retrieve
