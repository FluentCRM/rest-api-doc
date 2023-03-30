
# Tags

## Get All Tags

```shell
curl --location --request GET 'https://yourdomain.com/wp-json/fluent-crm/v2/tags' \
-H 'Authorization: Basic API_USERNAME:API_PASSWORD'
```

> The above command returns JSON structured like this:

```json
{
    "tags": [
        {
            "id": "2",
            "title": "User Two",
            "slug": "user-two",
            "description": null,
            "is_public": "0",
            "created_at": "2021-07-19 08:25:22",
            "updated_at": "2021-07-19 08:25:22",
            "totalCount": 1,
            "subscribersCount": 1
        },
        {
            "id": "1",
            "title": "User One",
            "slug": "user-one",
            "description": null,
            "is_public": "0",
            "created_at": "2021-07-19 08:25:22",
            "updated_at": "2021-07-19 08:25:22",
            "totalCount": 1,
            "subscribersCount": 1
        }
    ]
}
```

This endpoint returns all available tags.

### HTTP Request
`GET https://yourdomain.com/wp-json/fluent-crm/v2/tags`

### URL Parameters

Parameter | Description
--------- | -----------
sort_by | Sort your tag by id, title, subscribers
sort_order | Give a sorting order of the tag DESC or ASC
search | Search by title, slug, description

Other Parameters | Description
------------------ | ----------------
exclude_counts | Give exclude count status true or false. If false then return totalCount, subscribersCount with every tag
all_tags | Give all tags status true or false. If you want to get only id, title and slug only, then give value true


## Retrieve a Tag

```shell
curl --location --request GET 'https://yourdomain.com/wp-json/fluent-crm/v2/tags/4' \
-H 'Authorization: Basic API_USERNAME:API_PASSWORD'
```

> The above command returns JSON structured like this:

```json
{
    "tag": {
        "title": "User Tag",
        "slug": "user-tag",
        "description": "",
        "updated_at": "2021-07-20 13:18:19",
        "created_at": "2021-07-20 13:18:19",
        "id": 4
    }
}
```

### HTTP Request
`GET https://yourdomain.com/wp-json/fluent-crm/v2/tags/<ID>`

This endpoint will return a tag.


## Create a new Tag

```shell
curl --location --request POST 'https://yourdomain.com/wp-json/fluent-crm/v2/tags?title=New Tag&slug=new-data' \
-H 'Authorization: Basic API_USERNAME:API_PASSWORD'
```

> The above command returns JSON structured like this:

```json
{
    "tags": {
        "title": "New Tag",
        "slug": "new-data",
        "description": "",
        "updated_at": "2021-07-20 13:18:19",
        "created_at": "2021-07-20 13:18:19",
        "id": 4
    },
    "message": "Successfully saved the tag."
}
```

### HTTP Request
`POST https://yourdomain.com/wp-json/fluent-crm/v2/tags/`

### URL Parameters

Parameter | Description
--------- | -----------
title | Add name to your tag.
slug | Add slug name to your tag.
description | Add Internal Subtitle.

This endpoint will create a new tag.

## Update any Tag

```shell
curl --location --request PUT 'https://yourdomain.com/wp-json/fluent-crm/v2/tags/1?title=New Title' \
-H 'Authorization: Basic API_USERNAME:API_PASSWORD'
```

> The above command returns JSON structured like this:

```json
{
  "tags": "1",
  "message": "Successfully saved the tag."
}
```

### HTTP Request
`PUT https://yourdomain.com/wp-json/fluent-crm/v2/tags/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
title | Add name to your tag.
slug | Add slug name to your tag.
description | Add Internal Subtitle.

This endpoint will update a specific tag.


## Delete a specific Tag

```shell
curl --location --request DELETE 'https://yourdomain.com/wp-json/fluent-crm/v2/tags/<ID>' \
-H 'Authorization: Basic API_USERNAME:API_PASSWORD'
```

> The above command returns JSON structured like this:

```json
{
    "message": "Successfully removed the tag."
}
```

### HTTP Request
`DELETE https://yourdomain.com/wp-json/fluent-crm/v2/tags/<ID>`

This endpoint will delete a specific tag.
