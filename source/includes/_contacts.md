
# Contacts

## Get All Contacts

```shell
curl "https://yourdomain.com/wp-json/fluent-crm/v2/subscribers" \
  -H "Authorization: BASIC API_USERNAME:API_PASSWORD"
```
> The above command returns JSON structured like this:

```json
{
  "current_page": 1,
  "per_page": 10,
  "from": 1,
  "to": 10,
  "last_page": 493,
  "total": 9860,
  "data": [
    {
      "id": "9860",
      "user_id": "5984",
      "hash": "4a6f1ed89704814c100a954ec403cd2f",
      "contact_owner": "string",
      "company_id": "string",
      "prefix": "string",
      "first_name": "Kelli",
      "last_name": "Hand",
      "email": "sonny.pacocha@example.net",
      "timezone": "string",
      "address_line_1": "string",
      "address_line_2": "string",
      "postal_code": "string",
      "city": "string",
      "state": "string",
      "country": "string",
      "ip": "string",
      "latitude": "string",
      "longitude": "string",
      "total_points": "0",
      "life_time_value": "0",
      "phone": "string",
      "status": "subscribed",
      "contact_type": "lead",
      "source": "wp_users",
      "avatar": "string",
      "date_of_birth": "string",
      "created_at": {},
      "last_activity": "string",
      "updated_at": "string",
      "photo": "https://www.gravatar.com/avatar/4a6f1ed89704814c100a954ec403cd2f?s=128",
      "full_name": "Kelli Hand",
      "tags": [
        {
          "id": "2",
          "title": "Fluent Forms Users",
          "slug": "fluent-forms-users",
          "description": "string",
          "created_at": {},
          "updated_at": {},
          "pivot": {
            "subscriber_id": "9860",
            "object_id": "2",
            "object_type": "FluentCrm\\App\\Models\\Tag",
            "created_at": {},
            "updated_at": {}
          }
        }
      ],
      "lists": [
        {
          "id": "1",
          "title": "List Item 1",
          "slug": "list-item-1",
          "description": "string",
          "is_public": "0",
          "created_at": {},
          "updated_at": {},
          "pivot": {
            "subscriber_id": "9860",
            "object_id": "1",
            "object_type": "FluentCrm\\App\\Models\\Lists",
            "created_at": {},
            "updated_at": {}
          }
        }
      ]
    }
  ]
}
```

This endpoint retrieves all Contact.

### HTTP Request

`GET https://yourdomain.com/wp-json/fluent-crm/v2/subscribers`

### URL Parameters

Parameter | Type | Description | Default
--------- | ------- | ----------- | -------
| per_page |  int | Records per page | 10 |
| page |    int   | Page Number for Pagination | 1 |
| search | string | Search Parameter for filtering contacts | |
| tags | array | Tag Ids to filter contacts | |
| lists | array | List Ids to filter contacts | |
| statuses | array | Status slugs to filter contacts | |
| order_by | string | Order By contact column Value to sort contacts | id |
| order_type | string | Order Type contact column Value to sort contacts | DESC |
| custom_fields | boolean | Flag to get custom contact field values too| false
| company_ids | array | Company Ids to filter contacts | |

***Possible statuses values:***

- subscribed
- unsubscribed
- pending
- bounced
- complained

<aside class="success">
Remember — Use authentication Headers
</aside>

## Get a Specific Contact


```shell
curl "https://yourdomain.com/wp-json/fluent-crm/v2/subscribers/<ID>" \
  -H "Authorization: BASIC API_USERNAME:API_PASSWORD"
```

> The above command returns JSON structured like this:

