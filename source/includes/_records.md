# Records

## List all Records

You may list collection of zone using this action.

```shell
curl --include \
     --header "Authorization: Token iwwTXK54aahsosrx5JK7hkTe" \
  'http://www.dnsvault.net/api/v1/nodes/2/dns/views/51/zones/1/records'
```


> The above command returns JSON structured like this:

```json
[
  {
    "id": 10,
    "host_id": null,
    "zone_id": 13,
    "rr_zone": "test05.my",
    "rr_host": "@",
    "rr_combine": "test05.my",
    "rr_ttl": "3600",
    "rr_type": "SOA",
    "rr_data": "a.dnsvault.net. amir.localhost.my. 1 86400 7200 3600000 3600",
    "status": true,
    "processing_status": true,
    "backend_status": false,
    "delete_status": false,
    "created_at": "2015-12-30T16:57:19.249Z",
    "updated_at": "2015-12-30T16:57:19.249Z"
  },
  {
    "id": 11,
    "host_id": null,
    "zone_id": 13,
    "rr_zone": "test05.my",
    "rr_host": "@",
    "rr_combine": "test05.my",
    "rr_ttl": "3600",
    "rr_type": "NS",
    "rr_data": "a.dnsvault.net.",
    "status": true,
    "processing_status": true,
    "backend_status": false,
    "delete_status": false,
    "created_at": "2015-12-30T16:57:19.259Z",
    "updated_at": "2015-12-30T16:57:19.259Z"
  },
  {
    "id": 12,
    "host_id": null,
    "zone_id": 13,
    "rr_zone": "test05.my",
    "rr_host": "sample1",
    "rr_combine": "sample1.test05.my.",
    "rr_ttl": "86400",
    "rr_type": "A",
    "rr_data": "2.2.2.101",
    "status": true,
    "processing_status": false,
    "backend_status": false,
    "delete_status": false,
    "created_at": "2015-12-30T16:59:18.802Z",
    "updated_at": "2015-12-30T16:59:18.802Z"
  },
  {
    "id": 13,
    "host_id": null,
    "zone_id": 13,
    "rr_zone": "test05.my",
    "rr_host": "sample1",
    "rr_combine": "sample1.test05.my.",
    "rr_ttl": "86400",
    "rr_type": "A",
    "rr_data": "2.2.2.109",
    "status": true,
    "processing_status": false,
    "backend_status": false,
    "delete_status": false,
    "created_at": "2015-12-30T17:00:32.953Z",
    "updated_at": "2015-12-30T17:00:32.953Z"
  }
]
```

This endpoint show all records.

### HTTP Request

`GET http://www.dnsvault.net/views/:view_id/zones/:zone_id/records`

## Show Record

## Create Records

You may create multiple records for a host. After create you can check using dig tool, example: dig @srv1.dnsvault.net sample1.test05.my any

```shell
curl --include \
     --request POST \
     --header "Content-Type: application/json" \
     --data-binary "{
    \"host\": \"sample1\",
    \"records\": [
        { \"type\":\"A\", \"data\":\"2.2.2.2\"},
        { \"ttl\":\"7200\", \"type\":\"MX\", \"data\":\"10 mail.server01.com.\"}
    ]
}" \
'http://www.dnsvault.net/api/v1/nodes/2/dns/views/51/zones/1/records'
```


> The above command returns JSON structured like this:

```json
{
  "messages": {
    "success": [
      {
        "id": 14,
        "host_id": null,
        "zone_id": 13,
        "rr_zone": "test05.my",
        "rr_host": "sample1",
        "rr_combine": "sample1.test05.my.",
        "rr_ttl": null,
        "rr_type": "A",
        "rr_data": "2.2.2.2",
        "status": true,
        "processing_status": false,
        "backend_status": false,
        "delete_status": false,
        "created_at": "2015-12-30T17:54:09.796Z",
        "updated_at": "2015-12-30T17:54:09.796Z"
      },
      {
        "id": 15,
        "host_id": null,
        "zone_id": 13,
        "rr_zone": "test05.my",
        "rr_host": "sample1",
        "rr_combine": "sample1.test05.my.",
        "rr_ttl": "7200",
        "rr_type": "MX",
        "rr_data": "10 mail.server01.com.",
        "status": true,
        "processing_status": false,
        "backend_status": false,
        "delete_status": false,
        "created_at": "2015-12-30T17:54:10.197Z",
        "updated_at": "2015-12-30T17:54:10.197Z"
      }
    ],
    "errors": []
  }
}
```

This endpoint create multiple records.

### HTTP Request

`POST http://www.dnsvault.net/api/v1/nodes/:node_id/dns/views/:view_id/zones/:id/records`

## Create Record

You may create one records for a host. After create you can check using dig tool, example: dig @srv1.dnsvault.net sample1.test05.my any

```shell
curl --include \
     --request POST \
     --header "Content-Type: application/json" \
     --header "Authorization: Token iwwTXK54aahsosrx5JK7hkTe" \
     --data-binary "{
    \"host\": \"sample1\",
    \"record\": 
            {
                \"ttl\":3600,
                \"type\": \"A\",
                \"data\": \"2.2.2.2\"
            }
}" \
'http://www.dnsvault.net/api/v1/nodes/2/dns/views/51/zones/1/record'
```


> The above command returns JSON structured like this:

```json
{
  "id": 74,
  "host_id": null,
  "zone_id": 28,
  "rr_zone": "amir.my",
  "rr_host": "sample1",
  "rr_combine": "sample1.amir.my.",
  "rr_ttl": "3600",
  "rr_type": "A",
  "rr_data": "2.2.2.2",
  "status": true,
  "processing_status": false,
  "backend_status": false,
  "delete_status": false,
  "created_at": "2016-01-11T13:17:28.871Z",
  "updated_at": "2016-01-11T13:17:28.871Z"
}
```

This endpoint create a record.

### HTTP Request

`POST http://www.dnsvault.net/api/v1/nodes/:node_id/dns/views/:view_id/zones/:id/record`


## Delete Records

## Delete Record
You may delete records of host using this action. For testing you can use dig tool example: dig @srv1.dnsvault.net sample1.test05.my any

```shell
curl --include \
     --request DELETE \
     --header "Content-Type: application/json" \
     --data-binary "{
    \"host\": \"sample1\",
    \"records\": [
        { \"type\":\"A\", \"data\":\"2.2.2.2\"},
        { \"ttl\":\"7200\", \"type\":\"MX\", \"data\":\"10 mail.server01.com.\"}
    ]
}" \
'http://www.dnsvault.net/api/v1/nodes/2/dns/views/51/zones/1/records'
```


> The above command returns JSON structured like this:

```json
{
  "messages": {
    "success": [
      {
        "id": 14,
        "host_id": null,
        "zone_id": 13,
        "rr_zone": "test05.my",
        "rr_host": "sample1",
        "rr_combine": "sample1.test05.my.",
        "rr_ttl": "86400",
        "rr_type": "A",
        "rr_data": "2.2.2.2",
        "status": true,
        "processing_status": false,
        "backend_status": false,
        "delete_status": false,
        "created_at": "2015-12-30T17:54:09.796Z",
        "updated_at": "2015-12-30T17:54:09.796Z"
      }
    ],
    "errors": [
      {
        "host": "sample1",
        "error": "Record with type: MX and data: 10 mx.com. is not available, please try again."
      }
    ]
  }
}
```

This endpoint create a record.

### HTTP Request

`DELETE http://www.dnsvault.net/api/v1/nodes/:node_id/dns/views/:view_id/zones/:id/records`