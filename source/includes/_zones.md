# Zones

## List all Zones
You may list collection of zones using this action.

```shell
curl --include \
     --header "Content-Type: application/json" \
     --header "Authorization: Token iCDDAftiii2hzpnQMCrK2gtt" \
  'http://www.dnsvault.net/api/v1/nodes/4/dns/views/5/zones'
```

> The above command returns JSON structured like this:

```json
[
  {
    "view_id": 1,
    "zone_name": "amir.my",
    "description": "Amir's domain name",
    "zone_type": "master",
    "status": true,
    "processing_status": true,
    "backend_status": false,
    "delete_status": false,
    "boolean": false,
    "position": 1,
    "created_at": "2015-12-22T10:42:33.802Z",
    "updated_at": "2015-12-22T10:42:38.387Z"
  }
]
```

This endpoint get list of zones.

### HTTP Request

`GET http://www.dnsvault.net/views/:id/zones`



## Show Zone

You may list a zone using this action.

```shell
curl --include \
     --header "Authorization: Token iCDDAftiii2hzpnQMCrK2gtt" \
  'http://www.dnsvault.net/api/v1/nodes/4/dns/views/5/zones/5'
```

> The above command returns JSON structured like this:

```json
[
    {
      "view_id": 1,
      "zone_name": "amir.my",
      "description": "Amir's domain name",
      "zone_type": "master",
      "status": true,
      "processing_status": true,
      "backend_status": false,
      "delete_status": false,
      "boolean": false,
      "position": 1,
      "created_at": "2015-12-22T10:42:33.802Z",
      "updated_at": "2015-12-22T10:42:38.387Z"
    }
]
```

This endpoint get list of zones.

### HTTP Request

`GET http://www.dnsvault.net/api/v1/nodes/:node_id/dns/views/:view_id/zones/:id`


## Create Zone

You may create a zone using this action. It takes a JSON object containing a parameters.

```shell
curl --include \
     --request POST \
     --header "Content-Type: application/json" \
     --header "Authorization: Token iCDDAftiii2hzpnQMCrK2gtt" \
     --data-binary "{
    \"zone_name\": \"amir.my\",
    \"description\": \"Amir\'s domain name\"
}" \
'http://www.dnsvault.net/api/v1/nodes/node_id/dns/views/view_id/zones'
```

> The above command returns JSON structured like this:

```json
[
{
  "view_id": 1,
  "zone_name": "amir.my",
  "description": "Amir's domain name",
  "zone_type": "master",
  "status": true,
  "processing_status": true,
  "backend_status": false,
  "delete_status": false,
  "boolean": false,
  "position": 1,
  "created_at": "2015-12-22T10:42:33.802Z",
  "updated_at": "2015-12-22T10:42:38.387Z"
}
]
```

This endpoint create a zone.

### HTTP Request

`POST http://www.dnsvault.net/api/v1/nodes/node_id/dns/views/view_id/zones`

## Delete Zone

You may delete a zone using this action.

```shell
curl --include \
     --request DELETE \
     --header "Content-Type: application/json" \
     --header "Authorization: Token iCDDAftiii2hzpnQMCrK2gtt" \
  'http://vpn.labs.my:3000/api/v1/nodes/node_id/dns/views/view_id/zones/id'
```

 The above command returns JSON structured like this:

```json
[
{
  "success": {
    "7005": "Zone has been deleted"
  }
}
]
```

This endpoint delete a zone.

### HTTP Request

`DELETE http://www.dnsvault.net/api/v1/nodes/node_id/dns/views/view_id/zones`