```json
{
  "subscriber":{
    "id":"7743",
    "user_id":"1",
    "hash":"5acfbfb0e8135fe5a1e36bb40d90ad69",
    "contact_owner":null,
    "company_id":null,
    "prefix":null,
    "first_name":"JeweldddXXX",
    "last_name":"JewelZZZ",
    "email":"cep.jewel@gmail.com",
    "timezone":null,
    "address_line_1":"283ddd",
    "address_line_2":"sda",
    "postal_code":"34521",
    "city":"New",
    "state":"ME",
    "country":"US",
    "ip":"127.0.0.1",
    "latitude":null,
    "longitude":null,
    "total_points":"0",
    "life_time_value":"0",
    "phone":"01723371621",
    "status":"subscribed",
    "contact_type":"lead",
    "source":"woocommerce",
    "avatar":null,
    "date_of_birth":null,
    "created_at":"2021-07-17 21:08:30",
    "last_activity":"2021-07-18 13:45:42",
    "updated_at":"2021-07-18 20:22:48",
    "user_edit_url":"https:\/\/wp.lab\/wp-admin\/profile.php",
    "stats":{
      "emails":0,
      "opens":0,
      "clicks":0
    },
    "commerce_stat": [
      {
        "title": "Customer Since",
        "value": "March 24, 2022",
        "key": "customer_since",
        "actual_value": "2022-03-24 10:03:05"
      }
    ],
    "custom_values":{
      "some_number_field":"10",
      "checkbox":[
        "Value Option 1"
      ]
    },
    "photo":"https:\/\/www.gravatar.com\/avatar\/5acfbfb0e8135fe5a1e36bb40d90ad69?s=128",
    "full_name":"JeweldddXXX JewelZZZ",
    "tags":[
      {
        "id":"1",
        "title":"FluentCRM Users",
        "slug":"fluentcrm-users",
        "description":null,
        "created_at":"2021-07-17 21:06:25",
        "updated_at":"2021-07-17 21:06:25",
        "pivot":{
          "subscriber_id":"7743",
          "object_id":"1",
          "object_type":"FluentCrm\\App\\Models\\Tag",
          "created_at":"2021-07-19 17:30:52",
          "updated_at":"2021-07-19 17:30:52"
        }
      }
    ],
    "lists":[
      {
        "id":"1",
        "title":"List Item 1",
        "slug":"list-item-1",
        "description":null,
        "is_public":"0",
        "created_at":"2021-07-17 21:01:59",
        "updated_at":"2021-07-17 21:01:59",
        "pivot":{
          "subscriber_id":"7743",
          "object_id":"1",
          "object_type":"FluentCrm\\App\\Models\\Lists",
          "created_at":"2021-07-17 21:08:30",
          "updated_at":"2021-07-17 21:08:30"
        }
      }
    ]
  }
}
```

This endpoint retrieves a specific contact.

### HTTP Request

Get subscriber by id:  
`GET https://yourdomain.com/wp-json/fluent-crm/v2/subscribers/<ID>`

Or get by email:  
`GET https://yourdomain.com/wp-json/fluent-crm/v2/subscribers/0?get_by_email=<EMAIL>`

### URL Parameters

Parameter | Type | Description
--------- | ----------- | -----
with[] | array | Get Additional Contact Meta Properties

***Possible with parameters:***

- stats
- custom_fields
- subscriber.custom_values
- commerce_stat
- companies 


## Create a new contact

```shell

curl 'https://fcrm.test/wp-json/fluent-crm/v2/subscribers' \
  -H "Authorization: BASIC API_USERNAME:API_PASSWORD" \
  --data-raw 'first_name=Rafi&last_name=Ahmed&email=rafi%40authlab.io&phone=44+078+1961+0398&date_of_birth=2000-03-04&status=subscribed&address_line_1=1+Union+Street&address_line_2=64+Cunnery+Rd&city=Swansea&state=Swansea&postal_code=SA1+3EE&country=GB&tags%5B%5D=1&tags%5B%5D=2&lists%5B%5D=1&lists%5B%5D=2&custom_values%5Bcustom_field%5D=Custom+Field+Value&prefix=Mr&query_timestamp=1626770805540' \
	 
```
> The above command creates a new contact in Fluent CRM and returns the data in JSON.

