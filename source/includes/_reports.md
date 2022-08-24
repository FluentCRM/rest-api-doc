
# Reports

## Get Dashboard Stats

```shell
curl --location --request GET 'https://yourdomain.com/wp-json/fluent-crm/v2/reports/dashboard-stats' \
--header 'Authorization: Basic API_USERNAME:API_PASSWORD'
```

> The above command returns JSON structured like this:

```json
{
    "stats": {
        "total_subscribers": {
            "title": "Total Contacts",
            "count": 114,
            "route": {
                "name": "subscribers"
            }
        },
        "total_campaigns": {
            "title": "Campaigns",
            "count": 18,
            "route": {
                "name": "campaigns"
            }
        },
        "email_sent": {
            "title": "Emails Sent",
            "count": 79,
            "route": {
                "name": "all_emails"
            }
        },
        "tags": {
            "title": "Tags",
            "count": 5,
            "route": {
                "name": "tags"
            }
        },
        "total_templates": {
            "title": "Email Templates",
            "count": 3,
            "route": {
                "name": "templates"
            }
        }
    },
    "sales": [
      {
         "title":"Earnings (Today)",
         "content":"&#36;0.00"
      },
      {
         "title":"Earnings (Current Month)",
         "content":"&#36;0.00"
      },
      {
         "title":"Earnings (All Time)",
         "content":"&#36;0.00"
      }
    ],
    "onboarding": {
        "total": 5,
        "completed": 3,
        "steps": [
            {
                "label": "Create a Tag",
                "completed": true,
                "route": {
                    "name": "tags"
                }
            },
            {
                "label": "Import Contacts",
                "completed": true,
                "route": {
                    "name": "subscribers"
                }
            },
            {
                "label": "Create a Campaign",
                "completed": false,
                "route": {
                    "name": "campaigns"
                }
            },
            {
                "label": "Create an Automation",
                "completed": true,
                "route": {
                    "name": "funnels"
                }
            },
            {
                "label": "Create a Form",
                "completed": false,
                "route": {
                    "name": "forms"
                }
            }
        ]
    },
    "quick_links": [
        {
            "title": "View Contacts",
            "url": "https://yourdomain.com/wp-admin/admin.php?page=fluentcrm-admin#/subscribers",
            "icon": "el-icon-user"
        },
        {
            "title": "Contact Segments",
            "url": "https://yourdomain.com/wp-admin/admin.php?page=fluentcrm-admin#/contact-groups/lists",
            "icon": "el-icon-folder"
        },
        {
            "title": "Email Campaigns",
            "url": "https://yourdomain.com/wp-admin/admin.php?page=fluentcrm-admin#/email/campaigns",
            "icon": "el-icon-message"
        },
        {
            "title": "Email Sequences",
            "url": "https://yourdomain.com/wp-admin/admin.php?page=fluentcrm-admin#/email/sequences",
            "icon": "el-icon-alarm-clock"
        },
        {
            "title": "Forms",
            "url": "https://yourdomain.com/wp-admin/admin.php?page=fluentcrm-admin#/forms",
            "icon": "el-icon-document-checked"
        },
        {
            "title": "Automations",
            "url": "https://yourdomain.com/wp-admin/admin.php?page=fluentcrm-admin#/funnels",
            "icon": "el-icon-cold-drink"
        },
        {
            "title": "Settings",
            "url": "https://yourdomain.com/wp-admin/admin.php?page=fluentcrm-admin#/settings",
            "icon": "el-icon-setting"
        },
        {
            "title": "Documentations",
            "url": "https://yourdomain.com/wp-admin/admin.php?page=fluentcrm-admin#/documentation",
            "icon": "el-icon-document"
        }
    ],
    "ff_config": {
        "is_installed": true,
        "create_form_link": "https://yourdomain.com/wp-admin/admin.php?page=fluent_forms#add=1"
    }
}
```

This endpoint returns numbers of total contact, total campaigns, total email sent, total tags & total emails templates, quick_links, onboarding, sales and many more information.

### HTTP Request
`GET https://yourdomain.com/wp-json/fluent-crm/v2/reports/dashboard-stats`

## Get Subscribers Growth Rate

```shell
curl --location --request GET 'https://yourdomain.com/wp-json/fluent-crm/v2/reports/subscribers?date_range[]=2020-02-01&date_range[]=2022-02-10' \
--header 'Authorization: Basic API_USERNAME:API_PASSWORD'
```
> The above command returns JSON structured like this:

```json
{
    "stats": {
        "Feb 2020": 90,
        "Mar 2020": 60,
        "Apr 2020": 34,
        "May 2020": 76,
        "Jun 2020": 98,
        "Jul 2020": 96,
        "Aug 2020": 76,
        "Sep 2020": 87,
        "Oct 2020": 78,
        "Nov 2020": 87,
        "Dec 2020": 65,
        "Jan 2021": 88,
        "Feb 2021": 45,
        "Mar 2021": 56,
        "Apr 2021": 87,
        "May 2021": 105,
        "Jun 2021": 65,
        "Jul 2021": 109,
        "Aug 2021": 67,
        "Sep 2021": 54,
        "Oct 2021": 34,
        "Nov 2021": 79,
        "Dec 2021": 87,
        "Jan 2022": 56,
        "Feb 2022": 88
    }
}
```

This endpoint returns subscribers growth rate.

### HTTP Request

`GET https://yourdomain.com/wp-json/fluent-crm/v2/reports/reports/subscribers`

### URL Parameters

Parameter    | Type   | Description
---------    |--------|-----------
date_range[] | Date   | Accept from date & to date. And date format should be " YYYY-MM-DD ".

***How To Input The Date Range In URL?***

date_range[]=2020-02-01 ``1st date will work for from date.`` <br>
date_range[]=2022-02-10 ``2nd date will work for to date.`` <br>
date_range[]=2020-02-01&date_range[]=2022-02-10 ``Use like this one in the URL``

## Get Email Sending Stats

```shell
curl --location --request GET 'https://yourdomain.com/wp-json/fluent-crm/v2/reports/email-sents?date_range[]=2020-02-01&date_range[]=2022-02-10' \
--header 'Authorization: Basic API_USERNAME:API_PASSWORD'
```
> The above command returns JSON structured like this:

```json
{
    "stats": {
        "2020-03-03": 37,
        "2020-03-04": 54,
        "2020-03-05": 31,
        "2020-03-06": 35,
        "2020-03-07": 21,
        "2020-03-08": 31,
        "2020-03-09": 35,
        "2020-03-10": 43,
        "2020-03-11": 34
    }
}
```

This endpoint returns email sending rate.

### HTTP Request

`GET https://yourdomain.com/wp-json/fluent-crm/v2/reports/reports/email-sents`

### URL Parameters

Parameter | Type | Description
--------- | ------|-----------
date_range[] | Date | Accept from date & to date. And date format should be " YYYY-MM-DD ".

***How To Input The Date Range In URL?***

date_range[]=2020-03-03 ``1st date will work for from date.`` <br>
date_range[]=2022-03-11 ``2nd date will work for to date.`` <br>
date_range[]=2020-03-03&date_range[]=2022-03-11 ``Use like this one in the URL``

## Get Email Open Stats

```shell
curl --location --request GET 'https://yourdomain.com/wp-json/fluent-crm/v2/reports/email-opens?date_range[]=2020-02-01&date_range[]=2022-02-10' \
--header 'Authorization: Basic API_USERNAME:API_PASSWORD'
```
> The above command returns JSON structured like this:

```json
{
    "stats": {
        "2020-03-03": 37,
        "2020-03-04": 54,
        "2020-03-05": 31,
        "2020-03-06": 35,
        "2020-03-07": 21,
        "2020-03-08": 31,
        "2020-03-09": 35,
        "2020-03-10": 43,
        "2020-03-11": 34
    }
}
```

This endpoint returns email sending rate.

### HTTP Request

`GET https://yourdomain.com/wp-json/fluent-crm/v2/reports/reports/email-opens`

### URL Parameters

Parameter | Type | Description
--------- | ------|-----------
date_range[] | Date | Accept from date & to date. And date format should be " YYYY-MM-DD ".

***How To Input The Date Range In URL?***

date_range[]=2020-03-03 ``1st date will work for from date.`` <br>
date_range[]=2022-03-11 ``2nd date will work for to date.`` <br>
date_range[]=2020-03-03&date_range[]=2022-03-11 ``Use like this one in the URL``

## Get Email Link Click Stats

```shell
curl --location --request GET 'https://yourdomain.com/wp-json/fluent-crm/v2/reports/email-clicks?date_range[]=2020-02-01&date_range[]=2022-02-10' \
--header 'Authorization: Basic API_USERNAME:API_PASSWORD'
```
> The above command returns JSON structured like this:

