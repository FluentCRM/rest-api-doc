
# Campaigns

## Get All Campaigns

```shell
curl --location --request GET 'https://yourdomain.com/wp-json/fluent-crm/v2/campaigns' \
-H 'Authorization: Basic API_USERNAME:API_PASSWORD'
```

> The above command returns JSON structured like this:

```json
{
  "campaigns": {
    "total": 14,
    "per_page": 15,
    "current_page": 1,
    "last_page": 1,
    "next_page_url": null,
    "prev_page_url": null,
    "from": 1,
    "to": 14,
    "data": [
      {
        "id": 52,
        "parent_id": null,
        "type": "campaign",
        "title": "Testing mail",
        "available_urls": null,
        "slug": "testing-mail",
        "status": "archived",
        "template_id": "0",
        "email_subject": "Testing mail header",
        "email_pre_header": "Testing mail pre-header",
        "email_body": "<!-- wp:paragraph -->\n<p>This is testing mail</p>\n<!-- /wp:paragraph -->",
        "recipients_count": 44,
        "delay": "0",
        "utm_status": "0",
        "utm_source": "",
        "utm_medium": "",
        "utm_campaign": "",
        "utm_term": "",
        "utm_content": "",
        "design_template": "simple",
        "scheduled_at": "2022-08-19 10:47:19",
        "settings": {
          "mailer_settings": {
            "from_name": "",
            "from_email": "",
            "reply_to_name": "",
            "reply_to_email": "",
            "is_custom": "no"
          },
          "subscribers": [
            {
              "list": "2",
              "tag": "all"
            }
          ],
          "excludedSubscribers": null,
          "sending_filter": "list_tag",
          "dynamic_segment": {
            "id": "",
            "slug": ""
          },
          "template_config": {
            "content_width": "700",
            "headings_font_family": "-apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Helvetica, Arial, sans-serif, 'Apple Color Emoji', 'Segoe UI Emoji', 'Segoe UI Symbol'",
            "text_color": "#202020",
            "link_color": "",
            "headings_color": "#202020",
            "body_bg_color": "#FAFAFA",
            "content_bg_color": "#FFFFFF",
            "footer_text_color": "#202020",
            "content_font_family": "-apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Helvetica, Arial, sans-serif, 'Apple Color Emoji', 'Segoe UI Emoji', 'Segoe UI Symbol'",
            "disable_footer": "no"
          },
          "advanced_filters": [
            []
          ]
        },
        "created_by": "1",
        "created_at": "2022-08-19 10:38:32",
        "updated_at": "2022-08-19 10:47:29"
      }
    ]
  }
}
```

This endpoint returns all available campaign.

### HTTP Request
`GET https://yourdomain.com/wp-json/fluent-crm/v2/campaigns`

### URL Parameters

Parameter | Type   | Description
--------- |--------| -----------
searchBy | string | Search by title                                                                                            
sort_type | string | Give a sorting order of the list DESC or ASC                                                              
sort_by | string | Sort your list by id, title, type, email_subject, design_template, recipients_count, status and many more 
with | array  | Get other additional data 

***Possible with parameters:***

- stats


## Get a Specific Campaign

```shell
curl --location --request GET 'https://yourdomain.com/wp-json/fluent-crm/v2/campaigns/52' \
-H 'Authorization: Basic API_USERNAME:API_PASSWORD'
```

> The above command returns JSON structured like this:

