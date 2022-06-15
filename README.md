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
- [/api/double/market/open_collection_list](./api/double/market/open_collection_list.md) : Get the open collection list.
- [/api/user/nft/all](./api/user/nft/all.md) : Get the NFTs of the user.
- [/api/double/market/collection](./api/double/market/collection.md) : Get the listing NFTs by collection.
- [/api/double/market/detail](./api/double/market/detail.md) :Get the detail information of the NFT.

## Error Code
- 0: No error
- 10404 : not exists
- 10405 : invalid param
