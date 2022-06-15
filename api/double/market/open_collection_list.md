# /api/double/market/open_collection_list
Get the open collection list.

## request param
None 

## response
- verified : 
  - "0" : not verified
  - "1" : verified 

### response example

```json
{
    "code": "0",
    "msg": "success",
    "data": [
        {
            "id": "10",
            "name_url": "decentraland",
            "name_display": "Decentraland",
            "image_logo": "https://cdn.double.one/api/collection/dcl.png",
            "verified": "1"
        },
        {
            "id": "9",
            "name_url": "warena",
            "name_display": "Warena",
            "image_logo": "https://cdn.double.one/api/collection/warena_logo_3.png",
            "verified": "1"
        },
        {
            "id": "8",
            "name_url": "loserchick",
            "name_display": "LoserChick",
            "image_logo": "https://cdn.double.one/api/collection/loserchick_logo.png",
            "verified": "1"
        },
    ]
}
```