```json
{
  "campaign": {
    "id": 52,
    "parent_id": null,
    "type": "campaign",
    "title": "Testing mail",
    "available_urls": null,
    "slug": "testing-mail",
    "status": "archived",
    "template_id": "0",
    "email_subject": "Testing mail header",
    "email_pre_header": "Testing mail pre-header",
    "email_body": "<!-- wp:paragraph -->\n<p>This is testing mail</p>\n<!-- /wp:paragraph -->",
    "recipients_count": 44,
    "delay": "0",
    "utm_status": "0",
    "utm_source": "",
    "utm_medium": "",
    "utm_campaign": "",
    "utm_term": "",
    "utm_content": "",
    "design_template": "simple",
    "scheduled_at": "2022-08-19 10:47:19",
    "settings": {
      "mailer_settings": {
        "from_name": "",
        "from_email": "",
        "reply_to_name": "",
        "reply_to_email": "",
        "is_custom": "no"
      },
      "subscribers": [
        {
          "list": "2",
          "tag": "all"
        }
      ],
      "excludedSubscribers": null,
      "sending_filter": "list_tag",
      "dynamic_segment": {
        "id": "",
        "slug": ""
      },
      "template_config": {
        "content_width": "700",
        "headings_font_family": "-apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Helvetica, Arial, sans-serif, 'Apple Color Emoji', 'Segoe UI Emoji', 'Segoe UI Symbol'",
        "text_color": "#202020",
        "link_color": "",
        "headings_color": "#202020",
        "body_bg_color": "#FAFAFA",
        "content_bg_color": "#FFFFFF",
        "footer_text_color": "#202020",
        "content_font_family": "-apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Helvetica, Arial, sans-serif, 'Apple Color Emoji', 'Segoe UI Emoji', 'Segoe UI Symbol'",
        "disable_footer": "no"
      },
      "advanced_filters": [
        []
      ]
    },
    "created_by": "1",
    "created_at": "2022-08-19 10:38:32",
    "updated_at": "2022-08-19 10:47:29",
    "server_time": "2022-08-25 08:29:26"
  },
  "templates": []
}
```

This endpoint returns a campaign details.

### HTTP Request
`GET https://yourdomain.com/wp-json/fluent-crm/v2/campaigns/<ID>`

### URL Parameters

Parameter | Type   | Description
--------- |--------| -----------
with | array  | Get other additional data

***Possible with parameters:***

- stats

## Pause a Specific Campaign

```shell
curl --location --request POST 'https://yourdomain.com/wp-json/fluent-crm/v2/campaigns/52/pause' \
-H 'Authorization: Basic API_USERNAME:API_PASSWORD'
```

> The above command returns JSON structured like this:

```json
{
  "message": "Campaign has been successfully marked as paused",
  "campaign": {
    "campaign": {
      "id": 52,
      "parent_id": null,
      "type": "campaign",
      "title": "Testing mail",
      "available_urls": null,
      "slug": "testing-mail",
      "status": "archived",
      "template_id": "0",
      "email_subject": "Testing mail header",
      "email_pre_header": "Testing mail pre-header",
      "email_body": "<!-- wp:paragraph -->\n<p>This is testing mail</p>\n<!-- /wp:paragraph -->",
      "recipients_count": 44,
      "delay": "0",
      "utm_status": "0",
      "utm_source": "",
      "utm_medium": "",
      "utm_campaign": "",
      "utm_term": "",
      "utm_content": "",
      "design_template": "simple",
      "scheduled_at": "2022-08-19 10:47:19",
      "settings": {
        "mailer_settings": {
          "from_name": "",
          "from_email": "",
          "reply_to_name": "",
          "reply_to_email": "",
          "is_custom": "no"
        },
        "subscribers": [
          {
            "list": "2",
            "tag": "all"
          }
        ],
        "excludedSubscribers": null,
        "sending_filter": "list_tag",
        "dynamic_segment": {
          "id": "",
          "slug": ""
        },
        "template_config": {
          "content_width": "700",
          "headings_font_family": "-apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Helvetica, Arial, sans-serif, 'Apple Color Emoji', 'Segoe UI Emoji', 'Segoe UI Symbol'",
          "text_color": "#202020",
          "link_color": "",
          "headings_color": "#202020",
          "body_bg_color": "#FAFAFA",
          "content_bg_color": "#FFFFFF",
          "footer_text_color": "#202020",
          "content_font_family": "-apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Helvetica, Arial, sans-serif, 'Apple Color Emoji', 'Segoe UI Emoji', 'Segoe UI Symbol'",
          "disable_footer": "no"
        },
        "advanced_filters": [
          []
        ]
      },
      "created_by": "1",
      "created_at": "2022-08-19 10:38:32",
      "updated_at": "2022-08-19 10:47:29",
      "server_time": "2022-08-25 08:29:26"
    },
    "templates": []
  }
}
```

