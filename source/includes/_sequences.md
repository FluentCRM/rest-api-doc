
# Email Sequences

## Get All Email Sequences

```shell
curl "https://yourdomain.com/wp-json/fluent-crm/v2/sequences" \
  -H "Authorization: BASIC API_USERNAME:API_PASSWORD"
```
> The above command returns JSON structured like this:

```json
{
  "sequences": {
    "total": 4,
    "per_page": 15,
    "current_page": 1,
    "last_page": 1,
    "next_page_url": null,
    "prev_page_url": null,
    "from": 1,
    "to": 4,
    "data": [
      {
        "id": 2,
        "parent_id": null,
        "type": "email_sequence",
        "title": "First Sequence",
        "available_urls": null,
        "slug": "first-sequence",
        "status": "draft",
        "template_id": null,
        "email_subject": null,
        "email_pre_header": null,
        "email_body": "",
        "recipients_count": 0,
        "delay": "0",
        "utm_status": "0",
        "utm_source": null,
        "utm_medium": null,
        "utm_campaign": null,
        "utm_term": null,
        "utm_content": null,
        "design_template": "simple",
        "scheduled_at": null,
        "settings": {
          "mailer_settings": {
            "from_name": "",
            "from_email": "",
            "reply_to_name": "",
            "reply_to_email": "",
            "is_custom": "no"
          }
        },
        "created_by": "1",
        "created_at": "2022-02-07 09:54:19",
        "updated_at": "2022-02-07 09:54:19",
        "stats": {
          "emails": 2,
          "subscribers": 4
        }
      }
    ]
  }
}
```

This endpoint retrieves all email sequences.

### HTTP Request

`GET https://yourdomain.com/wp-json/fluent-crm/v2/sequences`

### URL Parameters

 Parameter | Type | Description                                        | Default 
-----------| ------- |----------------------------------------------------|---------
| per_page  |  int | Records per page                                   |         |
| page      |    int   | Page Number for Pagination                         |         |
| search    | string | Search Parameter for filtering sequences           |         |
| orderBy   | string | Order By sequence column Value to sort sequences   | id      |
| order     | string | Order Type sequence column Value to sort sequences | DESC    |
| with[]    | array | Get Additional Sequence Meta Properties            |         |

***Possible with parameters:***

- stats

## Get a Specific email sequence


```shell
curl "https://yourdomain.com/wp-json/fluent-crm/v2/sequences/<ID>?with[]=sequence_emails&with[]=email_stats" \
  -H "Authorization: BASIC API_USERNAME:API_PASSWORD"
```

> The above command returns JSON structured like this:

```json
{
  "sequence": {
    "id": 1,
    "parent_id": null,
    "type": "email_sequence",
    "title": "Test Sequence",
    "available_urls": null,
    "slug": "test-sequence",
    "status": "draft",
    "template_id": null,
    "email_subject": null,
    "email_pre_header": null,
    "email_body": "",
    "recipients_count": 0,
    "delay": "0",
    "utm_status": "0",
    "utm_source": null,
    "utm_medium": null,
    "utm_campaign": null,
    "utm_term": null,
    "utm_content": null,
    "design_template": "simple",
    "scheduled_at": null,
    "settings": {
      "mailer_settings": {
        "from_name": "",
        "from_email": "",
        "reply_to_name": "",
        "reply_to_email": "",
        "is_custom": "no"
      }
    },
    "created_by": "1",
    "created_at": "2022-02-14 04:49:14",
    "updated_at": "2022-02-14 04:49:14"
  },
  "sequence_emails": [
    {
      "id": 1,
      "parent_id": "1",
      "type": "sequence_mail",
      "title": "Fatal Error?",
      "available_urls": null,
      "slug": "fatal-error",
      "status": "published",
      "template_id": "0",
      "email_subject": "Fatal Error?",
      "email_pre_header": "Test Header",
      "email_body": "<!-- wp:paragraph -->\n<p>Start Writing Here</p>\n<!-- /wp:paragraph -->\n\n<!-- wp:heading {\"style\":{\"color\":{\"text\":\"#2c7df6\"}}} -->\n<h2 class=\"has-text-color\" id=\"i-am-here\" style=\"color:#2c7df6\">I am here</h2>\n<!-- /wp:heading -->",
      "recipients_count": "0",
      "delay": "60",
      "utm_status": "0",
      "utm_source": null,
      "utm_medium": null,
      "utm_campaign": null,
      "utm_term": null,
      "utm_content": null,
      "design_template": "simple",
      "scheduled_at": null,
      "settings": {
        "timings": {
          "delay_unit": "minutes",
          "delay": "1",
          "is_anytime": "yes",
          "sending_time": ""
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
        "mailer_settings": {
          "from_name": "",
          "from_email": "",
          "reply_to_name": "",
          "reply_to_email": "",
          "is_custom": "no"
        }
      },
      "created_by": "1",
      "created_at": "2022-02-14 04:50:06",
      "updated_at": "2022-02-14 04:50:06",
      "stats": {
        "total": 0,
        "sent": 0,
        "clicks": 0,
        "views": 0,
        "unsubscribers": 0,
        "revenue": false
      }
    }
  ]
}
```

