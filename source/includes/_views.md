# Views

## Get All Views

```shell
curl --include \
     --header "Authorization: Token iCDDAftiii2hzpnQMCrK2gtt" \
  'http://www.dnsvault.net/views'
```


> The above command returns JSON structured like this:

```json
[
  {
    "id": 17,
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
]
```

This endpoint get list of views.

### HTTP Request

`GET http://www.dnsvault.net/views`

## Get View

```shell
curl --include \
     --header "Authorization: Token iCDDAftiii2hzpnQMCrK2gtt" \
  'http://www.dnsvault.net/views/2'
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

`GET http://www.dnsvault.net/views/:id`

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
  'http://www.dnsvault.net/views'
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

`POST http://www.dnsvault.net/views`

### URL Parameters

Parameter | Description
--------- | -----------
view_name | View Name
description | Description Of View

## Update View

```shell
curl --include \
     --request POST \
     --header "Content-Type: application/json" \
     --data-binary "{
    \"view\": {
        \"description\": \"This is for internal network\"
    }
}" \
  'http://www.dnsvault.net/views/18'
```


> The above command returns JSON structured like this:

```json

{
  "errors": {
    "object": "view_id",
    "reason": "Couldn't find View with view_id 19"
  },
  "code": 422,
  "params": {
    "description": "change description",
    "controller": "api/v1/views",
    "action": "update",
    "node_id": "7",
    "id": "19",
    "view": {
      "description": "change description"
    }
  }
}
```

This endpoint update a views.

### HTTP Request

`PUT http://www.dnsvault.net/views/:id`

### URL Parameters

Parameter | Description
--------- | -----------
description | Description Of View

## Delete View

```shell
curl --include \
     --header "Authorization: Token iCDDAftiii2hzpnQMCrK2gtt" \
  'http://www.dnsvault.net/views/2'
```


> The above command returns JSON structured like this:

```json
{
  "errors": {
    "object": "view_id",
    "reason": "Couldn't find View with view_id 10"
  },
  "code": 422,
  "params": {
    "description": "change description",
    "controller": "api/v1/views",
    "action": "destroy",
    "node_id": "7",
    "id": "10",
    "view": {
      "description": "change description"
    }
  }
}
```

This endpoint delete a view.

### HTTP Request

`DELETE http://www.dnsvault.net/views/:id`
