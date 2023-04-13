
# Custom Fields

## Get All Custom Fields

```shell
curl --location --request GET 'https://yourdomain.com/wp-json/fluent-crm/v2/custom-fields/contacts' \
--header 'Authorization: Basic API_USERNAME:API_PASSWORD'
```

> The above command returns JSON structured like this:

```json
{
  "fields": [
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
    },
    {
      "field_key": "radio",
      "type": "radio",
      "label": "Is Valid",
      "options": [
        "Yes",
        "No"
      ],
      "slug": "is_valid"
    },
    {
      "field_key": "radio",
      "type": "radio",
      "label": "Choose",
      "options": [
        "Y",
        "X"
      ],
      "slug": "choose"
    },
    {
      "field_key": "radio",
      "type": "radio",
      "label": "Choose Country",
      "options": [
        "Bangladesh",
        "India",
        "USA"
      ],
      "slug": "choose_country"
    },
    {
      "field_key": "single-select",
      "type": "select-one",
      "label": "Select Country",
      "options": [
        "Bangladesh",
        "India",
        "Japan"
      ],
      "slug": "select_country"
    },
    {
      "field_key": "radio",
      "type": "radio",
      "label": "Radio Boxes",
      "options": [
        "AuthLab",
        "WPManageNinja",
        "Kamran Raja",
        "Option 4"
      ],
      "slug": "checking_box"
    },
    {
      "field_key": "checkbox",
      "type": "checkbox",
      "label": "Checkbox Field",
      "options": [
        "AuthLab",
        "WPManageNinja",
        "Kamran Raja",
        "Option 4"
      ],
      "slug": "checkbox_field"
    }
  ]
}
```

This endpoint returns all custom fields

### HTTP Request
`GET https://yourdomain.com/wp-json/fluent-crm/v2/custom-fields/contacts`

### URL Parameters

Parameter | Type  | Description           
--------- |-------|-----------------------
with | array | Get other additional data


***Possible with parameters:***

- field_types