This endpoint returns response after pausing a campaign.

### HTTP Request
`POST https://yourdomain.com/wp-json/fluent-crm/v2/campaigns/<ID>/pause`

**Note: You can pause a campaign only if the campaign is in working state**


## Resume a Specific Campaign

```shell
curl --location --request POST 'https://yourdomain.com/wp-json/fluent-crm/v2/campaigns/52/resume' \
-H 'Authorization: Basic API_USERNAME:API_PASSWORD'
```

> The above command returns JSON structured like this:

```json
{
  "message": "Campaign has been successfully marked as resumed",
  "campaign": {
    "campaign": {
      "id": 52,
      "parent_id": null,
      "type": "campaign",
      "title": "Testing mail",
      "available_urls": null,
      "slug": "testing-mail",
      "status": "archived",
      "template_id": "0",
      "email_subject": "Testing mail header",
      "email_pre_header": "Testing mail pre-header",
      "email_body": "<!-- wp:paragraph -->\n<p>This is testing mail</p>\n<!-- /wp:paragraph -->",
      "recipients_count": 44,
      "delay": "0",
      "utm_status": "0",
      "utm_source": "",
      "utm_medium": "",
      "utm_campaign": "",
      "utm_term": "",
      "utm_content": "",
      "design_template": "simple",
      "scheduled_at": "2022-08-19 10:47:19",
      "settings": {
        "mailer_settings": {
          "from_name": "",
          "from_email": "",
          "reply_to_name": "",
          "reply_to_email": "",
          "is_custom": "no"
        },
        "subscribers": [
          {
            "list": "2",
            "tag": "all"
          }
        ],
        "excludedSubscribers": null,
        "sending_filter": "list_tag",
        "dynamic_segment": {
          "id": "",
          "slug": ""
        },
        "template_config": {
          "content_width": "700",
          "headings_font_family": "-apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Helvetica, Arial, sans-serif, 'Apple Color Emoji', 'Segoe UI Emoji', 'Segoe UI Symbol'",
          "text_color": "#202020",
          "link_color": "",
          "headings_color": "#202020",
          "body_bg_color": "#FAFAFA",
          "content_bg_color": "#FFFFFF",
          "footer_text_color": "#202020",
          "content_font_family": "-apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Helvetica, Arial, sans-serif, 'Apple Color Emoji', 'Segoe UI Emoji', 'Segoe UI Symbol'",
          "disable_footer": "no"
        },
        "advanced_filters": [
          []
        ]
      },
      "created_by": "1",
      "created_at": "2022-08-19 10:38:32",
      "updated_at": "2022-08-19 10:47:29",
      "server_time": "2022-08-25 08:29:26"
    },
    "templates": []
  }
}
```

This endpoint returns response after pausing a campaign.

### HTTP Request
`POST https://yourdomain.com/wp-json/fluent-crm/v2/campaigns/<ID>/resume`

**Note: You can resume a campaign only if the campaign is in paused state**


## Duplicate a Specific Campaign

```shell
curl --location --request POST 'https://yourdomain.com/wp-json/fluent-crm/v2/campaigns/52/duplicate' \
-H 'Authorization: Basic API_USERNAME:API_PASSWORD'
```

> The above command returns JSON structured like this:

