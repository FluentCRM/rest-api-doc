# Automation Funnels

## Get All Funnels

```shell
curl "https://yourdomain.com/wp-json/fluent-crm/v2/funnels?with[]=triggers" \
  -H "Authorization: BASIC API_USERNAME:API_PASSWORD"
```
> The above command returns JSON structured like this:

```json
{
    "funnels": {
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
                "type": "funnels",
                "title": "Lists Applied",
                "trigger_name": "fluentcrm_contact_added_to_lists",
                "status": "published",
                "conditions": {
                    "run_multiple": "yes"
                },
                "settings": {
                    "lists": [
                        "1"
                    ],
                    "select_type": "any"
                },
                "created_by": "1",
                "created_at": "2022-05-16 08:26:28",
                "updated_at": "2022-06-28 06:22:55",
                "subscribers_count": 0
            }
        ]
    },
    "triggers": {
        "edd_update_payment_status": {
            "category": "Easy Digital Downloads",
            "label": "Edd - New Order Success",
            "description": "This Funnel will start once new order will be added as successful payment",
            "icon": "fc-icon-edd_new_order_success"
        },
        "user_register": {
            "category": "WordPress Triggers",
            "label": "New User Sign Up",
            "description": "This Funnel will be initiated when a new user has been registered in your site",
            "icon": "fc-icon-wp_new_user_signup"
        },
        "pmpro_after_change_membership_level": {
            "category": "Paid Membership Pro",
            "label": "Membership Level assignment of a User",
            "icon": "fc-icon-paid_membership_pro_user_level",
            "description": "This funnel will start when a user is assigned to specified membership levels"
        },
        "pmpro_membership_post_membership_expiry": {
            "category": "Paid Membership Pro",
            "label": "Membership Level Expiration",
            "icon": "fc-icon-membership_level_ex_pmp",
            "description": "This funnel will start when a membership has been expired for a user"
        },
        "mepr-account-is-active": {
            "category": "MemberPress",
            "label": "A member added to a membership level",
            "icon": "fc-icon-memberpress_membership",
            "description": "This funnel will start when a membership level get activated for a member"
        },
        "rcp_membership_post_activate": {
            "category": "Restrict Content Pro",
            "label": "A member added to a membership level",
            "icon": "fc-icon-rcp_membership_level",
            "description": "This funnel will start when a member is added to a level for the first time"
        },
        "learndash_update_course_access": {
            "category": "LearnDash",
            "label": "Enrolls in a Course",
            "icon": "fc-icon-learndash_enroll_course",
            "description": "This funnel will start when a student is enrolled in a course"
        },
        "rcp_membership_post_cancel": {
            "category": "Restrict Content Pro",
            "label": "Membership cancelled",
            "icon": "fc-icon-rcp_membership_cancle",
            "description": "This funnel will start when a membership has been cancelled"
        },
        "learndash_course_completed": {
            "category": "LearnDash",
            "label": "Completes a Course",
            "icon": "fc-icon-learndash_complete_course",
            "description": "This Funnel will start when a student completes a course"
        },
        "wp_login": {
            "category": "WordPress Triggers",
            "label": "User Login",
            "description": "This Funnel will be initiated when a user login to your site",
            "icon": "fc-icon-wp_new_user_signup"
        },
        "fluentcrm_contact_added_to_lists": {
            "category": "CRM",
            "label": "List Applied",
            "description": "This will run when selected lists have been applied to a contact",
            "icon": "fc-icon-list_applied_2"
        },
        "fluentcrm_contact_removed_from_lists": {
            "category": "CRM",
            "label": "List Removed",
            "description": "This will run when selected lists have been removed from a contact",
            "icon": "fc-icon-list_removed"
        },
        "fluentcrm_contact_added_to_tags": {
            "category": "CRM",
            "label": "Tag Applied",
            "description": "This will run when selected tags have been applied to a contact",
            "icon": "fc-icon-tag_applied"
        },
        "fluentcrm_contact_removed_from_tags": {
            "category": "CRM",
            "label": "Tag Removed",
            "description": "This will run when selected Tags have been removed from a contact",
            "icon": "fc-icon-tag_removed"
        },
        "woocommerce_order_status_processing": {
            "category": "WooCommerce",
            "label": "New Order (Processing)",
            "description": "This Funnel will start once new order has been placed as processing",
            "icon": "fc-icon-woo_new_order"
        },
        "woocommerce_order_status_completed": {
            "category": "WooCommerce",
            "label": "Order Completed",
            "icon": "fc-icon-woo_order_complete",
            "description": "This Funnel will start once new order has been marked as completed"
        },
        "woocommerce_order_refunded": {
            "category": "WooCommerce",
            "label": "Order Refunded",
            "icon": "fc-icon-woo_refund",
            "description": "This Automation will start once an order get refunded"
        },
        "learndash_lesson_completed": {
            "category": "LearnDash",
            "label": "Completes a Lesson",
            "icon": "fc-icon-learndash_complete_lesson",
            "description": "This Funnel will start a student completes a lesson"
        },
        "learndash_topic_completed": {
            "category": "LearnDash",
            "label": "Completes a Topic",
            "description": "This funnel will start when a user is completes a lesson topic"
        },
        "ld_added_group_access": {
            "category": "LearnDash",
            "label": "Enrolls in a Group",
            "icon": "fc-icon-learndash_course_group",
            "description": "This funnel will start when a user is enrolled in a group"
        },
        "mepr-event-transaction-expired": {
            "category": "MemberPress",
            "label": "A Subscription expired",
            "description": "This funnel will start when a subscription has been expired"
        },
        "woocommerce_order_status_changed": {
            "category": "WooCommerce",
            "label": "Order Status Changed",
            "description": "This Funnel will start when a Order status will change from one state to another",
            "icon": "fc-icon-woo"
        },
        "fluentform_submission_inserted": {
            "category": "CRM",
            "label": "New Form Submission (Fluent Forms)",
            "description": "This Funnel will be initiated when a new form submission has been submitted",
            "icon": "fc-icon-fluentforms"
        }
    }
}
```

