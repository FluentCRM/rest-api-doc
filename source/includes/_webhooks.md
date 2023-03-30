
# Webhooks

## Get All Webhooks

```shell
curl --location --request GET 'https://yourdomain.com/wp-json/fluent-crm/v2/webhooks' \
--header 'Authorization: Basic API_USERNAME:API_PASSWORD'
```

> The above command returns JSON structured like this:

```json
{
  "webhooks": [],
  "fields": [
    {
      "key": "prefix",
      "field": "Name Prefix"
    },
    {
      "key": "first_name",
      "field": "First Name"
    }
  ],
  "custom_fields": [
    {
      "key": "blood_group",
      "field": "Blood Group"
    },
    {
      "key": "username",
      "field": "Username"
    }
  ],
  "schema": {
    "name": "",
    "lists": [],
    "tags": [],
    "url": "",
    "status": ""
  },
  "lists": [
    {
      "id": 1,
      "title": "TutorLMS",
      "slug": "tutorlms",
      "description": null,
      "is_public": "0",
      "created_at": "2022-03-23 08:08:16",
      "updated_at": "2022-03-23 08:08:16"
    },
    {
      "id": 2,
      "title": "WooCommerce",
      "slug": "woocommerce",
      "description": null,
      "is_public": "0",
      "created_at": "2022-03-23 08:08:16",
      "updated_at": "2022-03-23 08:08:16"
    }
  ],
  "tags": [
    {
      "id": 1,
      "title": "Course Enrolled",
      "slug": "course-enrolled",
      "description": null,
      "created_at": "2022-03-23 08:08:55",
      "updated_at": "2022-03-23 08:08:55"
    },
    {
      "id": 2,
      "title": "Course Completed",
      "slug": "course-completed",
      "description": null,
      "created_at": "2022-03-23 08:08:55",
      "updated_at": "2022-03-23 08:08:55"
    }
  ]
}
```

This endpoint returns all webhooks as well as fields, custom_fields, schema, lists and tags

### HTTP Request
`GET https://yourdomain.com/wp-json/fluent-crm/v2/webhooks`

### URL Parameters

Parameter | Type   | Description            | Default
--------- |--------|------------------------| ----------
search | string | Filter by webhook name | empty


## Create a webhook

```shell
curl --location --request POST 'https://yourdomain.com/wp-json/fluent-crm/v2/webhook' \
--header 'Authorization: Basic API_USERNAME:API_PASSWORD'
```
> The above command returns JSON structured like this:

```json
{
  "id": 82,
  "webhook": {
    "name": "Demo Webhook",
    "status": "pending",
    "tags": [
      1,
      2
    ],
    "lists": [
      1,
      2
    ],
    "url": "http://wp.test/?fluentcrm=1&route=contact&hash=0d501311-7884-4060-b10f-14a0cbc1e829"
  },
  "webhooks": [
    {
      "id": 82,
      "object_type": "webhook",
      "object_id": null,
      "key": "0d501311-7884-4060-b10f-14a0cbc1e829",
      "value": {
        "name": "Demo Webhook",
        "status": "pending",
        "tags": [
          1,
          2
        ],
        "lists": [
          1,
          2
        ],
        "url": "http://wp.test/?fluentcrm=1&route=contact&hash=0d501311-7884-4060-b10f-14a0cbc1e829"
      },
      "created_at": "2022-08-26 06:42:26",
      "updated_at": "2022-08-26 06:42:26"
    }
  ],
  "message": "Successfully created the WebHook"
}
```

This endpoint return response after creating a webhook.

### HTTP Request

`POST https://yourdomain.com/wp-json/fluent-crm/v2/webhook`

### URL Parameters

Parameter    | Type    | Description           | Required
---------    |---------|-----------------------| ---------
name | string  | The name of webhook   | true
status | boolean | The status of webhook | true
tags | array | Id's of tags          | false
lists | array | Id's of lists         | false

***Possible status parameters***

- pending
- subscribed

## Update a webhook

```shell
curl --location --request PUT 'https://yourdomain.com/wp-json/fluent-crm/v2/webhook/82' \
--header 'Authorization: Basic API_USERNAME:API_PASSWORD'
```
> The above command returns JSON structured like this:

```json
{
  "webhooks": [
    {
      "id": 82,
      "object_type": "webhook",
      "object_id": null,
      "key": "0d501311-7884-4060-b10f-14a0cbc1e829",
      "value": {
        "name": "Changed webhook",
        "status": "subscribed",
        "tags": [],
        "lists": [],
        "url": "http://wp.test/?fluentcrm=1&route=contact&hash=0d501311-7884-4060-b10f-14a0cbc1e829",
        "query_timestamp": "1661496607456"
      },
      "created_at": "2022-08-26 06:42:26",
      "updated_at": "2022-08-26 06:52:00"
    }
  ],
  "message": "Successfully updated the webhook"
}
```

This endpoint return response after updating a webhook.

### HTTP Request

`PUT https://yourdomain.com/wp-json/fluent-crm/v2/webhook/<ID>`

### URL Parameters

Parameter    | Type    | Description           | Required
---------    |---------|-----------------------| ---------
name | string  | The name of webhook   | true
status | boolean | The status of webhook | true
tags | array | Id's of tags          | false
lists | array | Id's of lists         | false

***Possible status parameters***

- pending
- subscribed


## Delete a webhook

```shell
curl --location --request DELETE 'https://yourdomain.com/wp-json/fluent-crm/v2/webhook/82' \
--header 'Authorization: Basic API_USERNAME:API_PASSWORD'
```
> The above command returns JSON structured like this:

```json
{
  "webhooks": [],
  "message": "Successfully deleted the webhook"
}
```

This endpoint return response after deleting a webhook.

### HTTP Request

`DELETE https://yourdomain.com/wp-json/fluent-crm/v2/webhook/<ID>`
