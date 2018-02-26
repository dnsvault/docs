## Templates

### List All Waf Templates


```shell
curl --include \
     --header "Authorization: Token iwwTXK54aahsosrx5JK7hkTe" \
  'http://www.dnsvault.net/api/v1/nodes/2/waf/templates'
```

> The above command returns JSON structured like this:

```json
[
    {
        "id": 1,
        "name": "default",
        "description": "default template",
        "status": null
    },
    {
        "id": 2,
        "name": "dnsv",
        "description": "dnsv template",
        "status": null
    }
]
```

This endpoint retrieves all template.

##### HTTP Request

`GET http://www.dnsvault.net/api/v1/nodes/:node_id/waf/templates`

##### URL Parameters

Parameter | Description
--------- | -----------
Node_id | The ID of the waf templates's node to retrieve


### Show Waf Template 


```shell
curl --include \
     --header "Authorization: Token iwwTXK54aahsosrx5JK7hkTe" \
  'http://www.dnsvault.net/api/v1/nodes/2/waf/templates/1'
```

> The above command returns JSON structured like this:

```json
{
    "id": 1,
    "name": "default",
    "description": "default template",
    "status": null
}
```

This endpoint retrieve details of an waf templates.

##### HTTP Request

`GET http://www.dnsvault.net/api/v1/nodes/:node_id/waf/templates/:id`

##### URL Parameters

Parameter | Description
--------- | -----------
Node_id | The ID of the waf templates's node to retrieve
Id | The ID of the waf templates to retrieve

### Create Waf Template

You may create an waf templates using this action. It takes a JSON object containing a parameters.

```shell
curl --include \
     --request POST \
     --header "Content-Type: application/json" \
     --data-binary "{
    \"name\": \"local\",
    \"description\": \"local template\"
}" \
'http://www.dnsvault.net/api/v1/nodes/2/waf/templates'
```

> The above command returns JSON structured like this:

```json
{
    "id": 3,
    "name": "local",
    "description": "local template",
    "status": null,
    "created_at": "2018-02-22T08:15:55.186Z",
    "updated_at": "2018-02-22T08:15:55.186Z"
}
```

This endpoint creates an waf templates.

##### HTTP Request

`POST http://www.dnsvault.net/api/v1/nodes/:node_id/waf/templates`

##### URL Parameters

Parameter | Description
--------- | -----------
Node_id | The ID of the waf templates's node to retrieve

##### Required Arguments

Parameter | Description
--------- | -----------
Name | Name of the waf template
Description | Description of the template

### Update Template

```shell
curl --include \
     --request PUT \
     --header "Content-Type: application/json" \
     --data-binary "{
    \"template\": {
        \"name\": \"local\",
        \"description\": \"update: local template\"
    }
}" \
  'http://www.dnsvault.net/api/v1/nodes/2/waf/templates/3'
```


> The above command returns JSON structured like this:

```json
{
    "id": 3,
    "name": "local",
    "description": "update: local template",
    "status": null,
    "created_at": "2018-02-22T08:15:55.186Z",
    "updated_at": "2018-02-22T08:15:55.186Z"
}
```

This endpoint update a template.

##### HTTP Request

`PUT http://www.dnsvault.net/api/v1/nodes/:node_id/waf/templates/:id`

##### URL Parameters

Parameter | Description
--------- | -----------
Node_id | The ID of the waf templates's node to retrieve
Id | The ID of the waf templates to retrieve

##### Required Arguments

Parameter | Description
--------- | -----------
Name | Name of the waf template
Description | Description of the template

### Delete Template

```shell
curl --include \
     --request DELETE \
     --header "Authorization: Token iwwTXK54aahsosrx5JK7hkTe" \
  'http://www.dnsvault.net/api/v1/nodes/2/waf/templates/2'
```


> The above command returns JSON structured like this:

```json
{
    "id": 2,
    "name": "dnsv",
    "description": "dnsv template",
    "status": null
}
```

This endpoint delete a waf templates.

##### HTTP Request

`DELETE http://www.dnsvault.net/api/v1/nodes/:node_id/waf/templates/:id`

##### URL Parameters

Parameter | Description
--------- | -----------
Node_id | The ID of the waf templates's node to retrieve
Id | The ID of the waf templates to delete