This endpoint retrieves all funnels.

### HTTP Request

`GET https://yourdomain.com/wp-json/fluent-crm/v2/funnels`

### URL Parameters

Parameter | Type | Description                                     | Default
-----------| ------ |-------------------------------------------------|---------
| per_page  | int | Records per page                                |         |
| page      | int  | Page Number for Pagination                      |         |
| search    | string | Search Parameter for filtering funnels          |         |
| sort_by   | string | Order By funnel column Value to sort funnels   | id      |
| sort_type     | string | Order Type funnel column Value to sort funnels | DESC    |
| with[]    | array | Get Additional funnel Meta Properties          |         |

***Possible with parameters:***

- triggers

## Get a Specific funnel


```shell
curl "https://yourdomain.com/wp-json/fluent-crm/v2/funnels/<ID>" \
  -H "Authorization: BASIC API_USERNAME:API_PASSWORD"
```

> The above command returns JSON structured like this:

```json
{
  "funnel": {
    "id": 1,
    "type": "funnels",
    "title": "ss",
    "trigger_name": "fluentcrm_contact_added_to_lists",
    "status": "published",
    "conditions": {
      "run_multiple": "yes"
    },
    "settings": {
      "lists": [
        "19"
      ],
      "select_type": "any"
    },
    "created_by": "1",
    "created_at": "2022-08-16 06:22:48",
    "updated_at": "2022-08-18 02:56:36",
    "trigger": {
      "category": "CRM",
      "label": "List Applied",
      "description": "This will run when selected lists have been applied to a contact",
      "icon": "fc-icon-list_applied_2"
    },
    "settingsFields": {
      "title": "List Applied",
      "sub_title": "This will run when selected lists have been applied to a contact",
      "fields": {
        "lists": {
          "type": "option_selectors",
          "option_key": "lists",
          "is_multiple": true,
          "label": "Select Lists",
          "placeholder": "Select List"
        },
        "select_type": {
          "label": "Run When",
          "type": "radio",
          "options": [
            {
              "id": "any",
              "title": "contact added in any of the selected lists"
            },
            {
              "id": "all",
              "title": "contact added in all of the selected lists"
            }
          ],
          "dependency": {
            "depends_on": "lists",
            "operator": "!=",
            "value": []
          }
        }
      }
    },
    "conditionFields": {
      "run_multiple": {
        "type": "yes_no_check",
        "label": "",
        "check_label": "Restart the Automation Multiple times for a contact for this event. (Only enable if you want to restart automation for the same contact)",
        "inline_help": "If you enable, then it will restart the automation for a contact if the contact already in the automation. Otherwise, It will just skip if already exist"
      }
    },
    "description": ""
  }
}
```

This endpoint retrieves all funnels.

### HTTP Request

`GET https://yourdomain.com/wp-json/fluent-crm/v2/funnels/<ID>`

### URL Parameters

Parameter | Type | Description                                     | Default
-----------| ------ |-------------------------------------------------|---------
| with[]    | array | Get Additional funnel Meta Properties          |         |

***Possible with parameters:***

- blocks
- block_fields
- funnel_sequences

## Get Subscribers from a specific funnel


```shell
curl "https://yourdomain.com/wp-json/fluent-crm/v2/funnels/<ID>/subscribers" \
  -H "Authorization: BASIC API_USERNAME:API_PASSWORD"
```

> The above command returns JSON structured like this:

