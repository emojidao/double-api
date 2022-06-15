# /api/double/market/detail
Get the detail information of the NFT.

## request param
- nft_addr: The contract address of the NFT.
- nft_id: The tokenId of the NFT.
- chain_id:  The chain id of EVM compatible blockchain.

request example: 
```json
{
    "nft_addr":"0x80d6deebe29ccc484abd19b150681d55af83021a",
    "nft_id": "6",
    "chain_id": 97
}
```
## response
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
- rent_max_end_time: The end time of the order, UNIX timestamp(second).
- rent_min_duration: The min periods(second) of the rental.
- payment_token: The address of the payment token. If payment_token == '0x0000000000000000000000000000000000000000', it means the native coin.
- price_usd: The price of the NFT by USD.
- stats: The properties of the NFT.
- activity: The onchain event of the NFT.
- onft_id: The original NFT id, If the nft_type == '1' or nft_type == '2', the `onft_id` will not be empty. That means the doNFT is minted from the specific(onft_id) original NFT.
- details: The basic info of a NFT. If the NFT is doNFT, there will be a original NFT information.

### response example

```json
{
    "code": "0",
    "msg": "success",
    "data": {
        "chain_id": "4",
        "nft_addr": "0xb146d1e18c8272f2a248d20f30c96bc77fba9283",
        "nft_id": "1",
        "nft_owner": "0x35f4b5edf7043429991220978b20d71d82a4a7e1",
        "nft_user": "",
        "user_expires": "",
        "name": "Parcels 116,125",
        "image": "https://api.decentraland.org/v2/parcels/116/125/map.png?size=24&width=1024&height=1024",
        "start_timestamp": "1652272748",
        "end_timestamp": "18446744073709551615",
        "is_on_lent": "1",
        "price": "100000000000000",
        "price_usd": "0.226371",
        "payment_token": "0x0000000000000000000000000000000000000000",
        "rent_min_duration": "86400",
        "rent_max_end_time": "1667826000",
        "nft_type": "1",
        "onft_id": "39472754562828861761751454462085112529021",
        "payment_token_info": {
            "chain_id": "4",
            "symbol": "ETH",
            "decimal": "18",
            "address": "0x0000000000000000000000000000000000000000",
            "price_usd": "2263.71",
            "colored_icon": "https://cdn.double.one/api/payment_token/ETH_colored.png",
            "white_icon": "https://cdn.double.one/api/payment_token/ETH_white.png"
        },
        "pair_contract": {
            "addr": "0x6ba0ac64d4afdbab1857a17abcdc0424b73be7bc"
        },

        "collection": {
            "name_url": "decentraland",
            "name_display": "Decentraland",
            "verified": "1",
            "image_logo": "https://cdn.double.one/api/collection/dcl.png",
            "image_cover": "https://cdn.double.one/api/collection/dcl_cover.png",
            "web_site": "https://decentraland.org/",
            "app_site": "https://builder.decentraland.org/",
            "twitter": "https://twitter.com/decentraland",
            "discord": "https://decentraland.org/discord/",
            "discription": "Rent or lend the land in Decentraland on Double Protocol."
        },
        "collection_ext": {
            "min_rental_days": "1",
            "max_rental_days": "180",
            "is_filtered_by_min_rental_days": "0",
            "renter_tips": [],
            "lender_tips": [],
            "payment_token": [
                {
                    "chain_id": "4",
                    "symbol": "ETH",
                    "address": "0x0000000000000000000000000000000000000000",
                    "decimal": "18",
                    "price_usd": "2263.71",
                    "white_icon": "https://cdn.double.one/api/payment_token/ETH_white.png",
                    "colored_icon": "https://cdn.double.one/api/payment_token/ETH_colored.png",
                    "min_price": "0"
                }
            ]
        },
        "chain_name_url": "rinkeby",
        "stats": [
            {
                "display_name": "X",
                "value": 116
            },
            {
                "display_name": "Y",
                "value": 125
            },
            {
                "display_name": "Distance to District",
                "value": 1
            },
            {
                "display_name": "Distance to Road",
                "value": 2
            },
            {
                "display_name": "Distance to Plaza",
                "value": 3
            }
        ],
        "details": [
            {
                "type": "url",
                "display_name": "doNFT Contract Address",
                "value": "0xb146d1e18c8272f2a248d20f30c96bc77fba9283",
                "url": "https://rinkeby.etherscan.io/address/0xb146d1e18c8272f2a248d20f30c96bc77fba9283"
            },
            {
                "type": "url",
                "display_name": "doNFT Token ID",
                "value": "1",
                "url": "https://rinkeby.etherscan.io/token/0xb146d1e18c8272f2a248d20f30c96bc77fba9283?a=1"
            },
            {
                "type": "url",
                "display_name": "Original Contract Address",
                "value": "0x6ba0ac64d4afdbab1857a17abcdc0424b73be7bc",
                "url": "https://rinkeby.etherscan.io/address/0x6ba0ac64d4afdbab1857a17abcdc0424b73be7bc"
            },
            {
                "type": "url",
                "display_name": "Original Token ID",
                "value": "39472754562828861761751454462085112529021",
                "url": "https://rinkeby.etherscan.io/token/0x6ba0ac64d4afdbab1857a17abcdc0424b73be7bc?a=39472754562828861761751454462085112529021"
            },
            {
                "type": "text",
                "display_name": "Token Standard",
                "value": "ERC-721"
            },
            {
                "type": "text",
                "display_name": "Blockchain",
                "value": "Rinkeby"
            }
        ],
        "activity": [
            {
                "nft_addr": "0xb146d1e18c8272f2a248d20f30c96bc77fba9283",
                "nft_id": "1",
                "event_type": "Minted",
                "block_time": "1652272748",
                "from_addr": "0x0000000000000000000000000000000000000000",
                "to_addr": "0x35f4b5edf7043429991220978b20d71d82a4a7e1",
                "chain_id": "4",
                "from": "0x0000000000000000000000000000000000000000",
                "to": "0x35f4b5edf7043429991220978b20d71d82a4a7e1",
                "url": "https://rinkeby.etherscan.io/tx/0x6444d7dbf2bebd5c315fdb590ae89e20caab2cb8c80f7a49d8f290a446f351db"
            },
            {
                "nft_addr": "0xb146d1e18c8272f2a248d20f30c96bc77fba9283",
                "nft_id": "1",
                "event_type": "List",
                "block_time": "1652272748",
                "from_addr": "0x35f4b5edf7043429991220978b20d71d82a4a7e1",
                "to_addr": "",
                "chain_id": "4",
                "from": "0x35f4b5edf7043429991220978b20d71d82a4a7e1",
                "to": "",
                "url": "https://rinkeby.etherscan.io/tx/0x6444d7dbf2bebd5c315fdb590ae89e20caab2cb8c80f7a49d8f290a446f351db",
                "price": "100000000000000",
                "payment_token_info": {
                    "chain_id": "4",
                    "symbol": "ETH",
                    "decimal": "18",
                    "address": "0x0000000000000000000000000000000000000000",
                    "price_usd": "2263.71",
                    "colored_icon": "https://cdn.double.one/api/payment_token/ETH_colored.png",
                    "white_icon": "https://cdn.double.one/api/payment_token/ETH_white.png"
                }
            }
        ],
    }
}
```
