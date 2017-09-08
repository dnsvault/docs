# Access Control List

## List all Acls

You may list collection of ACL using this action. Default per page is 20.

```shell
curl --include \
     --header "Authorization: Token iwwTXK54aahsosrx5JK7hkTe" \
'http://www.dnsvault.net/api/v1/nodes/2/dns/acls'
```

> The above command returns JSON structured like this:

```json
[
  {
    "id": 2,
    "acl_name": "internal",
    "description": "This is for internal network",
    "status": true,
    "created_at": "2016-01-17T07:57:17.493Z",
    "updated_at": "2016-01-17T07:57:17.493Z"
  },
  {
    "id": 3,
    "acl_name": "ainternal",
    "description": "This is for internal network",
    "status": true,
    "created_at": "2016-01-17T08:05:18.939Z",
    "updated_at": "2016-01-17T08:05:18.939Z"
  }
]
```

This endpoint retrieves all acl.

### HTTP Request

`GET http://www.dnsvault.net/api/v1/nodes/:node_id/dns/acls`

## Show Acl

You may show an ACL using this action. 

```shell
curl --include \
     --header "Authorization: Token iwwTXK54aahsosrx5JK7hkTe" \
'http://www.dnsvault.net/api/v1/nodes/2/dns/acls/36'
```

> The above command returns JSON structured like this:

```json
{
    "id": 36,
    "node_id": 2,
    "acl_name": "blacklist6",
    "description": "This is for internal network",
    "status": "active",
    "read_only": false,
    "created_at": "2017-07-11T02:45:34.625Z",
    "updated_at": "2017-07-11T02:45:34.625Z"
}
```

This endpoint shows detail of an acl.

### HTTP Request

`GET http://www.dnsvault.net/api/v1/nodes/:node_id/dns/acls/:id`


## Create Acl

You may create a ACL using this action. It takes a JSON object containing a parameters.

```shell
curl --include \
     --request POST \
     --header "Content-Type: application/json" \
     --data-binary "{
    \"acl_name\": \"blacklist6\",
    \"description\": \"This is for internal network\"
}" \
'http://www.dnsvault.net/api/v1/nodes/2/dns/acls'
```

> The above command returns JSON structured like this:

```json
{
    "id": 36,
    "node_id": 2,
    "acl_name": "blacklist6",
    "description": "This is for internal network",
    "status": "active",
    "read_only": false,
    "created_at": "2017-07-11T02:45:34.625Z",
    "updated_at": "2017-07-11T02:45:34.625Z"
}
```

This endpoint creates an acl.

### HTTP Request

`POST http://www.dnsvault.net/api/v1/nodes/:node_id/dns/acls`

## Delete Acl

You may delete an ACL using this action.

```shell
curl --include \
     --request DELETE \
     --header "Content-Type: application/json" \
'http://www.dnsvault.net/api/v1/nodes/2/dns/acls/36'
```

> The above command returns JSON structured like this:

```json
{
    "id": 36,
    "node_id": 2,
    "acl_name": "blacklist6",
    "description": "This is for internal network",
    "status": "active",
    "read_only": false,
    "created_at": "2017-07-11T02:45:34.625Z",
    "updated_at": "2017-07-11T02:45:34.625Z"
}
```

This endpoint creates an acl.

`DELETE http://www.dnsvault.net/api/v1/nodes/:node_id/dns/acls/:id`

