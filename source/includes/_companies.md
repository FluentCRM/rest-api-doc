
# Companies

## Get All Companies

```shell
curl "https://yourdomain.com/wp-json/fluent-crm/v2/companies" \
  -H "Authorization: BASIC API_USERNAME:API_PASSWORD"
```
> The above command returns JSON structured like this:

```json
{
    "companies": {
        "total": 2,
        "per_page": 15,
        "current_page": 1,
        "last_page": 1,
        "next_page_url": null,
        "prev_page_url": null,
        "from": 1,
        "to": 2,
        "data": [
            {
                "id": 2,
                "hash": "18740e0997e2a0f6b04756da5a9d7b44",
                "owner_id": "1913",
                "name": "Demo Company",
                "industry": "Alternative Dispute Resolution",
                "website": "https://www.php.net/manual",
                "email": "demo@gmail.com",
                "timezone": "",
                "address_line_1": "",
                "address_line_2": "",
                "postal_code": "",
                "city": "",
                "state": "",
                "country": "BD",
                "employees_number": "0",
                "description": "This is a demo company",
                "phone": "",
                "type": "active",
                "logo": "http://wp.test/wp-content/uploads/2022/11/1280px-Taka_Bengali_letter.svg_.png",
                "linkedin_url": "",
                "status": "active",
                "created_at": "2023-03-13 18:34:34",
                "updated_at": "2023-03-16 15:02:33",
                "contacts_count": 0,
                "owner": {
                    "id": 1913,
                    "user_id": "1",
                    "hash": "eedc61a75aec6315291f11c96cfc036a",
                    "contact_owner": null,
                    "company_id": null,
                    "prefix": "Mr",
                    "first_name": "Nihar",
                    "last_name": "Das",
                  ...
                }
            },
            ...
        ]
    }
}
```

This endpoint retrieves all Company.

### HTTP Request

`GET https://yourdomain.com/wp-json/fluent-crm/v2/companies`

### URL Parameters

Parameter | Type | Description                                                               | Default
--------- | ------- |---------------------------------------------------------------------------| -------
| per_page |  int | Records per page                                                          | 10 |
| page |    int   | Page Number for Pagination                                                | 1 |
| search | string | Search by 'name', 'phone', 'description', 'email' for filtering companies | |
| sort_by | string | Sort By company column Value to sort companies                            | id |
| sort_order | string | Sort Type company column Value to sort companies                          | DESC |

***Possible searchable columns:***

- name
- phone
- description
- email


## Search company

```shell

curl 'https://fcrm.test/wp-json/fluent-crm/v2/companies/search' \
  -H "Authorization: BASIC API_USERNAME:API_PASSWORD" \
  --data-raw 'search=demo' \
	 
	 
```

> The above command returns JSON structured like this:

```json
{
  "results": [
    {
      "id": 2,
      "name": "Demo Company",
      "email": "demo@gmail.com",
      "logo": "http://wp.test/wp-content/uploads/2022/11/1280px-Taka_Bengali_letter.svg_.png",
      "phone": "",
      "website": "https://www.php.net/manual"
    },
    {
      "id": 1,
      "name": "Hello",
      "email": "demo@d.com",
      "logo": "http://wp.test/wp-content/uploads/2022/03/pin.png",
      "phone": "",
      "website": ""
    }
  ],
  "has_more": false
}
```

This endpoint search company by 'name', 'phone', 'description', 'email'

### HTTP Request

`DELETE https://yourdomain.com/wp-json/fluent-crm/v2/contacts/search`

### URL Parameters

Parameter | Description
--------- | -----------
subscriber_id | The ID of the contact to search company
search | search 'name', 'phone', 'description', 'email' Parameter for filtering companies

***Possible searchable columns:***

- name
- phone
- description
- email


## Get a Specific Company


```shell
curl "https://yourdomain.com/wp-json/fluent-crm/v2/companies/<ID>" \
  -H "Authorization: BASIC API_USERNAME:API_PASSWORD"
```

