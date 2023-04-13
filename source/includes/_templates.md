# Email Templates

## Get All Email Templates

```shell
curl "https://yourdomain.com/wp-json/fluent-crm/v2/templates" \
  -H "Authorization: BASIC API_USERNAME:API_PASSWORD"
```
> The above command returns JSON structured like this:

```json
{
    "templates": {
        "total": 18,
        "per_page": 15,
        "current_page": 1,
        "last_page": 2,
        "next_page_url": "/wp-json/fluent-crm/v2/templates?page=2",
        "prev_page_url": null,
        "from": 1,
        "to": 15,
        "data": [
            {
                "ID": 713,
                "post_author": "1",
                "post_date": "2022-08-08 06:46:21",
                "post_date_gmt": "2022-08-08 06:46:21",
                "post_content": "<!-- wp:paragraph -->\n<p>Start Writing Here</p>\n<!-- /wp:paragraph -->\n\n<!-- wp:buttons -->\n<div class=\"wp-block-buttons\"><!-- wp:button {\"style\":{\"border\":{\"radius\":\"5px\"}}} -->\n<div class=\"wp-block-button\"><a class=\"wp-block-button__link\" style=\"border-radius:5px\">hello</a></div>\n<!-- /wp:button --></div>\n<!-- /wp:buttons -->",
                "post_title": "Post title",
                "post_excerpt": "Post Excerpt",
                "post_status": "draft",
                "comment_status": "closed",
                "ping_status": "closed",
                "post_password": "",
                "post_name": "",
                "to_ping": "",
                "pinged": "",
                "post_modified": "2022-08-08 08:16:07",
                "post_modified_gmt": "2022-08-08 08:16:07",
                "post_content_filtered": "",
                "post_parent": "0",
                "guid": "http://test-plugins.test/?p=713",
                "menu_order": "0",
                "post_type": "fc_template",
                "post_mime_type": "",
                "comment_count": "0"
            }
        ]
    }
}
```
This endpoint retrieves all email Templates.

### HTTP Request

`GET https://yourdomain.com/wp-json/fluent-crm/v2/templates`

### URL Parameters

Parameter | Type   | Description                                        | Default
------- |--------|----------------------------------------------------| -----
| per_page |  int | Records per page                                   | |
| page |    int   | Page Number for Pagination                         | |
| search | string | Search Parameter for filtering templates           | |
| order_by | string | Order By template column Value to sort tmeplates   | ID |
| order_type | string | Order Type template column Value to sort templates | desc |

<aside class="success">
Remember — Use authentication Headers
</aside>

## Get a Specific Email Template


```shell
curl "https://yourdomain.com/wp-json/fluent-crm/v2/templates/<ID>" \
  -H "Authorization: BASIC API_USERNAME:API_PASSWORD"
```

> The above command returns JSON structured like this:

```json
{
    "template": {
        "post_title": "Post Title",
        "post_content": "<!-- wp:paragraph -->\n<p>Start Writing Here</p>\n<!-- /wp:paragraph -->\n\n<!-- wp:heading -->\n<h2 id=\"cool\">Cool</h2>\n<!-- /wp:heading -->",
        "post_excerpt": "Post Excerpt",
        "email_subject": "Email Subject",
        "edit_type": "html",
        "design_template": "simple",
        "settings": {
            "template_config": {
                "content_width": "700",
                "headings_font_family": "-apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Helvetica, Arial, sans-serif, 'Apple Color Emoji', 'Segoe UI Emoji', 'Segoe UI Symbol'",
                "text_color": "#202020",
                "link_color": "",
                "headings_color": "#202020",
                "body_bg_color": "#FF0000",
                "content_bg_color": "#FFFFFF",
                "footer_text_color": "#202020",
                "content_font_family": "-apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Helvetica, Arial, sans-serif, 'Apple Color Emoji', 'Segoe UI Emoji', 'Segoe UI Symbol'",
                "disable_footer": "no"
            }
        }
    }
}
```

This endpoint retrieves a specific email template.

### HTTP Request

`GET https://yourdomain.com/wp-json/fluent-crm/v2/templates/<ID>`

## Create a new email template

```shell

curl 'https://fcrm.test/wp-json/fluent-crm/v2/templates' \
  -H "Authorization: BASIC API_USERNAME:API_PASSWORD" \
  --data-raw 'template[post_title]=Test&template[post_content]=Start Writing&template[post_excerpt]=Post Excerpt&template[design_template]=simple&template[email_subject]=Subject&template[edit_type]=html' \
	 
```
> The above command creates a new email template in Fluent CRM and returns the data in JSON.


```json 
{
    "message": "Template successfully created",
    "template_id": 1
}
```

This endpoint creates a new email template.

### HTTP Request

`POST https://yourdomain.com/wp-json/fluent-crm/v2/templates`

### URL Parameters

Parameter | Type | Required| Description | Default 
--------- | ---- | ------- | ----------- |--------
template[post_title] | string | no | Add title of a tmeplate |        | 
template[post_content] | string | no | Add content of a tmeplate |        |
template[post_excerpt] | string | no | Add excerpt of a tmeplate |        |
template[email_subject] | string | no | Add email subject of a tmeplate |        |
template[edit_type] | string | no | Add edit type of a tmeplate | html   |
template[design_template] | string | no | Add design type of a tmeplate | simple

***Possible design_template values:***

- simple
- plain
- classic
- raw_classic
- raw_html



## Duplicate a email template

```shell

```

```json 
{
    "message": "Template successfully duplicated",
    "template_id": 1
}
```

This endpoint duplicate a template.

### HTTP Request

`POST https://yourdomain.com/wp-json/fluent-crm/v2/templates/duplicate/<ID>`


## Update any email template data

```shell

```

>The above command JSON structured like this:

```json
{
  "message": "Template successfully updated",
  "template_id": "1"
}
```


This endpoint update a specific email template. Make sure you are passing the data in body as raw JSON format. Below there's an example added.<br>
```
{
  "template":{
    "post_title": "Updated Title",
    "post_content": "Start Writing Here",
    "post_excerpt": "updated excerpt",
    "email_subject": "updated email subject",
    "design_template": "simple"
  }
}
```


### HTTP Request

`PUT https://fcrm.test/wp-json/fluent-crm/v2/templates/<ID>`


### URL Parameters

Parameter | Type | Required| Description
--------- | ---- | ------- | -----------
template[post_title] | string | no | Add title of a tmeplate
template[post_content] | string | no | Add content of a tmeplate
template[post_excerpt] | string | no | Add excerpt of a tmeplate
template[email_subject] | string | no | Add email subject of a tmeplate
template[edit_type] | string | no | Add edit type of a tmeplate
template[design_template] | string | no | Add design type of a tmeplate

***Possible design_template values:***

- simple
- plain
- classic
- raw_classic
- raw_html


## Delete Email Templates

```shell

```

```json
{
  "message": "The template has been deleted successfully."
}
```

This endpoint deletes a specific email template.

### HTTP Request

`DELETE https://yourdomain.com/wp-json/fluent-crm/v2/templates/<ID>`

### Delete Multiple email templates
`POST https://yourdomain.com/wp-json/fluent-crm/v2/templates/do-bulk-action`

This endpoint deletes multiple email templates. Make sure you are passing the data in body as raw JSON format. Below there's an example added: 
```
{
  "action_name": "delete_templates",
  "template_ids": [1, 2]
}
```

### URL Parameters

Parameter | type  | Description
--------- |-------| -----------
template_ids | array | The ID of the template to delete 

