# Double API
Double API is in beta.

## Host 
- Product env host: https://double.one
- Test env host: https://test.double.one

## Request and Response 
### Request 
- method: HTTP POST
- Content-Type: application/json

### Response 
- Content-Type: application/json


## API
- [/api/double/config/all](./api/double/config/all.md) : Get basic config.
- [/api/user/nft_owner/all](./api/user/nft_owner/all.md) : Get the NFTs of the user.
- [/api/double/collection/single_collection](./api/double/collection/single_collection.md) : Get the listing NFTs by collection.
- [/api/double/activity/activity_records](./api/double/activity/activity_records.md) : Get the NFTs activities.

## Error Code
- 0: No error
- 10404 : not exists
- 10405 : invalid param