This endpoint retrieves a specific email sequence.

### HTTP Request

`GET https://yourdomain.com/wp-json/fluent-crm/v2/sequences/<ID>`

### URL Parameters

Parameter | Type | Description
--------- | ----------- | -----
with[] | array | Get Additional Sequence Meta Properties

***Possible with parameters:***

- sequence_emails
- email_stats


## Get Email Sequences by specific Subscriber


```shell
curl "https://yourdomain.com/wp-json/fluent-crm/v2/sequences/subscriber/<ID>/sequences" \
  -H "Authorization: BASIC API_USERNAME:API_PASSWORD"
```

> The above command returns JSON structured like this:

```json
{
    "sequence_trackers": {
        "total": 1,
        "per_page": 15,
        "current_page": 1,
        "last_page": 1,
        "next_page_url": null,
        "prev_page_url": null,
        "from": 1,
        "to": 1,
        "data": [
            {
                "id": 1,
                "campaign_id": "2",
                "last_sequence_id": "13",
                "subscriber_id": "17210",
                "next_sequence_id": null,
                "status": "completed",
                "type": "sequence_tracker",
                "last_executed_time": "2022-08-25 08:56:51",
                "next_execution_time": null,
                "notes": null,
                "created_at": "2022-08-25 08:56:51",
                "updated_at": "2022-08-25 08:56:51",
                "sequence": {
                    "id": 2,
                    "parent_id": null,
                    "type": "email_sequence",
                    "title": "First Sequence",
                    "available_urls": null,
                    "slug": "first-sequence",
                    "status": "draft",
                    "template_id": null,
                    "email_subject": null,
                    "email_pre_header": null,
                    "email_body": "",
                    "recipients_count": 0,
                    "delay": "0",
                    "utm_status": "0",
                    "utm_source": null,
                    "utm_medium": null,
                    "utm_campaign": null,
                    "utm_term": null,
                    "utm_content": null,
                    "design_template": "simple",
                    "scheduled_at": null,
                    "settings": {
                        "mailer_settings": {
                            "from_name": "",
                            "from_email": "",
                            "reply_to_name": "",
                            "reply_to_email": "",
                            "is_custom": "no"
                        }
                    },
                    "created_by": "1",
                    "created_at": "2022-02-07 09:54:19",
                    "updated_at": "2022-02-07 09:54:19"
                },
                "last_sequence": {
                    "id": 13,
                    "parent_id": "2",
                    "type": "sequence_mail",
                    "title": "Rounded Button",
                    "available_urls": null,
                    "slug": "rounded-button",
                    "status": "published",
                    "template_id": "315",
                    "email_subject": "Rounded Button",
                    "email_pre_header": "Rounded button",
                    "email_body": "<!-- wp:paragraph -->\n<p>Start Writing Here</p>\n<!-- /wp:paragraph -->\n\n<!-- wp:buttons -->\n<div class=\"wp-block-buttons\"><!-- wp:button {\"style\":{\"border\":{\"radius\":\"100px\"}}} -->\n<div class=\"wp-block-button\"><a class=\"wp-block-button__link\" style=\"border-radius:100px\">Rounded button</a></div>\n<!-- /wp:button --></div>\n<!-- /wp:buttons -->",
                    "recipients_count": "0",
                    "delay": "60",
                    "utm_status": "0",
                    "utm_source": null,
                    "utm_medium": null,
                    "utm_campaign": null,
                    "utm_term": null,
                    "utm_content": null,
                    "design_template": "simple",
                    "scheduled_at": null,
                    "settings": {
                        "timings": {
                            "delay_unit": "minutes",
                            "delay": "1",
                            "is_anytime": "yes",
                            "sending_time": ""
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
                        "mailer_settings": {
                            "from_name": "",
                            "from_email": "",
                            "reply_to_name": "",
                            "reply_to_email": "",
                            "is_custom": "no"
                        }
                    },
                    "created_by": "1",
                    "created_at": "2022-03-04 05:07:53",
                    "updated_at": "2022-03-04 05:07:53"
                },
                "next_sequence": null
            }
        ]
    }
}
```

This endpoint get email sequences by specific subscriber.

### HTTP Request

`GET https://yourdomain.com/wp-json/fluent-crm/v2/sequences/subscriber/<ID>/sequences`

Note: Use subscriber's ID

### URL Parameters

Parameter | Type   | Description                                                    
------- |--------|----------------------------------------------------------------
| per_page |  int | Records per page                                               
| page |    int   | Page Number for Pagination                                     