```json
{
    "funnel_subscribers": {
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
                "id": 199,
                "funnel_id": "25",
                "starting_sequence_id": null,
                "next_sequence": "6",
                "subscriber_id": "17216",
                "last_sequence_id": "45",
                "next_sequence_id": "43",
                "last_sequence_status": "complete",
                "status": "cancelled",
                "type": "funnel",
                "last_executed_time": "2022-08-19 10:46:24",
                "next_execution_time": "2022-08-19 12:00:24",
                "notes": null,
                "source_trigger_name": "fluentcrm_contact_added_to_lists",
                "source_ref_id": null,
                "created_at": "2022-08-19 10:45:12",
                "updated_at": "2022-08-19 10:50:51",
                "subscriber": {
                    "id": 17216,
                    "user_id": null,
                    "hash": "fe48b7b2cb1f37b5f11dfbbac11d9a73",
                    "contact_owner": null,
                    "company_id": null,
                    "prefix": null,
                    "first_name": "fname",
                    "last_name": "lname",
                    "email": "example@gmail.com",
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
                    "status": "unsubscribed",
                    "contact_type": "lead",
                    "source": "FluentForms",
                    "avatar": null,
                    "date_of_birth": null,
                    "created_at": "2022-08-19 10:45:12",
                    "last_activity": "2022-08-19 10:50:10",
                    "updated_at": "2022-08-19 10:50:51",
                    "full_name": "fname lname",
                    "photo": "https://www.gravatar.com/avatar/fe48b7b2cb1f37b5f11dfbbac11d9a73?s=128"
                },
                "last_sequence": null,
                "next_sequence_item": null,
                "metrics": [
                    {
                        "id": 1,
                        "funnel_id": "1",
                        "sequence_id": "1",
                        "subscriber_id": "1",
                        "benchmark_value": "0",
                        "benchmark_currency": "USD",
                        "status": "completed",
                        "notes": null,
                        "created_at": "2022-08-19 10:46:22",
                        "updated_at": "2022-08-19 10:46:22"
                    }
                ]
            }
        ]
    }
}
```

This endpoint get subscribers from a specific funnel.

### HTTP Request

`GET https://yourdomain.com/wp-json/fluent-crm/v2/funnels/<ID>/subscribers`

### URL Parameters

 Parameter | Type   | Description
-----------|--------|----------------------------------------------------------------
| per_page  | int    | Records per page
| page      | int    | Page Number for Pagination          
| search    | string | Search Parameter for filtering subscribers            
| status    | string | Status slugs to filter subscribers         
| with      | array  | Get Additional subscriber Meta Properties         

***Possible with parameters:***

- funnel
- sequences


## Duplicate a Specific Funnel

```shell
curl "https://yourdomain.com/wp-json/fluent-crm/v2/funnels/<ID>/clone" \
  -H "Authorization: BASIC API_USERNAME:API_PASSWORD"
```

> The above command returns JSON structured like this:

```json
{
  "message": "Funnel has been successfully cloned",
  "funnel": {
    "title": "[Copy] List Apply Trigger",
    "trigger_name": "fluentcrm_contact_added_to_lists",
    "status": "draft",
    "conditions": {
      "run_multiple": "yes"
    },
    "settings": {
      "lists": [
        "3"
      ],
      "select_type": "any"
    },
    "created_by": 0,
    "type": "funnels",
    "updated_at": "2022-08-30 03:43:01",
    "created_at": "2022-08-30 03:43:01",
    "id": 3
  }
}
```

This endpoint duplicate a email sequence.

### HTTP Request

`POST https://yourdomain.com/wp-json/fluent-crm/v2/funnels/<ID>/clone`


## Get report of a Specific Funnel

```shell
curl "https://yourdomain.com/wp-json/fluent-crm/v2/funnels/<ID>/report" \
  -H "Authorization: BASIC API_USERNAME:API_PASSWORD"
```

> The above command returns JSON structured like this:

```json
{
    "stats": {
        "metrics": [
            {
                "label": "Entrance",
                "count": 6,
                "sequence_id": 0,
                "type": "root",
                "percent": 100,
                "percent_text": 100,
                "previous_step_count": 6,
                "drop_count": 0,
                "drop_percent": 0
            }
        ],
        "total_revenue": 0,
        "total_revenue_formatted": "0.00",
        "revenue_currency": "USD"
    }
}
```

This endpoint get report of a specific funnel.

### HTTP Request

`GET https://yourdomain.com/wp-json/fluent-crm/v2/funnels/<ID>/report`

## Delete Funnel

```shell
curl "https://yourdomain.com/wp-json/fluent-crm/v2/funnels/<ID>" \
  -H "Authorization: BASIC API_USERNAME:API_PASSWORD"
```

> The above command returns JSON structured like this:

```json
{
  "message": "Funnel has been deleted"
}
```

This endpoint deletes funnels.

### HTTP Request

`DELETE https://yourdomain.com/wp-json/fluent-crm/v2/funnels/<ID>`


### Delete multiple funnels
`POST https://yourdomain.com/wp-json/fluent-crm/v2/funnels/do-bulk-action`

This endpoint deletes funnels. Make sure you are passing the data in body as raw JSON format. Below there's an example added:

`
{
"action_name": "delete_funnels",
"funnel_ids": [1, 2]
}
`

### URL Parameters

Parameter | type  | Description
--------- |-------| -----------
funnel_ids | array | The ID of the funnel to delete 