```json 
{
    "message": "Successfully added the subscriber.",
    "contact": {
        "prefix": "Mr",
        "first_name": "Rafi",
        "last_name": "Ahmed",
        "email": "rafi@authlab.io",
        "phone": " 44 078 1961 0398",
        "date_of_birth": "2000-03-04",
        "address_line_1": "1 Union Street",
        "address_line_2": "64 Cunnery Rd",
        "city": "Swansea",
        "state": "Swansea",
        "country": "United Kingdom (UK)",
        "postal_code": "SA1 3EE",
        "status": "subscribed",
        "hash": "3f6e19a6d1fcf98c73e031882796091f",
        "updated_at": "2021-07-19 22:11:48",
        "created_at": "2021-07-19 22:11:48",
        "id": 17,
        "photo": "https://www.gravatar.com/avatar/3f6e19a6d1fcf98c73e031882796091f?s=128",
        "full_name": "Rafi Ahmed",
        "tags": [
            {
                "id": "1",
                "title": "User One",
                "slug": "user-one",
                "description": null,
                "created_at": "2021-07-19 08:25:34",
                "updated_at": "2021-07-19 08:25:34",
                "pivot": {
                    "subscriber_id": "17",
                    "object_id": "1",
                    "object_type": "FluentCrm\\App\\Models\\Tag",
                    "created_at": "2021-07-19 22:11:48",
                    "updated_at": "2021-07-19 22:11:48"
                }
            },
            {
                "id": "2",
                "title": "User Two",
                "slug": "user-two",
                "description": null,
                "created_at": "2021-07-19 08:25:34",
                "updated_at": "2021-07-19 08:25:34",
                "pivot": {
                    "subscriber_id": "17",
                    "object_id": "2",
                    "object_type": "FluentCrm\\App\\Models\\Tag",
                    "created_at": "2021-07-19 22:11:48",
                    "updated_at": "2021-07-19 22:11:48"
                }
            }
        ],
        "lists": [
            {
                "id": "1",
                "title": "User One",
                "slug": "user-one",
                "description": null,
                "is_public": "0",
                "created_at": "2021-07-19 08:25:22",
                "updated_at": "2021-07-19 08:25:22",
                "pivot": {
                    "subscriber_id": "17",
                    "object_id": "1",
                    "object_type": "FluentCrm\\App\\Models\\Lists",
                    "created_at": "2021-07-19 22:11:48",
                    "updated_at": "2021-07-19 22:11:48"
                }
            },
            {
                "id": "2",
                "title": "User Two",
                "slug": "user-two",
                "description": null,
                "is_public": "0",
                "created_at": "2021-07-19 08:25:22",
                "updated_at": "2021-07-19 08:25:22",
                "pivot": {
                    "subscriber_id": "17",
                    "object_id": "2",
                    "object_type": "FluentCrm\\App\\Models\\Lists",
                    "created_at": "2021-07-19 22:11:48",
                    "updated_at": "2021-07-19 22:11:48"
                }
            }
        ]
    },
    "action_type": "created"
}
```

This endpoint creates a new contact.

### HTTP Request

`POST https://yourdomain.com/wp-json/fluent-crm/v2/subscribers`

### URL Parameters

Parameter | Type | Required| Description
--------- | ---- | ------- | -----------
prefix | string | no | Add Name Prefix of a Contact
first_name | string | no | Add Contact's First Name
last_name | string | no | Add Contact's Last Name
email | email | yes | Add Contact's Email
phone | string | no | Add Contact's Phone Number
date_of_birth | string | no | Add Contact's Date Of Birth ( Format: YYYY-MM-DD )
address_line_1 | string | no | Add Contact's Address Line 1
address_line_2 | string | no | Add Contact's Address Line 2
city | string | no | Add Contact's City
state | string | no | Add Contact's State
country | string | no | Add Contact's Country
postal_code | string | no | Add Contact's ZIP Code
photo | string | no | Add Contact's Profile Picture
tags | array | no | Add Contact To One or Multiple Tags ( Tags data type is array & only takes the ID of a tag, e.g. **tags[]=1&tags[]=2** )
lists | array | no | Add Contact To One or Multiple Lists ( List data type is array & only takes the ID of a list e.g. **lists[]=1&lists[]=2**)
custom_values | array | no | Add Custom Value To a Contact ( Custom Field data type is array, To add data to custom field you have to define the key & value, key is custom field slug name, e.g. **custom_values[custom_field_slug]= Custom Field Value**)
__force_update | boolean | no | If you add this flag as true then contact will be updated if exist
status | string | yes | Add Contact's Status

