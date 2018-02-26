## Records (delete many)

### List all Records

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
        "domain": "dnsv.my",
        "subdomain": "yolo",
        "combine": "yolo.dnsv.my",
        "ttl": "86400",
        "kind": "A",
        "data": "2.2.11.1",
        "status": "active",
        "read_only": false,
        "created_at": "2018-02-23T08:55:37.547Z",
        "updated_at": "2018-02-23T08:55:37.547Z"
    },
    {
        "id": 11,
        "domain": null,
        "subdomain": "ddd",
        "combine": null,
        "ttl": "86400",
        "kind": "AAAA",
        "data": "::1",
        "status": "active",
        "read_only": false,
        "created_at": "2018-02-22T05:49:39.711Z",
        "updated_at": "2018-02-22T05:49:39.711Z"
    }
]
```

This endpoint show all records.

#### HTTP Request

`GET http://www.dnsvault.net/api/v1/nodes/:node_id/dns/views/:view_id/zones/:zone_id/records`

#### URL Parameters

Parameter | Description
--------- | -----------
Node_id | The ID of the record's node to retrieve
View_id | The ID of the record's view to retrieve
Zone_id | The ID of the record's zone to retrieve

### Show Record

You may view detail of a record using this action.

```shell
curl --include \
'http://www.dnsvault.net/api/v1/nodes/2/dns/views/51/zones/1/records/10'
```

> The above command returns JSON structured like this:

```json
{
    "id": 10,
    "domain": "dnsv.my",
    "subdomain": "yolo",
    "combine": "yolo.dnsv.my",
    "ttl": "86400",
    "kind": "A",
    "data": "2.2.11.1",
    "status": "active",
    "read_only": false,
    "created_at": "2018-02-23T08:55:37.547Z",
    "updated_at": "2018-02-23T08:55:37.547Z"
}
```

This endpoint retrieves detail of a record.

#### HTTP Request

`GET http://www.dnsvault.net/api/v1/nodes/:node_id/dns/views/:view_id/zones/:zone_id/records/:id`

#### URL Parameters

Parameter | Description
--------- | -----------
Node_id | The ID of the record's node to retrieve
View_id | The ID of the record's view to retrieve
Zone_id | The ID of the record's zone to retrieve
Id | The ID of the record to retrieve

### Create Records

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

#### HTTP Request

`POST http://www.dnsvault.net/api/v1/nodes/:node_id/dns/views/:view_id/zones/:zone_id/records`

#### URL Parameters

Parameter | Description
--------- | -----------
Node_id | The ID of the record's node to retrieve
View_id | The ID of the record's view to retrieve
Zone_id | The ID of the record's zone to retrieve

#### Required Parameters

Parameter | Description
--------- | -----------
type | The ID of the record's node to retrieve
ttl | The ID of the record's view to retrieve

### Delete Records (pending)

### Delete Record
You may delete records of host using this action. For testing you can use dig tool example: dig @srv1.dnsvault.net sample1.test05.my any

```shell
curl --include \
     --request DELETE \
'http://www.dnsvault.net/api/v1/nodes/2/dns/views/51/zones/1/records/10'
```


> The above command returns JSON structured like this:

```json
{
    "id": 10,
    "domain": "dnsv.my",
    "subdomain": "yolo",
    "combine": "yolo.dnsv.my",
    "ttl": "86400",
    "kind": "A",
    "data": "2.2.11.1",
    "status": "active",
    "read_only": false,
    "created_at": "2018-02-23T08:55:37.547Z",
    "updated_at": "2018-02-23T08:55:37.547Z"
}
```

This endpoint delete a record.

#### HTTP Request

`DELETE http://www.dnsvault.net/api/v1/nodes/:node_id/dns/views/:view_id/zones/:zone_id/records/:id`

#### URL Parameters

Parameter | Description
--------- | -----------
Node_id | The ID of the record's node to retrieve
View_id | The ID of the record's view to retrieve
Zone_id | The ID of the record's zone to retrieve
id | The ID of the record to delete