```json
{
  "campaign": {
    "title": "[Duplicate] Testing mail",
    "slug": "testing-mail-1661422372",
    "email_body": "<!-- wp:paragraph -->\n<p>This is testing mail</p>\n<!-- /wp:paragraph -->",
    "status": "draft",
    "template_id": "0",
    "email_subject": "Testing mail header",
    "email_pre_header": "Testing mail pre-header",
    "utm_status": "0",
    "utm_source": "",
    "utm_medium": "",
    "utm_campaign": "",
    "utm_term": "",
    "utm_content": "",
    "design_template": "simple",
    "created_by": 0,
    "settings": {
      "mailer_settings": {
        "from_name": "",
        "from_email": "",
        "reply_to_name": "",
        "reply_to_email": "",
        "is_custom": "no"
      },
      "subscribers": [
        {
          "list": "2",
          "tag": "all"
        }
      ],
      "excludedSubscribers": null,
      "sending_filter": "list_tag",
      "dynamic_segment": {
        "id": "",
        "slug": ""
      },
      "template_config": {
        "content_width": "700",
        "headings_font_family": "-apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Helvetica, Arial, sans-serif, 'Apple Color Emoji', 'Segoe UI Emoji', 'Segoe UI Symbol'",
        "text_color": "#202020",
        "link_color": "",
        "headings_color": "#202020",
        "body_bg_color": "#FAFAFA",
        "content_bg_color": "#FFFFFF",
        "footer_text_color": "#202020",
        "content_font_family": "-apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Helvetica, Arial, sans-serif, 'Apple Color Emoji', 'Segoe UI Emoji', 'Segoe UI Symbol'",
        "disable_footer": "no"
      },
      "advanced_filters": [
        []
      ]
    },
    "type": "campaign",
    "updated_at": "2022-08-25 10:12:52",
    "created_at": "2022-08-25 10:12:52",
    "id": 54
  },
  "message": "Campaign has been successfully duplicated"
}
```

This endpoint returns response after duplicating a campaign.

### HTTP Request
`POST https://yourdomain.com/wp-json/fluent-crm/v2/campaigns/<ID>/duplicate`


## Update a Campaign's Title

```shell
curl --location --request PUT 'https://yourdomain.com/wp-json/fluent-crm/v2/campaigns/52/title' \
-H 'Authorization: Basic API_USERNAME:API_PASSWORD'
```

> The above command returns JSON structured like this:

```json
{
  "message": "Campaign has been updated",
  "campaign": {
    "id": 54,
    "parent_id": null,
    "type": "campaign",
    "title": "Ha Ha La La",
    "available_urls": null,
    "slug": "testing-mail-1661422372",
    "status": "draft",
    "template_id": "0",
    "email_subject": "Testing mail header",
    "email_pre_header": "Testing mail pre-header",
    "email_body": "<!-- wp:paragraph -->\n<p>This is testing mail</p>\n<!-- /wp:paragraph -->",
    "recipients_count": 0,
    "delay": "0",
    "utm_status": "0",
    "utm_source": "",
    "utm_medium": "",
    "utm_campaign": "",
    "utm_term": "",
    "utm_content": "",
    "design_template": "simple",
    "scheduled_at": null,
    "settings": {
      "mailer_settings": {
        "from_name": "",
        "from_email": "",
        "reply_to_name": "",
        "reply_to_email": "",
        "is_custom": "no"
      },
      "subscribers": [
        {
          "list": "2",
          "tag": "all"
        }
      ],
      "excludedSubscribers": null,
      "sending_filter": "list_tag",
      "dynamic_segment": {
        "id": "",
        "slug": ""
      },
      "template_config": {
        "content_width": "700",
        "headings_font_family": "-apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Helvetica, Arial, sans-serif, 'Apple Color Emoji', 'Segoe UI Emoji', 'Segoe UI Symbol'",
        "text_color": "#202020",
        "link_color": "",
        "headings_color": "#202020",
        "body_bg_color": "#FAFAFA",
        "content_bg_color": "#FFFFFF",
        "footer_text_color": "#202020",
        "content_font_family": "-apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Helvetica, Arial, sans-serif, 'Apple Color Emoji', 'Segoe UI Emoji', 'Segoe UI Symbol'",
        "disable_footer": "no"
      },
      "advanced_filters": [
        []
      ]
    },
    "created_by": "0",
    "created_at": "2022-08-25 10:12:52",
    "updated_at": "2022-08-25 10:19:48"
  }
}
```