```json
{
    "stats": {
        "2020-03-03": 37,
        "2020-03-04": 54,
        "2020-03-05": 31,
        "2020-03-06": 35,
        "2020-03-07": 21,
        "2020-03-08": 31,
        "2020-03-09": 35,
        "2020-03-10": 43,
        "2020-03-11": 34
    }
}
```

This endpoint returns email sending rate.

### HTTP Request

`GET https://yourdomain.com/wp-json/fluent-crm/v2/reports/reports/email-clicks`

### URL Parameters

Parameter | Type | Description
--------- | ------|-----------
date_range[] | Date | Accept from date & to date. And date format should be " YYYY-MM-DD ".

***How To Input The Date Range In URL?***

date_range[]=2020-03-03 ``1st date will work for from date.`` <br>
date_range[]=2022-03-11 ``2nd date will work for to date.`` <br>
date_range[]=2020-03-03&date_range[]=2022-03-11 ``Use like this one in the URL``


## Get Options

```shell
curl --location --request GET 'https://yourdomain.com/wp-json/fluent-crm/v2/reports/options?fields=roles,custom_fields' \
--header 'Authorization: Basic API_USERNAME:API_PASSWORD'
```

> The above command returns JSON structured like this:

```json
{
  "options": {
    "roles": {
      "subscriber": {
        "name": "Subscriber",
        "capabilities": {
          "read": true,
          "level_0": true
        }
      }
    },
    "custom_fields": [
      {
        "field_key": "single-select",
        "type": "select-one",
        "label": "Blood Group",
        "options": [
          "A+",
          "A-",
          "B+",
          "B-"
        ],
        "slug": "blood_group"
      },
      {
        "field_key": "text",
        "type": "text",
        "label": "Username",
        "slug": "username"
      }
    ]
  }
}
```

This endpoint returns options.

### HTTP Request
`GET https://yourdomain.com/wp-json/fluent-crm/v2/reports/options`

### URL Parameters

Parameter | Description
--------- | -----------
fields | get specific options **e.g. fields=countries,lists,tags**

***Possible fields parameters***

- countries
- lists
- tags
- campaigns
- email_sequences
- automation_funnels
- statuses
- editable_statuses
- contact_types
- sampleCsv
- segments
- roles
- profile_sections
- custom_fields


## Get Ajax Options

```shell
curl --location --request GET 'https://yourdomain.com/wp-json/fluent-crm/v2/reports/ajax-options?option_key=woo_categories' \
--header 'Authorization: Basic API_USERNAME:API_PASSWORD'
```

> The above command returns JSON structured like this:

```json
{
  "options": [
    {
      "id": 27,
      "title": "Smartphone"
    },
    {
      "id": 26,
      "title": "Soft drink"
    },
    {
      "id": 25,
      "title": "Uncategorized"
    }
  ]
}
```

This endpoint returns ajax options.

### HTTP Request
`GET https://yourdomain.com/wp-json/fluent-crm/v2/reports/ajax-options`

### URL Parameters

Parameter | Type | Description | Default
--------- | ----------- | ------------- | ----------
option_key | string | get specific plugin's options | empty
search | string | Search Parameter for filtering | empty
values | array | Search By Option Ids | empty

***Possible option_key parameters***

- woo_categories
- woo_products
- product_selector_woo
- product_selector_woo_order
- edd_products
- product_selector_edd
- product_selector_rcp
- edd_coupons
- product_selector_lifterlms
- product_selector_lifterlms_groups
- product_selector_learndash
- product_selector_learndash_groups
- product_selector_pmpro
- product_selector_tutorlms
- product_selector_wishlist
- woo_coupons


## Get Taxonomy Terms

```shell
curl --location --request GET 'https://yourdomain.com/wp-json/fluent-crm/v2/reports/taxonomy-terms' \
--header 'Authorization: Basic API_USERNAME:API_PASSWORD'
```

> The above command returns JSON structured like this:

```json
{
  "options": [
    {
      "id": "4",
      "title": "Advanced"
    },
    {
      "id": "37",
      "title": "Aged Oak 691D"
    },
    {
      "id": "32",
      "title": "API"
    },
    {
      "id": "49",
      "title": "Backend"
    },
    {
      "id": "48",
      "title": "Basic"
    }
  ]
}
```

This endpoint returns taxonomy terms.

### HTTP Request
`GET https://yourdomain.com/wp-json/fluent-crm/v2/reports/taxonomy-terms`

### URL Parameters

Parameter | Type | Description                    | Default
--------- | ----------- |--------------------------------| ----------
taxonomy | string | get specific taxonomy          | empty
search | string | Search Parameter for filtering | empty
values | array | Search By texonomy Ids         | empty