> The above command returns JSON structured like this:

```json
{
    "company": {
        "id": 2,
        "hash": "18740e0997e2a0f6b04756da5a9d7b44",
        "owner_id": "1913",
        "name": "Demo Company",
        "industry": "Alternative Dispute Resolution",
        "website": "https://www.php.net/manual",
        "email": "demo@gmail.com",
        "timezone": "",
        "address_line_1": "",
        "address_line_2": "",
        "postal_code": "",
        "city": "",
        "state": "",
        "country": "BD",
        "employees_number": "0",
        "description": "This is a demo company",
        "phone": "",
        "type": "active",
        "logo": "http://wp.test/wp-content/uploads/2022/11/1280px-Taka_Bengali_letter.svg_.png",
        "linkedin_url": "",
        "status": "active",
        "created_at": "2023-03-13 18:34:34",
        "updated_at": "2023-03-16 15:02:33",
        "contacts_count": 0,
        "owner": {
            "id": 1913,
            "user_id": "1",
            "hash": "eedc61a75aec6315291f11c96cfc036a",
            "contact_owner": null,
            "company_id": null,
            "prefix": "Mr",
            "first_name": "Demo",
            "last_name": "Owner",
            "email": "demo@gmail.com",
            "timezone": null,
            "address_line_1": "Rahim Tower, Subhanighat Bishwa Road",
            "address_line_2": "Sylhet",
            "postal_code": "3100",
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
            "date_of_birth": "1994-10-13",
            "created_at": "2022-09-12 06:18:49",
            "last_activity": "2023-03-29 11:39:14",
            "updated_at": "2023-03-29 11:39:14",
            "stats": {
                "emails": 14,
                "opens": 1,
                "clicks": 1
            },
            "full_name": "Demo Owner",
            "photo": "https://www.gravatar.com/avatar/eedc61a75aec6315291f11c96cfc036a?s=128&d=https%3A%2F%2Fui-avatars.com%2Fapi%2FNihar%2BDas/128"
        }
    }
}
```

This endpoint retrieves a specific company.

### HTTP Request

Get company by id:  
`GET https://yourdomain.com/wp-json/fluent-crm/v2/companies/<ID>`

Or get by 'name', 'email', 'phone':  
`GET https://yourdomain.com/wp-json/fluent-crm/v2/companies/0?find_by=email&find_by_value=demo@gmail.com`


## Create a new company

```shell

curl 'https://fcrm.test/wp-json/fluent-crm/v2/companies' \
  -H "Authorization: BASIC API_USERNAME:API_PASSWORD" \
  --data-raw 'name=Bluesky&description=This is bluesky company&email=bluesky%26authlab.io&phone=44+078+1961+0398&owner_id=14&employees_number=120&industry=IT-farm&type=Running&address_line_1=1+Union+Street&address_line_2=64+Cunnery+Rd&city=Swansea&state=Swansea&postal_code=SA1+3EE&country=GB&query_timestamp=1626770805540' \
	 
```
> The above command creates a new company in Fluent CRM and returns the data in JSON.

```json
{
    "message": "Company has been created successfully",
    "company": {
        "name": "Bluesky",
        "description": "This is bluesky company",
        "phone": "44 078 1961 0398",
        "email": "",
        "owner_id": "14",
        "employees_number": true,
        "industry": "IT-farm",
        "type": "Running",
        "address_line_1": "1 Union Street",
        "address_line_2": "64 Cunnery Rd",
        "postal_code": "SA1 3EE",
        "city": "Swansea",
        "state": "Swansea",
        "country": "GB",
        "hash": "dc9d1ea355621a1dfcb2b9c58771dfa4",
        "updated_at": "2023-03-30 11:12:57",
        "created_at": "2023-03-30 11:12:57",
        "id": 3
    }
}
```

This endpoint creates a new company.

### HTTP Request

`POST https://yourdomain.com/wp-json/fluent-crm/v2/companies`

### URL Parameters