This endpoint returns response after updating a campaign title.

### HTTP Request
`PUT https://yourdomain.com/wp-json/fluent-crm/v2/campaigns/<ID>/title`

### URL Parameters

Parameter | Type   | Description         | Required
--------- |--------|---------------------| ----------
title | string | Title of a campaign | true











## Delete a Specific Campaign

```shell
curl --location --request DELETE 'https://yourdomain.com/wp-json/fluent-crm/v2/campaigns/54' \
-H 'Authorization: Basic API_USERNAME:API_PASSWORD'
```

> The above command returns JSON structured like this:

```json
{
  "success": true
}
```

This endpoint returns response after deleting a campaign.

### HTTP Request
`DELETE https://yourdomain.com/wp-json/fluent-crm/v2/campaigns/<ID>`





## Get Campaign's Recipients Count

```shell
curl --location --request GET 'https://yourdomain.com/wp-json/fluent-crm/v2/campaigns/52/estimated-recipients-count' \
-H 'Authorization: Basic API_USERNAME:API_PASSWORD'
```

> The above command returns JSON structured like this:

```json
{
  "estimated_count": 44
}
```

This endpoint returns a campaign's total recipient count.

### HTTP Request
`GET https://yourdomain.com/wp-json/fluent-crm/v2/campaigns/<ID>/estimated-recipients-count`


## Get Campaign's Emails

```shell
curl --location --request GET 'https://yourdomain.com/wp-json/fluent-crm/v2/campaigns/52/emails' \
-H 'Authorization: Basic API_USERNAME:API_PASSWORD'
```

> The above command returns JSON structured like this:

```json
{
  "emails": {
    "total": 44,
    "per_page": 15,
    "current_page": 1,
    "last_page": 3,
    "next_page_url": "/wp-json/fluent-crm/v2/campaigns/52/emails?page=2",
    "prev_page_url": null,
    "from": 1,
    "to": 15,
    "data": [
      {
        "id": 130,
        "campaign_id": "52",
        "email_type": "campaign",
        "subscriber_id": "99",
        "email_subject_id": null,
        "email_address": "cexim77235@mahazai.com",
        "email_subject": "Testing mail header",
        "email_body": "",
        "email_headers": [],
        "is_open": "0",
        "is_parsed": "1",
        "click_counter": null,
        "status": "sent",
        "note": null,
        "scheduled_at": "2022-08-19 10:47:25",
        "email_hash": "49ac7f4a-6f7c-4dcd-ac06-f0391b2ff0f8",
        "created_at": "2022-08-19 10:47:19",
        "updated_at": "2022-08-19 10:47:25",
        "subscriber": {
          "id": 99,
          "user_id": "26",
          "hash": "e75efca302bc760109bd6a04793f9647",
          "contact_owner": null,
          "company_id": null,
          "prefix": null,
          "first_name": "dscasdvc",
          "last_name": "vdsv",
          "email": "cexim77235@mahazai.com",
          "timezone": null,
          "address_line_1": "Ambarkhana",
          "address_line_2": null,
          "postal_code": "3030",
          "city": "Sylhet",
          "state": "BD-60",
          "country": "BD",
          "ip": null,
          "latitude": null,
          "longitude": null,
          "total_points": "0",
          "life_time_value": "0",
          "phone": "01761152186",
          "status": "subscribed",
          "contact_type": "customer",
          "source": "web",
          "avatar": null,
          "date_of_birth": null,
          "created_at": "2022-06-27 10:25:18",
          "last_activity": null,
          "updated_at": "2022-07-21 10:46:34",
          "full_name": "dscasdvc vdsv",
          "photo": "https://www.gravatar.com/avatar/e75efca302bc760109bd6a04793f9647?s=128"
        }
      }
    ]
  },
  "failed_counts": 0
}
```

