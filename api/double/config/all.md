# /api/double/config/all
Get basic config.

## request param
None 

## response
- middleware : The middleware contract address, middleware is used for query some data from one or some contract in one request.
- market: The market contract address. 

### response example

```json
{
    "code": "0",
    "msg": "success",
    "data": {
        "front": {
            "api_version": "1.2.1.1",
            "network": [
                {
                    "chain_id": 97,
                    "name_display": "BscTest",
                    "currency_symbol": "BNB",
                    "rpc": "",
                    "block_explorer": "https://testnet.bscscan.com",
                    "middleware": "0x1e5AFD24E50d4cc25a615B6872fa85C59c8A536C",
                    "market": "0xAE1ABbB6550431Ad1dE32621509E3e71287F8aac"
                },
                {
                    "chain_id": 4,
                    "name_display": "Rinkeby",
                    "currency_symbol": "ETH",
                    "rpc": "",
                    "block_explorer": "https://rinkeby.etherscan.io",
                    "middleware": "0x89E4B454C6b223B56697f4Cd09A642429c435F86",
                    "market": "0x078AB7E728832E162648b64976D83C3bD23615cd"
                }
            ],
        },

        "payment_token": [
            {
                "chain_id": "4",
                "symbol": "ETH",
                "decimal": "18",
                "address": "0x0000000000000000000000000000000000000000",
                "price_usd": "2445.83",
                "colored_icon": "https://cdn.double.one/api/payment_token/ETH_colored.png",
                "white_icon": "https://cdn.double.one/api/payment_token/ETH_white.png"
            },
            {
                "chain_id": "97",
                "symbol": "BNB",
                "decimal": "18",
                "address": "0x0000000000000000000000000000000000000000",
                "price_usd": "341.7",
                "colored_icon": "https://cdn.double.one/api/payment_token/BNB_colored.png",
                "white_icon": "https://cdn.double.one/api/payment_token/BNB_white.png"
            },
            {
                "chain_id": "97",
                "symbol": "RENA",
                "decimal": "18",
                "address": "0x8e5d8b8a9dfe99e60b23f9e1bd86ed2e26cbf360",
                "price_usd": "0.095669",
                "colored_icon": "https://cdn.double.one/api/payment_token/RENA_colored.png",
                "white_icon": "https://cdn.double.one/api/payment_token/RENA_white.png"
            },
            {
                "chain_id": "4",
                "symbol": "CHICK",
                "decimal": "18",
                "address": "0x6c9b6fdb39ec1f4750e3b147ed240d203d8a69dd",
                "price_usd": "0.1",
                "colored_icon": "https://cdn.double.one/api/payment_token/CHICK_colored.png",
                "white_icon": "https://cdn.double.one/api/payment_token/CHICK_white.png"
            },
            {
                "chain_id": "4",
                "symbol": "BUSD",
                "decimal": "6",
                "address": "0x6b19dd4170f62dff69cab077e229b294ef8156f6",
                "price_usd": "1",
                "colored_icon": "https://cdn.double.one/api/payment_token/BUSD_colored.png",
                "white_icon": "https://cdn.double.one/api/payment_token/BUSD_white.png"
            }
        ]
    }
}
```
