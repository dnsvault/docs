## DNS Options

### Get All Options


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

##### HTTP Request

`GET http://www.dnsvault.net/api/v1/nodes/:node_id/options`

##### URL Parameters

Parameter | Description
--------- | -----------
Node_id | The ID of the option's node to retrieve


### Get an Option 


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

##### HTTP Request

`GET http://www.dnsvault.net/api/v1/nodes/:node_id/options/:id`

##### URL Parameters

Parameter | Description
--------- | -----------
Node_id | The ID of the option's node to retrieve
Id | The ID of the option to retrieve

### Update Option

```shell
curl --include \
     --request PUT \
     --header "Content-Type: application/json" \
     --data-binary "{
    \"option\": {
        \"statement\": \"blackhole\",
        \"statement_value\": \"acl\"
    }
}" \
  'http://www.dnsvault.net/api/v1/nodes/1/dns/options/18'
```


> The above command returns JSON structured like this:

```json
{
    "id": 18,
    "node_id": 1,
    "statement": "blackhole",
    "statement_value": "acl",
    "status": "active",
    "category": "queries",
    "description": null,
    "created_at": "2018-02-02T04:47:52.326Z",
    "updated_at": "2018-02-02T04:47:52.326Z"
}
```

This endpoint update a options.

##### HTTP Request

`PUT http://www.dnsvault.net/api/v1/nodes/:node_id/dns/options/:id`

##### URL Parameters

Parameter | Description
--------- | -----------
Node_id | The ID of the option's node to retrieve
Id | The ID of the option to retrieve

##### Required Arguments

Parameter | Description
--------- | -----------
statement | Name of a statement, such as 'listen-on-ipv4'
statement_value | Value of a statement, such as 'address'

Statement | Statement_value
--------- | ---------------
blackhole | ip_address
 | acl
allow-recursion | ip_address
 | acl
forward | none
 | first
 | only
recursion | yes OR no
auth-nxdomain | yes OR no
dnssec-validation | yes OR no
