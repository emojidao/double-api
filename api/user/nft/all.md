# /api/user/nft/all
Get the NFTs of the user,  all the NFTs are in open collection list.

## request param
- user_addr: The wallet address of the user.
- page_size: The max count of one page.
- page_number: The page number, the first page number is "1"
- collection_id: optional, if collection_id is set, only the NFTs in this collection will be returned.

request example: 
```json
{
  "user_addr": "0xA842BB15253eCF633A6C9ddB75a10f3f89b35e92",
  "page_size": 10,
  "page_number": 1,
  "collection_id":4
}
```
## response
- total_record_count : The total record count of NTFs for the request
- page_number: The current page number.
- nft_addr: The contract address of the NFT.
- nft_id: The tokenId of the NFT.
- nft_owner: The owner the the NFT.
- nft_renter: The renter of the NFT.
- nft_type:  Both 'common doNFT' and 'vNFT' are doNFT. The user with a doNFT has the right to use the original NFT for a specified period of time.
  - "0" : oNFT(Original NFT), used to distinguish doNFT, which is the ERC-721 standard NFT that the user already has.
  - "1" : Common doNFT, split from vNFT
  - "2" : vNFT, Lender stakes an NFT into a Double contract, and will receive an vNFT as a certificate to redeem the original NFT.
- start_timestamp: The start Time of doNFT, UNIX timestamp(second).
- end_timestamp: The end Time of doNFT, UNIX timestamp(second) .
- is_on_lent: 
  - "1": There will be a price.
  - "0": The price is empty.
- rent_max_end_time: The end time of the order, UNIX timestamp(second).
- rent_min_duration: The min periods(second) of the rental.
- payment_token: The address of the payment token. If payment_token == '0x0000000000000000000000000000000000000000', it means the native coin.

### response example

```json
{
    "code": "0",
    "msg": "success",
    "data": {
        "page_info": {
            "page_size": 10,
            "page_number": 1,
            "total_record_count": 2,
            "total_page_count": 1
        },
        "list": [
            {
                "id": "685",
                "nft_id": "121",
                "nft_addr": "0xa3bd16320d2048af9ab716d03295adeb2f3e51ab",
                "nft_owner": "0xdac88ff7422eb36910fbcf5c2ff941a94fc32813",
                "nft_renter": "",
                "name": "v-TrumpChick-2576",
                "chain_id": "4",
                "image": "https://imgtest.loserchick.fi/5-2576-l",
                "nft_type": "2",
                "start_timestamp": "1653219370",
                "end_timestamp": "18446744073709551615",
                "price": "1000000000000000000",
                "payment_token": "0x6c9b6fdb39ec1f4750e3b147ed240d203d8a69dd",
                "is_on_lent": "1",
                "rent_max_end_time": "1657112400",
                "rent_min_duration": "259200",
                "payment_token_info": {
                    "chain_id": "4",
                    "symbol": "CHICK",
                    "decimal": "18",
                    "address": "0x6c9b6fdb39ec1f4750e3b147ed240d203d8a69dd",
                    "price_usd": "0.1",
                    "colored_icon": "https://cdn.double.one/api/payment_token/CHICK_colored.png",
                    "white_icon": "https://cdn.double.one/api/payment_token/CHICK_white.png"
                },
                "chain_name_url": "rinkeby",
            },
            {
                "id": "611",
                "nft_id": "90",
                "nft_addr": "0xa3bd16320d2048af9ab716d03295adeb2f3e51ab",
                "nft_owner": "0xdac88ff7422eb36910fbcf5c2ff941a94fc32813",
                "nft_renter": "",
                "name": "v-TrumpChick-2570",
                "chain_id": "4",
                "image": "https://imgtest.loserchick.fi/5-2570-l",
                "nft_type": "1",
                "start_timestamp": "1653189993",
                "end_timestamp": "18446744073709551615",
                "price": "1000000000000000000",
                "payment_token": "0x6c9b6fdb39ec1f4750e3b147ed240d203d8a69dd",
                "is_on_lent": "1",
                "rent_max_end_time": "1656396000",
                "rent_min_duration": "259200",
                "payment_token_info": {
                    "chain_id": "4",
                    "symbol": "CHICK",
                    "decimal": "18",
                    "address": "0x6c9b6fdb39ec1f4750e3b147ed240d203d8a69dd",
                    "price_usd": "0.1",
                    "colored_icon": "https://cdn.double.one/api/payment_token/CHICK_colored.png",
                    "white_icon": "https://cdn.double.one/api/payment_token/CHICK_white.png"
                },
                "chain_name_url": "rinkeby",
            },
        ]
      ,
    }
}
```
