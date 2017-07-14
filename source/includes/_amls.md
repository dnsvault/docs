# Address Match List

## List all Amls

You may list collection of AML using this action. Default per page is 20.

```shell
curl --include \
'http://www.dnsvault.net/api/v1/nodes/2/dns/acls/36/amls'
```

> The above command returns JSON structured like this:

```json
[
  {
    "id": 1,
    "acl_name_id": 2,
    "address": "1.1.1.1",
    "position": 1,
    "negate": false,
    "status": true,
    "read_only": false,
    "created_at": "2016-01-17T14:56:49.161Z",
    "updated_at": "2016-01-17T14:56:49.161Z"
  },
  {
    "id": 2,
    "acl_name_id": 2,
    "address": "192.168.1.0/24",
    "position": 2,
    "negate": false,
    "status": true,
    "read_only": false,
    "created_at": "2016-01-17T14:58:07.066Z",
    "updated_at": "2016-01-17T14:58:07.066Z"
  },
  {
    "id": 3,
    "acl_name_id": 2,
    "address": "192.168.0.0/16",
    "position": 3,
    "negate": false,
    "status": true,
    "read_only": false,
    "created_at": "2016-01-17T14:58:40.282Z",
    "updated_at": "2016-01-17T14:58:40.282Z"
  }
]
```

This endpoint retrieves all aml.

### HTTP Request

`GET http://www.dnsvault.net/api/v1/nodes/:node_id/dns/acls/:acl_id/amls`

## Create Aml

You may create a AML using this action. It takes a JSON object containing a parameters.

```shell
curl --include \
     --request POST \
     --header "Content-Type: application/json" \
     --data-binary "{
    \"address\": \"1.1.1.28\",
    \"negate\": \"true\"
}" \
'http://www.dnsvault.net/api/v1/nodes/2/dns/acls/30/amls'
```

> The above command returns JSON structured like this:

```json
{
    "id": 24,
    "acl_id": 30,
    "value_type": null,
    "value": null,
    "address": "1.1.1.28",
    "position": 1,
    "negate": true,
    "status": "active",
    "read_only": false,
    "created_at": "2017-07-11T03:06:24.184Z",
    "updated_at": "2017-07-11T03:06:24.184Z"
}
```

This endpoint creates an aml.

### HTTP Request

`POST http://www.dnsvault.net/api/v1/nodes/:node_id/dns/acls/:acl_id/amls`

## Show Aml

You may list collection of AML using this action. Default per page is 20.

```shell
curl --include \
'http://www.dnsvault.net/api/v1/nodes/2/dns/acls/30/amls/24'
```

> The above command returns JSON structured like this:

```json
{
    "id": 24,
    "acl_id": 30,
    "address": "1.1.1.28",
    "position": 1,
    "negate": true,
    "status": "active",
    "read_only": false,
    "created_at": "2017-07-11T03:06:24.184Z",
    "updated_at": "2017-07-11T03:06:24.184Z"
}
```

This endpoint retrieves an aml.

### HTTP Request

`GET http://www.dnsvault.net/api/v1/nodes/:node_id/dns/acls/:acl_id/amls/:id`

## Delete Aml

You may delete an AML using this action.

```shell
curl --include \
     --request DELETE \
'http://www.dnsvault.net/api/v1/nodes/2/dns/acls/30/amls/24'
```

> The above command returns JSON structured like this:

```json
{
    "id": 24,
    "acl_id": 30,
    "address": "1.1.1.28",
    "position": 1,
    "negate": true,
    "status": "active",
    "read_only": false,
    "created_at": "2017-07-11T03:06:24.184Z",
    "updated_at": "2017-07-11T03:06:24.184Z"
}
```

This endpoint delete an aml.

### HTTP Request

`DELETE http://www.dnsvault.net/api/v1/nodes/:node_id/dns/acls/:acl_id/amls/:id`