## Get Subscribers from a specific email sequence


```shell
curl "https://yourdomain.com/wp-json/fluent-crm/v2/sequences/<ID>/subscribers" \
  -H "Authorization: BASIC API_USERNAME:API_PASSWORD"
```

> The above command returns JSON structured like this:

```json
{
    "total": 1,
    "per_page": 15,
    "current_page": 1,
    "last_page": 1,
    "next_page_url": null,
    "prev_page_url": null,
    "from": 1,
    "to": 1,
    "data": [
        {
            "id": 1,
            "campaign_id": "1",
            "last_sequence_id": "1",
            "subscriber_id": "1",
            "next_sequence_id": null,
            "status": "completed",
            "type": "sequence_tracker",
            "last_executed_time": "2022-08-25 08:44:16",
            "next_execution_time": null,
            "notes": null,
            "created_at": "2022-08-25 08:44:16",
            "updated_at": "2022-08-25 08:44:16",
            "subscriber": {
                "id": 1,
                "user_id": null,
                "hash": "67a7a8ce2603f193447d52fc0fb8f745",
                "contact_owner": null,
                "company_id": null,
                "prefix": null,
                "first_name": "",
                "last_name": "",
                "email": "mafobit507@kuruapp.com",
                "timezone": null,
                "address_line_1": "",
                "address_line_2": "",
                "postal_code": "1001",
                "city": "City",
                "state": "State",
                "country": "UK",
                "ip": null,
                "latitude": null,
                "longitude": null,
                "total_points": "0",
                "life_time_value": "0",
                "phone": "75456345",
                "status": "subscribed",
                "contact_type": "lead",
                "source": null,
                "avatar": null,
                "date_of_birth": "0000-00-00",
                "created_at": "2022-03-29 06:19:10",
                "last_activity": null,
                "updated_at": "2022-08-16 11:29:26",
                "full_name": "",
                "photo": "https://www.gravatar.com/avatar/67a7a8ce2603f193447d52fc0fb8f745?s=128"
            }
        }
    ]
}
```

This endpoint get subscribers from a email sequence.

### HTTP Request

`GET https://yourdomain.com/wp-json/fluent-crm/v2/sequences/<ID>/subscribers`

### URL Parameters

Parameter | type  | Description | Default
--------- |-------|-----------------------------| --------
| per_page |  int | Records per page            | |
| page |    int   | Page Number for Pagination  | |


## Duplicate a Specific email sequence


```shell
curl "https://yourdomain.com/wp-json/fluent-crm/v2/sequences/<ID>/duplicate" \
  -H "Authorization: BASIC API_USERNAME:API_PASSWORD"
```

> The above command returns JSON structured like this:

```json
{
    "sequence": {
        "title": "[Duplicate] Test Sequence",
        "settings": {
            "mailer_settings": {
                "from_name": "",
                "from_email": "",
                "reply_to_name": "",
                "reply_to_email": "",
                "is_custom": "no"
            }
        },
        "design_template": "simple",
        "email_body": "",
        "status": "draft",
        "type": "email_sequence",
        "slug": "duplicate-test-sequence",
        "created_by": 0,
        "updated_at": "2022-08-25 08:21:45",
        "created_at": "2022-08-25 08:21:45",
        "id": 2
    },
    "message": "Selected sequence has been successfully duplicated"
}
```

This endpoint duplicate a email sequence.

### HTTP Request

`POST https://yourdomain.com/wp-json/fluent-crm/v2/sequences/<ID>/duplicate`


## Delete Email Sequence

```shell
curl "https://yourdomain.com/wp-json/fluent-crm/v2/sequences/<ID>" \
  -H "Authorization: BASIC API_USERNAME:API_PASSWORD"
```

> The above command returns JSON structured like this:

```json
{
  "message": "Email sequence successfully deleted"
}
```

```shell
curl "https://yourdomain.com/wp-json/fluent-crm/v2/sequences/do-bulk-action?sequence_ids[]=1&sequence_ids[]=2" \
  -H "Authorization: BASIC API_USERNAME:API_PASSWORD"
```

> The above command returns JSON structured like this:

```json
{
  "message": "Selected Sequences has been deleted permanently"
}
```
This endpoint deletes a specific email sequence.

### HTTP Request

`DELETE https://yourdomain.com/wp-json/fluent-crm/v2/sequences/<ID>`


### Delete multiple email sequences
`POST https://yourdomain.com/wp-json/fluent-crm/v2/sequences/do-bulk-action`

This endpoint deletes multiple email sequences. Make sure you are passing the data in body as raw JSON format. Below there's an example added:

`
{
  "sequence_ids": [1, 2]
}
`

### URL Parameters

Parameter | type  | Description
--------- |-------| -----------
sequence_ids | array | The ID of the sequence to delete 

