# Views

## Get All Views
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

### HTTP Request

`GET http://www.dnsvault.net/api/v1/nodes/:node_id/dns/views`

## Get a View

```shell
curl --include \
     --header "Authorization: Token iwwTXK54aahsosrx5JK7hkTe" \
  'http://www.dnsvault.net/api/v1/nodes/2/dns/views/2'
```


> The above command returns JSON structured like this:

```json
{
  "id": 2,
  "view_name": "roxme",
  "description": "This is for internal network",
  "status": true,
  "position": 1,
  "created_at": "2016-06-25T04:42:39.111Z",
  "updated_at": "2016-06-25T04:42:39.146Z",
  "node_id": 7,
  "node": {
    "id": 7,
    "node_name": "elastic2.dnsvault.net",
    "description": null,
    "created_at": "2016-06-23T03:44:19.064Z",
    "updated_at": "2016-06-23T03:44:19.064Z",
    "tag": "agent",
    "fingerprint": "83:81:16:F1:6C:B3:F3:F2:40:F1:0E:6E:34:22:55:C5:F9:73:D4:DA:B2:78:4D:2F:12:11:B9:3A:8C:D2:D4:3B",
    "fingerprint_algorithm": "SHA256"
  }
}
```

This endpoint get details of a view.

### HTTP Request

`GET http://www.dnsvault.net/api/v1/nodes/:node_id/dns/views/:id`

### URL Parameters

Parameter | Description
--------- | -----------
Id | The ID of the views to retrieve

## Create View

```shell
curl --include \
     --request POST \
     --header "Content-Type: application/json" \
     --data-binary "{
    \"view\": {
        \"view_name\": \"internal\",
        \"description\": \"This is for internal network\"
    }
}" \
  'http://www.dnsvault.net/api/v1/nodes/2/dns/views'
```


> The above command returns JSON structured like this:

```json
{
  "id": 18,
  "view_name": "internal",
  "description": "This is for internal network",
  "status": true,
  "position": 2,
  "created_at": "2016-06-25T05:18:20.646Z",
  "updated_at": "2016-06-25T05:18:20.646Z",
  "node_id": 7,
  "node": {
    "id": 7,
    "node_name": "elastic2.dnsvault.net",
    "description": null,
    "created_at": "2016-06-23T03:44:19.064Z",
    "updated_at": "2016-06-23T03:44:19.064Z",
    "tag": "agent",
    "fingerprint": "83:81:16:F1:6C:B3:F3:F2:40:F1:0E:6E:34:22:55:C5:F9:73:D4:DA:B2:78:4D:2F:12:11:B9:3A:8C:D2:D4:3B",
    "fingerprint_algorithm": "SHA256"
  }
}
```

This endpoint create a views.

### HTTP Request

`POST http://www.dnsvault.net/api/v1/nodes/:node_id/dns/views`

### URL Parameters

Parameter | Description
--------- | -----------
view_name | View Name
description | Description Of View

## Update View

```shell
curl --include \
     --request PUT \
     --header "Content-Type: application/json" \
     --data-binary "{
    \"view\": {
        \"description\": \"This is for internal network\"
    }
}" \
  'http://www.dnsvault.net/api/v1/nodes/2/dns/views/18'
```


> The above command returns JSON structured like this:

```json

{
  "id": 18,
  "view_name": "internal",
  "description": "YOLO",
  "status": true,
  "position": 2,
  "created_at": "2016-06-25T05:18:20.646Z",
  "updated_at": "2016-06-25T05:18:20.646Z",
  "node_id": 7,
  "node": {
    "id": 7,
    "node_name": "elastic2.dnsvault.net",
    "description": null,
    "created_at": "2016-06-23T03:44:19.064Z",
    "updated_at": "2016-06-23T03:44:19.064Z",
    "tag": "agent",
    "fingerprint": "83:81:16:F1:6C:B3:F3:F2:40:F1:0E:6E:34:22:55:C5:F9:73:D4:DA:B2:78:4D:2F:12:11:B9:3A:8C:D2:D4:3B",
    "fingerprint_algorithm": "SHA256"
  }
}

```

This endpoint update a views.

### HTTP Request

`PUT http://www.dnsvault.net/api/v1/nodes/:node_id/dns/views/:id`

### URL Parameters

Parameter | Description
--------- | -----------
description | Description of a View

## Delete View

```shell
curl --include \
     --request DELETE \
     --header "Authorization: Token iwwTXK54aahsosrx5JK7hkTe" \
  'http://www.dnsvault.net/api/v1/nodes/2/dns/views/18'
```


> The above command returns JSON structured like this:

```json
{
  "id": 18,
  "view_name": "internal",
  "description": "This is for internal network",
  "status": true,
  "position": 2,
  "created_at": "2016-06-25T05:18:20.646Z",
  "updated_at": "2016-06-25T05:18:20.646Z",
  "node_id": 7,
  "node": {
    "id": 7,
    "node_name": "elastic2.dnsvault.net",
    "description": null,
    "created_at": "2016-06-23T03:44:19.064Z",
    "updated_at": "2016-06-23T03:44:19.064Z",
    "tag": "agent",
    "fingerprint": "83:81:16:F1:6C:B3:F3:F2:40:F1:0E:6E:34:22:55:C5:F9:73:D4:DA:B2:78:4D:2F:12:11:B9:3A:8C:D2:D4:3B",
    "fingerprint_algorithm": "SHA256"
  }
}

```

This endpoint delete a view.

### HTTP Request

`DELETE http://www.dnsvault.net/api/v1/nodes/:node_id/dns/views/:id`

### URL Parameters

Parameter | Description
--------- | -----------
Id | The ID of the option to retrieve