Parameter | Type    | Required | Description
--------- |---------|----------| -----------
name | string  | yes      | Add Company's Name
description | string  | no       | Add Company's Description
email | email   | no       | Add Company's Email
phone | string  | no       | Add Company's Phone Number
address_line_1 | string  | no       | Add Company's Address Line 1
address_line_2 | string  | no       | Add Company's Address Line 2
city | string  | no       | Add Company's City
state | string  | no       | Add Company's State
country | string  | no       | Add Company's Country
postal_code | string  | no       | Add Company's ZIP Code
type | string  | no       | Add Company's Type
owner_id | string  | no       | Add Company's Owner
employees_number | integer | no       | Add Company's employee number
industry | string  | no       | Add Company's industry category

***Possible type values:***

- Prospect
- Partner
- Reseller
- Vendor
- Other


## Update any company data

```shell
curl 'https://fcrm.test/wp-json/fluent-crm/v2/companies/<ID>' \
  -H "Authorization: BASIC API_USERNAME:API_PASSWORD" \
  --data-raw 'name=BlueSky&description=This is bluesky company&email=bluesky%26authlab.io&phone=44+078+1961+0398&owner_id=14&employees_number=110&industry=IT-farm&type=Running&address_line_1=1+Union+Street&address_line_2=64+Cunnery+Rd' \
	 
```

>The above command JSON structured like this:

```json
{
    "message": "Company has been updated",
    "company": {
        "id": 3,
        "hash": "dc9d1ea355621a1dfcb2b9c58771dfa4",
        "owner_id": "14",
        "name": "BlueSky",
        "industry": "IT-farm",
        "website": null,
        "email": "",
        "timezone": null,
        "address_line_1": "1 Union Street",
        "address_line_2": "64 Cunnery Rd",
        "postal_code": "SA1 3EE",
        "city": "Swansea",
        "state": "Swansea",
        "country": "GB",
        "employees_number": true,
        "description": "This is bluesky company",
        "phone": "44 078 1961 0398",
        "type": "Running",
        "logo": null,
        "linkedin_url": null,
        "status": null,
        "created_at": "2023-03-30 11:12:57",
        "updated_at": "2023-03-30 11:56:05"
    }
}
```

This endpoint update any company.

### HTTP Request

`POST https://yourdomain.com/wp-json/fluent-crm/v2/companies/<ID>`

### URL Parameters

Parameter | Type    | Required | Description
--------- |---------|----------| -----------
name | string  | yes      | Add Company's Name
description | string  | no       | Add Company's Description
email | email   | no       | Add Company's Email
phone | string  | no       | Add Company's Phone Number
address_line_1 | string  | no       | Add Company's Address Line 1
address_line_2 | string  | no       | Add Company's Address Line 2
city | string  | no       | Add Company's City
state | string  | no       | Add Company's State
country | string  | no       | Add Company's Country
postal_code | string  | no       | Add Company's ZIP Code
type | string  | no       | Add Company's Type
owner_id | string  | no       | Add Company's Owner
employees_number | integer | no       | Add Company's employee number
industry | string  | no       | Add Company's industry category

***Possible type values:***

- Prospect
- Partner
- Reseller
- Vendor
- Other


## Update company's properties

```shell

curl 'https://fcrm.test/wp-json/fluent-crm/v2/companies/companies-property' \
  -H "Authorization: BASIC API_USERNAME:API_PASSWORD" \
  --data-raw 'property=type&value=Partner&companies[]=1&companies[]=2' \
	 
	 
```

> The above command returns JSON structured like this:

```json

{
    "message": "Company successfully updated"
}
```

This endpoint update company properties.

### HTTP Request

`PUT https://yourdomain.com/wp-json/fluent-crm/v2/companies/companies-property`

### URL Parameters

Parameter | Type   | Required | Description
--------- |--------|----------| -----------
property | string | yes      | Updateable properties are 'type', 'logo' or 'owner_id'
value | string | yes       | Value of 'type', 'logo' or 'owner_id'
companies | array  | yes       | Update will apply to provided company ids

***Possible type values:***

