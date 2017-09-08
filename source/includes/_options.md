# Options

## Get All Options


```shell
curl --include \
     --header "Authorization: Token iwwTXK54aahsosrx5JK7hkTe" \
  'http://www.dnsvault.net/api/v1/nodes/1/options'
```

> The above command returns JSON structured like this:

```json
[
    {
        "id": 3,
        "statement": "listen-on-ipv4",
        "statement_value": "address",
        "status": "active",
        "category": null,
        "description": null,
        "created_at": "2017-08-17T05:09:45.697Z",
        "updated_at": "2017-08-18T04:01:35.311Z"
    },
    {
        "id": 4,
        "statement": "listen-on-ipv6",
        "statement_value": "address",
        "status": "active",
        "category": null,
        "description": null,
        "created_at": "2017-08-17T05:09:45.751Z",
        "updated_at": "2017-08-18T04:01:45.518Z"
    }
]
```

This endpoint retrieves all options.

### HTTP Request

`GET http://www.dnsvault.net/api/v1/nodes/1/options`


## Get an Option 


```shell
curl --include \
     --header "Authorization: Token iwwTXK54aahsosrx5JK7hkTe" \
  'http://www.dnsvault.net/api/v1/nodes/1/options/3'
```

> The above command returns JSON structured like this:

```json
{
    "id": 3,
    "statement": "listen-on-ipv4",
    "statement_value": "address",
    "status": "active",
    "category": null,
    "description": null,
    "created_at": "2017-08-17T05:09:45.697Z",
    "updated_at": "2017-08-18T04:01:35.311Z"
}
```

This endpoint retrieve details of an option.

### HTTP Request

`GET http://www.dnsvault.net/api/v1/nodes/1/options/:id`

### URL Parameters

Parameter | Description
--------- | -----------
Id | The ID of the option to retrieve

## Create Option

You may create an option using this action. It takes a JSON object containing a parameters.

```shell
curl --include \
     --request POST \
     --header "Content-Type: application/json" \
     --data-binary "{
    \"acl_name\": \"blacklist6\",
    \"description\": \"This is for internal network\"
}" \
'http://www.dnsvault.net/api/v1/nodes/2/dns/options'
```

> The above command returns JSON structured like this:

```json
{
    "id": 3,
    "statement": "listen-on-ipv4",
    "statement_value": "address",
    "status": "active",
    "category": null,
    "description": null,
    "created_at": "2017-08-17T05:09:45.697Z",
    "updated_at": "2017-08-18T04:01:35.311Z"
}
```

This endpoint creates an option.

### HTTP Request

`POST http://www.dnsvault.net/api/v1/nodes/:node_id/dns/options`

### Required Arguments

Parameter | Description
--------- | -----------
statement | Name of a statement, such as 'listen-on-ipv4'
statement_value | Value of a statement, such as 'address'

## Update Option

```shell
curl --include \
     --request PUT \
     --header "Content-Type: application/json" \
     --data-binary "{
    \"option\": {
        \"description\": \"This is for internal network\"
    }
}" \
  'http://www.dnsvault.net/api/v1/nodes/2/dns/options/18'
```


> The above command returns JSON structured like this:

```json
{
    "id": 3,
    "statement": "listen-on-ipv4",
    "statement_value": "address",
    "status": "active",
    "category": null,
    "description": null,
    "created_at": "2017-08-17T05:09:45.697Z",
    "updated_at": "2017-08-18T04:01:35.311Z"
}
```

This endpoint update a options.

### HTTP Request

`PUT http://www.dnsvault.net/api/v1/nodes/:node_id/dns/options/:id`

### Required Arguments

Parameter | Description
--------- | -----------
statement | Name of a statement, such as 'listen-on-ipv4'
statement_value | Value of a statement, such as 'address'

## Delete Option

```shell
curl --include \
     --request DELETE \
     --header "Authorization: Token iwwTXK54aahsosrx5JK7hkTe" \
  'http://www.dnsvault.net/api/v1/nodes/2/dns/options/2'
```


> The above command returns JSON structured like this:

```json
{
    "id": 3,
    "statement": "listen-on-ipv4",
    "statement_value": "address",
    "status": "active",
    "category": null,
    "description": null,
    "created_at": "2017-08-17T05:09:45.697Z",
    "updated_at": "2017-08-18T04:01:35.311Z"
}
```

This endpoint delete a option.

### HTTP Request

`DELETE http://www.dnsvault.net/api/v1/nodes/:node_id/dns/options/:id`

### URL Parameters

Parameter | Description
--------- | -----------
Id | The ID of the option to delete