This endpoint returns a campaign's emails.

### HTTP Request
`GET https://yourdomain.com/wp-json/fluent-crm/v2/campaigns/<ID>/emails`


## Delete Campaign's Emails

```shell
curl --location --request DELETE 'https://yourdomain.com/wp-json/fluent-crm/v2/campaigns/52/emails' \
-H 'Authorization: Basic API_USERNAME:API_PASSWORD'
```

> The above command returns JSON structured like this:

```json
{
  "message": "Selected emails are deleted",
  "recipients_count": 9
}
```

This endpoint returns response after deleting a campaign's emails.

### HTTP Request
`DELETE https://yourdomain.com/wp-json/fluent-crm/v2/campaigns/<ID>/emails`

### URL Parameters

Parameter | Type  | Description             | Default
--------- |-------|-------------------------| ----------
email_ids | array | Email Ids of a campaign | []


## Get Campaign's Processing State

```shell
curl --location --request GET 'https://yourdomain.com/wp-json/fluent-crm/v2/campaigns/52/processing-stat' \
-H 'Authorization: Basic API_USERNAME:API_PASSWORD'
```

> The above command returns JSON structured like this:

```json
{
  "reload": true,
  "campaign": {
    "id": 52,
    "parent_id": null,
    "type": "campaign",
    "title": "Testing mail",
    "available_urls": null,
    "slug": "testing-mail",
    "status": "archived",
    "template_id": "0",
    "email_subject": "Testing mail header",
    "email_pre_header": "Testing mail pre-header",
    "email_body": "<!-- wp:paragraph -->\n<p>This is testing mail</p>\n<!-- /wp:paragraph -->",
    "recipients_count": 44,
    "delay": "0",
    "utm_status": "0",
    "utm_source": "",
    "utm_medium": "",
    "utm_campaign": "",
    "utm_term": "",
    "utm_content": "",
    "design_template": "simple",
    "scheduled_at": "2022-08-19 10:47:19",
    "settings": {
      "mailer_settings": {
        "from_name": "",
        "from_email": "",
        "reply_to_name": "",
        "reply_to_email": "",
        "is_custom": "no"
      },
      "subscribers": [
        {
          "list": "2",
          "tag": "all"
        }
      ],
      "excludedSubscribers": null,
      "sending_filter": "list_tag",
      "dynamic_segment": {
        "id": "",
        "slug": ""
      },
      "template_config": {
        "content_width": "700",
        "headings_font_family": "-apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Helvetica, Arial, sans-serif, 'Apple Color Emoji', 'Segoe UI Emoji', 'Segoe UI Symbol'",
        "text_color": "#202020",
        "link_color": "",
        "headings_color": "#202020",
        "body_bg_color": "#FAFAFA",
        "content_bg_color": "#FFFFFF",
        "footer_text_color": "#202020",
        "content_font_family": "-apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Helvetica, Arial, sans-serif, 'Apple Color Emoji', 'Segoe UI Emoji', 'Segoe UI Symbol'",
        "disable_footer": "no"
      },
      "advanced_filters": [
        []
      ]
    },
    "created_by": "1",
    "created_at": "2022-08-19 10:38:32",
    "updated_at": "2022-08-19 10:47:29"
  }
}
```

This endpoint returns a campaign's processing stat.

### HTTP Request
`GET https://yourdomain.com/wp-json/fluent-crm/v2/campaigns/<ID>/processing-stat`


## Get Campaign's Status

```shell
curl --location --request GET 'https://yourdomain.com/wp-json/fluent-crm/v2/campaigns/52/status' \
-H 'Authorization: Basic API_USERNAME:API_PASSWORD'
```