***Possible status values:***

- subscribed
- unsubscribed
- pending
- bounced
- complained


## Update any contact data

```shell

```

>The above command JSON structured like this:

```json
{
  "message": "Subscriber successfully updated",
  "contact": {
    "id": "22",
    "user_id": null,
    "hash": "d76b4b3ba7daf871cc03a6037fbaa019",
    "contact_owner": null,
    "company_id": null,
    "prefix": "Mr",
    "first_name": "Andres",
    "last_name": "Alexser",
    "email": "alex@mail.com",
    "timezone": null,
    "address_line_1": "3 Union Street",
    "address_line_2": "1 Union Street",
    "postal_code": "SA1 3EE",
    "city": "Swansea",
    "state": "Swansea",
    "country": "GB",
    "ip": null,
    "latitude": null,
    "longitude": null,
    "total_points": "0",
    "life_time_value": "0",
    "phone": "44 098 6726 635",
    "status": "subscribed",
    "contact_type": "lead",
    "source": null,
    "avatar": null,
    "date_of_birth": "1995-07-14",
    "created_at": "2021-07-20 10:39:06",
    "last_activity": null,
    "updated_at": "2021-07-20 11:32:43",
    "photo": "https://www.gravatar.com/avatar/d76b4b3ba7daf871cc03a6037fbaa019?s=128",
    "full_name": "Andres Alexser"
  },
  "isDirty": true
}
```
This endpoint update a specific contact. Make sure you are passing the data in body as raw JSON format. Below there's an example added.<br>
```
{
  "subscriber":{
    "email": "alex@mail.com",
    "first_name": "Andres",
    "last_name": "Alexser"
  }
}
```


### HTTP Request

`PUT https://fcrm.test/wp-json/fluent-crm/v2/subscribers/<ID>`

### URL Parameters

Parameter | Type | Required| Description
--------- | ---- | ------- | -----------
prefix | string | no | Add Name Prefix of a Contact
first_name | string | no | Add Contact's First Name
last_name | string | no | Add Contact's Last Name
email | email | yes | Add Contact's Email
phone | string | no | Add Contact's Phone Number
date_of_birth | string | no | Add Contact's Date Of Birth ( Format: YYYY-MM-DD )
address_line_1 | string | no | Add Contact's Address Line 1
address_line_2 | string | no | Add Contact's Address Line 2
city | string | no | Add Contact's City
state | string | no | Add Contact's State
country | string | no | Add Contact's Country
postal_code | string | no | Add Contact's ZIP Code
photo | string | no | Add Contact's Profile Picture
attach_tags | array | no | Add Contact To One or Multiple Tags ( Tags data type is array & only takes the ID of a tag, e.g. **attach_tags[]=1&attach_tags[]=2** )
detach_tags | array | no | Remove One or Multiple Tags from Contact ( Tags data type is array & only takes the ID of a tag, e.g. **detach_tags[]=1&detach_tags[]=2** )
attach_lists | array | no | Add Contact To One or Multiple Lists ( List data type is array & only takes the ID of a list e.g. **attach_lists[]=1&attach_lists[]=2**)
detach_lists | array | no | Remove One or Multiple Lists from Contact ( List data type is array & only takes the ID of a list, e.g. **detach_lists[]=1&detach_lists[]=2** )
custom_values | array | no | Add Custom Value To a Contact ( Custom Field data type is array, To add data to custom field you have to define the key & value, key is custom field slug name, e.g. **custom_values[custom_field_slug]= Custom Field Value**)
status | string | yes | Add Contact's Status
company_id | int | no | Add company to Contact

***Possible status values:***

- subscribed
- unsubscribed
- pending
- bounced
- complained