## Get Emails

```shell
curl --location --request GET 'https://yourdomain.com/wp-json/fluent-crm/v2/reports/emails' \
--header 'Authorization: Basic API_USERNAME:API_PASSWORD'
```

> The above command returns JSON structured like this:

```json
{
  "emails": {
    "total": 207,
    "per_page": 15,
    "current_page": 1,
    "last_page": 14,
    "next_page_url": "/wp-json/fluent-crm/v2/reports/emails?page=2",
    "prev_page_url": null,
    "from": 1,
    "to": 15,
    "data": [
      {
        "id": 314,
        "campaign_id": "41",
        "email_type": "campaign",
        "subscriber_id": "1905",
        "email_subject_id": null,
        "email_address": "koxohen302@ukgent.com",
        "email_subject": "Heleoo",
        "email_body": "",
        "email_headers": [],
        "is_open": "0",
        "is_parsed": "1",
        "click_counter": null,
        "status": "sent",
        "note": null,
        "scheduled_at": "2022-08-22 16:53:48",
        "email_hash": "ae8a3f46-2f77-4ea3-921a-3fa04b941079",
        "created_at": "2022-08-22 16:47:28",
        "updated_at": "2022-08-22 16:53:48",
        "subscriber": {
          "id": 1905,
          "user_id": null,
          "hash": "3f0ed92b231d748a1e4539fc9e3617d4",
          "contact_owner": null,
          "company_id": null,
          "prefix": null,
          "first_name": "Koxohen",
          "last_name": "302",
          "email": "koxohen302@ukgent.com",
          "timezone": null,
          "address_line_1": "Modina Market, Sylhet",
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
          "source": "FluentForms",
          "avatar": null,
          "date_of_birth": null,
          "created_at": "2022-08-19 10:55:22",
          "last_activity": null,
          "updated_at": "2022-08-19 10:55:39",
          "full_name": "Koxohen 302",
          "photo": "https://www.gravatar.com/avatar/3f0ed92b231d748a1e4539fc9e3617d4?s=128"
        },
        "campaign": {
          "id": 41,
          "parent_id": null,
          "type": "campaign",
          "title": "Order Status",
          "available_urls": null,
          "slug": "order-status",
          "status": "scheduled",
          "template_id": "0",
          "email_subject": "Heleoo",
          "email_pre_header": "",
          "email_body": "<!-- wp:paragraph -->\n<p>Start Writing Here</p>\n<!-- /wp:paragraph -->",
          "recipients_count": 44,
          "delay": "0",
          "utm_status": "0",
          "utm_source": "",
          "utm_medium": "",
          "utm_campaign": "",
          "utm_term": "",
          "utm_content": "",
          "design_template": "simple",
          "scheduled_at": "2022-08-22 16:53:02",
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
          "created_at": "2022-07-20 11:11:20",
          "updated_at": "2022-08-22 16:47:28"
        }
      },
      "...."
    ]
  }
}
```

This endpoint returns taxonomy terms.

### HTTP Request
`GET https://yourdomain.com/wp-json/fluent-crm/v2/reports/emails`


## Delete Bulk Emails

```shell
curl --location --request DELETE 'https://yourdomain.com/wp-json/fluent-crm/v2/reports/emails' \
--header 'Authorization: Basic API_USERNAME:API_PASSWORD' \
--data-raw 'email_ids[]=314&email_ids[]=313&email_ids[]=312' 
```

> The above command returns JSON structured like this:

```json
{
  "message": "Selected emails has been deleted"
}
```

This endpoint returns message after deleting emails by email_ids.

### HTTP Request
`DELETE https://yourdomain.com/wp-json/fluent-crm/v2/reports/emails`

### URL Parameters

Parameter | Type   | Description                    | Required 
--------- |--------|--------------------------------| ----------
email_ids | array  | delete emails by provided id   | true


## Get Advance Providers

```shell
curl --location --request GET 'https://yourdomain.com/wp-json/fluent-crm/v2/reports/advanced-providers' \
--header 'Authorization: Basic API_USERNAME:API_PASSWORD'
```

> The above command returns JSON structured like this:

```json
{
  "providers": {
    "crm": {
      "title": "CRM"
    },
    "learndash": {
      "title": "LearnDash"
    }
  }
}
```

This endpoint returns advance providers.

### HTTP Request
`GET https://yourdomain.com/wp-json/fluent-crm/v2/reports/advanced-providers`