> The above command returns JSON structured like this:

```json
{
  "current_timestamp": "2022-08-25 08:49:04",
  "stat": [
    {
      "status": "sent",
      "total": "44"
    }
  ],
  "campaign": {
    "id": 52,
    "parent_id": null,
    "type": "campaign",
    "title": "Testing mail",
    "available_urls": null,
    "slug": "testing-mail",
    "status": "archived",
    "template_id": "0",
    "email_subject": "Testing mail header",
    "email_pre_header": "Testing mail pre-header",
    "email_body": "<!-- wp:paragraph -->\n<p>This is testing mail</p>\n<!-- /wp:paragraph -->",
    "recipients_count": 44,
    "delay": "0",
    "utm_status": "0",
    "utm_source": "",
    "utm_medium": "",
    "utm_campaign": "",
    "utm_term": "",
    "utm_content": "",
    "design_template": "simple",
    "scheduled_at": "2022-08-19 10:47:19",
    "settings": {
      "mailer_settings": {
        "from_name": "",
        "from_email": "",
        "reply_to_name": "",
        "reply_to_email": "",
        "is_custom": "no"
      },
      "subscribers": [
        {
          "list": "2",
          "tag": "all"
        }
      ],
      "excludedSubscribers": null,
      "sending_filter": "list_tag",
      "dynamic_segment": {
        "id": "",
        "slug": ""
      },
      "template_config": {
        "content_width": "700",
        "headings_font_family": "-apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Helvetica, Arial, sans-serif, 'Apple Color Emoji', 'Segoe UI Emoji', 'Segoe UI Symbol'",
        "text_color": "#202020",
        "link_color": "",
        "headings_color": "#202020",
        "body_bg_color": "#FAFAFA",
        "content_bg_color": "#FFFFFF",
        "footer_text_color": "#202020",
        "content_font_family": "-apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Helvetica, Arial, sans-serif, 'Apple Color Emoji', 'Segoe UI Emoji', 'Segoe UI Symbol'",
        "disable_footer": "no"
      },
      "advanced_filters": [
        []
      ]
    },
    "created_by": "1",
    "created_at": "2022-08-19 10:38:32",
    "updated_at": "2022-08-19 10:47:29"
  },
  "sent_count": 44,
  "analytics": {
    "unsubscribe": {
      "type": "unsubscribe",
      "total": "1",
      "icon_class": "el-icon el-icon-warning-outline",
      "is_percent": true,
      "label": "Unsubscribe Rate (1)"
    }
  },
  "subject_analytics": []
}
```

This endpoint returns a campaign's status.

### HTTP Request
`GET https://yourdomain.com/wp-json/fluent-crm/v2/campaigns/<ID>/status`


## Get Campaign's Links

```shell
curl --location --request GET 'https://yourdomain.com/wp-json/fluent-crm/v2/campaigns/52/link-report' \
-H 'Authorization: Basic API_USERNAME:API_PASSWORD'
```

> The above command returns JSON structured like this:

```json
{
  "links": []
}
```

This endpoint returns a campaign's links.

### HTTP Request
`GET https://yourdomain.com/wp-json/fluent-crm/v2/campaigns/<ID>/link-report`


## Get Campaign's Revenues

```shell
curl --location --request GET 'https://yourdomain.com/wp-json/fluent-crm/v2/campaigns/52/revenues?per_page=2&page=1' \
-H 'Authorization: Basic API_USERNAME:API_PASSWORD'
```

> The above command returns JSON structured like this:

```json
{
  "orders": [],
  "labels": {
    "id": "ID",
    "title": "Title",
    "status": "Status",
    "date": "Date",
    "total": "Total"
  },
  "total": 0
}
```

This endpoint returns a campaign's revenues.