## Create or Update contact

```shell

```

>The above command JSON structured like this:

```json
{
  "message": "Subscriber successfully updated",
  "contact": {
    "id": "22",
    "user_id": null,
    "hash": "d76b4b3ba7daf871cc03a6037fbaa019",
    "contact_owner": null,
    "company_id": null,
    "prefix": "Mr",
    "first_name": "Andres",
    "last_name": "Alexser",
    "email": "alex@mail.com",
    "timezone": null,
    "address_line_1": "3 Union Street",
    "address_line_2": "1 Union Street",
    "postal_code": "SA1 3EE",
    "city": "Swansea",
    "state": "Swansea",
    "country": "GB",
    "ip": null,
    "latitude": null,
    "longitude": null,
    "total_points": "0",
    "life_time_value": "0",
    "phone": "44 098 6726 635",
    "status": "subscribed",
    "contact_type": "lead",
    "source": null,
    "avatar": null,
    "date_of_birth": "1995-07-14",
    "created_at": "2021-07-20 10:39:06",
    "last_activity": null,
    "updated_at": "2021-07-20 11:32:43",
    "photo": "https://www.gravatar.com/avatar/d76b4b3ba7daf871cc03a6037fbaa019?s=128",
    "full_name": "Andres Alexser"
  },
  "isDirty": true
}
```
This endpoint update a specific contact. Make sure you are passing the data in body as raw JSON format. Below there's an example added.<br>
```
{
  "subscriber":{
    "email": "alex@mail.com",
    "first_name": "Andres",
    "last_name": "Alexser"
  }
}
```


### HTTP Request

`POST https://fcrm.test/wp-json/fluent-crm/v2/subscribers`

### URL Parameters

Parameter | Type | Required | Description
--------- | ---- |----------| -----------
__force_update | string | yes      | the value mush be "yes"
prefix | string | no       | Add Name Prefix of a Contact
first_name | string | no       | Add Contact's First Name
last_name | string | no       | Add Contact's Last Name
email | email | yes      | Add Contact's Email
phone | string | no       | Add Contact's Phone Number
date_of_birth | string | no       | Add Contact's Date Of Birth ( Format: YYYY-MM-DD )
address_line_1 | string | no       | Add Contact's Address Line 1
address_line_2 | string | no       | Add Contact's Address Line 2
city | string | no       | Add Contact's City
state | string | no       | Add Contact's State
country | string | no       | Add Contact's Country
postal_code | string | no       | Add Contact's ZIP Code
photo | string | no       | Add Contact's Profile Picture
tags | array | no       | Add Contact To One or Multiple Tags ( Tags data type is array & only takes the ID / slug / title of a tag, e.g. **[1,2,'title_or_slug']** )
detach_tags | array | no       | Remove One or Multiple Tags from Contact ( Tags data type is array & takes the ID / slug / title of a tag, e.g. **[1,2,'title_or_slug']** )
lists | array | no       | Add Contact To One or Multiple Lists ( List data type is array & only takes the ID / slug / title of a list e.g. **[1,2,'title_or_slug']**)
detach_lists | array | no       | Remove One or Multiple Lists from Contact ( List data type is array & takes the ID / slug / title of a list, e.g. **[1,2,'title_or_slug']** )
custom_values | array | no       | Add Custom Value To a Contact ( Custom Field data type is array, To add data to custom field you have to define the key & value, key is custom field slug name, e.g. **custom_values[custom_field_slug]= Custom Field Value**)
status | string | yes      | Add Contact's Status
company_id | int | no       | Add company to Contact

***Possible status values:***

- subscribed
- unsubscribed
- pending
- bounced
- complained


## Delete a Specific Contact

```shell

```

> The above command returns JSON structured like this:

```json
{
  "message": "Selected Subscribers has been deleted"
}
```

This endpoint deletes a specific contact.

### HTTP Request

`DELETE https://yourdomain.com/wp-json/fluent-crm/v2/subscribers/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
subscribers[] | The ID of the contact to delete