- Prospect
- Partner
- Reseller
- Vendor
- Other


## Attach subscribers to company

```shell

curl 'https://fcrm.test/wp-json/fluent-crm/v2/companies/attach-subscribers' \
  -H "Authorization: BASIC API_USERNAME:API_PASSWORD" \
  --data-raw 'subscriber_ids[]=1980&subscriber_ids[]=1979&company_ids[]=1&company_ids[]=2' \
	 
	 
```

> The above command returns JSON structured like this:

```json
{
  "message": "Selected Companies has been attached successfully",
  "companies": [
    {
      "id": 1,
      "hash": "a9ba241222b3ba9f7158e006ffc28aa7",
      "owner_id": "1968",
      "name": "Hello",
      "industry": "Apparel & Fashion",
      "website": "",
      "email": "demo@d.com",
      "timezone": "",
      "address_line_1": "Tahirpur",
      "address_line_2": "Sylhet",
      "postal_code": "",
      "city": "",
      "state": "",
      "country": "",
      "employees_number": "0",
      "description": "Hello",
      "phone": "",
      "type": "Partner",
      "logo": "http://wp.test/wp-content/uploads/2022/03/pin.png",
      "linkedin_url": "",
      "status": "active",
      "created_at": "2023-03-13 15:05:45",
      "updated_at": "2023-03-30 14:55:33"
    },
    {
      "id": 2,
      "hash": "18740e0997e2a0f6b04756da5a9d7b44",
      "owner_id": "1913",
      "name": "Demo Company",
      "industry": "Alternative Dispute Resolution",
      "website": "https://www.php.net/manual",
      "email": "demo@gmail.com",
      "timezone": "",
      "address_line_1": "",
      "address_line_2": "",
      "postal_code": "",
      "city": "",
      "state": "",
      "country": "BD",
      "employees_number": "0",
      "description": "This is a demo company",
      "phone": "",
      "type": "Partner",
      "logo": "http://wp.test/wp-content/uploads/2022/11/1280px-Taka_Bengali_letter.svg_.png",
      "linkedin_url": "",
      "status": "active",
      "created_at": "2023-03-13 18:34:34",
      "updated_at": "2023-03-30 14:55:33"
    }
  ]
}
```

This endpoint update company properties.

### HTTP Request

`PUT https://yourdomain.com/wp-json/fluent-crm/v2/companies/attach-subscribers`

### URL Parameters

Parameter | Type   | Required | Description
--------- |--------|----------| -----------
subscriber_ids | array | yes      | Subscriber ids will be attached with company
company_ids | array  | yes       | Company ids where subscribers will be attached 


## Detach subscribers to company

```shell

curl 'https://fcrm.test/wp-json/fluent-crm/v2/companies/detach-subscribers' \
  -H "Authorization: BASIC API_USERNAME:API_PASSWORD" \
  --data-raw 'subscriber_ids[]=1980&subscriber_ids[]=1979&company_ids[]=1&company_ids[]=2' \
	 
	 
```

> The above command returns JSON structured like this:

```json
{
  "message": "Company has been successfully detached",
  "companies": [],
  "last_primary_company_id": false
}
```

This endpoint update company properties.

### HTTP Request

`PUT https://yourdomain.com/wp-json/fluent-crm/v2/companies/detach-subscribers`

### URL Parameters

Parameter | Type   | Required | Description
--------- |--------|----------| -----------
subscriber_ids | array | yes      | Subscriber ids will be detached with company
company_ids | array  | yes       | Company ids where subscribers will be detached


## Delete a Specific Company

```shell
curl 'https://fcrm.test/wp-json/fluent-crm/v2/companies/3' \
  -H "Authorization: BASIC API_USERNAME:API_PASSWORD" \
  
```

> The above command returns JSON structured like this:

```json
{
  "message": "Company has been deleted successfully"
}
```

This endpoint deletes a specific company.

### HTTP Request

`DELETE https://yourdomain.com/wp-json/fluent-crm/v2/companies/<ID>`