### HTTP Request
`GET https://yourdomain.com/wp-json/fluent-crm/v2/campaigns/<ID>/revenues`

### URL Parameters

Parameter | Type | Description | Default
--------- |------| ----------- | ----------
per_page | int  | Records per page | 10 
page | int  | Page Number for Pagination | 1


## Get Campaign's Unsubscribes

```shell
curl --location --request GET 'https://yourdomain.com/wp-json/fluent-crm/v2/campaigns/52/unsubscribers?per_page=2&page=1' \
-H 'Authorization: Basic API_USERNAME:API_PASSWORD'
```

> The above command returns JSON structured like this:

```json
{
  "unsubscribes": {
    "total": 0,
    "per_page": 2,
    "current_page": 1,
    "last_page": 0,
    "next_page_url": null,
    "prev_page_url": null,
    "from": null,
    "to": null,
    "data": []
  }
}
```

This endpoint returns a campaign's unsubscribers.

### HTTP Request
`GET https://yourdomain.com/wp-json/fluent-crm/v2/campaigns/<ID>/unsubscribers`

### URL Parameters

Parameter | Type | Description | Default
--------- |------| ----------- | ----------
per_page | int  | Records per page | 15
page | int  | Page Number for Pagination | 1


## Get Campaign's Contacts by Segment

```shell
curl --location --request GET 'https://yourdomain.com/wp-json/fluent-crm/v2/campaigns/52/contacts-by-segment?per_page=2&page=1' \
-H 'Authorization: Basic API_USERNAME:API_PASSWORD'
```

> The above command returns JSON structured like this:

```json
{
  "subscribers": {
    "total": 44,
    "per_page": 15,
    "current_page": 1,
    "last_page": 3,
    "next_page_url": "/wp-json/fluent-crm/v2/campaigns/52/contacts-by-segment?page=2",
    "prev_page_url": null,
    "from": 1,
    "to": 15,
    "data": [
      {
        "id": 658,
        "user_id": null,
        "hash": "93b66e2a55f146e2e3cb9ea2e06e4a81",
        "contact_owner": null,
        "company_id": null,
        "prefix": null,
        "first_name": "Laurence",
        "last_name": null,
        "email": "lboudet@free.fr",
        "timezone": null,
        "address_line_1": null,
        "address_line_2": null,
        "postal_code": null,
        "city": null,
        "state": null,
        "country": null,
        "ip": "127.0.0.1",
        "latitude": null,
        "longitude": null,
        "total_points": "0",
        "life_time_value": "0",
        "phone": null,
        "status": "subscribed",
        "contact_type": "lead",
        "source": "ActiveCampaign",
        "avatar": null,
        "date_of_birth": null,
        "created_at": "2022-01-22 00:45:54",
        "last_activity": null,
        "updated_at": "2022-08-02 08:28:15",
        "full_name": "Laurence",
        "photo": "https://www.gravatar.com/avatar/93b66e2a55f146e2e3cb9ea2e06e4a81?s=128",
        "lists": [
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
            "id": 9,
            "title": "Hello",
            "slug": "hello",
            "description": null,
            "created_at": "2022-06-24 05:23:49"
          }
        ]
      }
    ]
  }
}
```

This endpoint returns a campaign's contacts by segment.

### HTTP Request
`GET https://yourdomain.com/wp-json/fluent-crm/v2/campaigns/<ID>/contacts-by-segment`

### URL Parameters

Parameter | Type   | Description                                                                                                               | Default
--------- |--------|---------------------------------------------------------------------------------------------------------------------------| ----------
per_page | int    | Records per page                                                                                                          | 15
page | int    | Page Number for Pagination                                                                                                | 1
search | string | Filter by contacts email, first_name, last_name, address_line_1, address_line_2, postal_code, city, state, country, phone  | empty
sort_by | string | Give a sorting field of the contacts field                                                                                | id
sort_type | string | Give a sorting order of the contacts DESC or ASC                                                                          | DESC
