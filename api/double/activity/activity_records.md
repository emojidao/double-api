# /api/double/activity/activity_records
Get the NFTs activities.

## request param
- page_size: The max count of one page. The max value is 100
- page_number: The page number, the first page number is "1"
- flag: 
 - account:  Activities of one user
 - collection :  Activities of one collection
 - nft : Activities of one nft
- collection_id:  The id of the collection.
- nft_owner: It is required when flag == 'account'
- event_type: Array, such as [], ["rent","list"]
 - rent
 - rent_out: Only valid if flag ==  "account", filter the activities that others rent from the nft_owner
 - list
 - delist
  

request example: 
```json
{"page_size":20,"page_number":1,"nft_owner":"0x35f4b5edf7043429991220978b20d71d82a4a7e1","collection_id":"318","chain_id":"","flag":"account","event_type":["rent_out"]}
```
## response
- page_info.total_record_count : The total record count of NTFs for the request
- page_info.page_number: The current page number.
- nft_addr: The contract address of the NFT.
- nft_id: The tokenId of the NFT.
- nft_renter: The renter of the NFT.
- from_addr: The lender address
- to_addr: When event_type == 'Rent', to_addr is the renter
- rent_duration: When event_type == 'Rent', `rent_duration` is the rental time, unit: seconds
- total_price: When event_type == 'Rent', `total_price` is the rental fee paid by the renter,  display total price = total_price / pow(10,payment_token_info.decimal)

### response example

```json
{
	"code": "0",
	"msg": "success",
	"data": {
		"page_info": {
			"page_size": 20,
			"page_number": 1,
			"total_record_count": 3,
			"total_page_count": 1
		},
		"list": [
			{
				"chain_id": "97",
				"nft_addr": "0xcba8d2b21d4eb99bfe86b5175a26505952a6f1eb",
				"nft_id": "50",
				"nft_count": "1",
				"collection_info_id": "393",
				"onft_type": "0",
				"onft_addr": "0x343312fd29e5b0c1b6059a9870e630b7281a5554",
				"onft_id": "2",
				"onft_md5": "b5d91fd0e39a2af9fdb76062fc3f421c",
				"event_type": "Rent",
				"block_time": "1670992673",
				"hash": "0x5ba02f2ad71e9cc1a91c14afff3a5bf7bb20a13b95cee8ddd469604c750d4193",
				"from_addr": "0x97dc7e8091af6ac6ff37f4bd9ea89a537a34775d",
				"to_addr": "0x35f4b5edf7043429991220978b20d71d82a4a7e1",
				"rent_duration": 259200,
				"total_price": "3000000000000000",
				"payment_token_info": {
					"chain_id": "97",
					"symbol": "BNB",
					"decimal": "18",
					"address": "0x0000000000000000000000000000000000000000",
					"price_usd": "300.4",
					"icon": "https://static.double.one/double/prod/homepage/payment-token/BNB.png"
				},
				"amount": "1",
				"collection_info": {
					"id": "393",
					"name_display": "bsctest_721",
					"name_url": "bsctest_721",
					"cycle_type": "2"
				},
				"name": "BOSSChick-2",
				"image": "https://cdn.doubleimg.com/97/0x343312fd29e5b0c1b6059a9870e630b7281a5554/2/0/aHR0cHM6Ly9pbWdtYXRpYy5sb3NlcmNoaWNrLmZpLzQtMi1s.png"
			},
			{
				"chain_id": "97",
				"nft_addr": "0xcba8d2b21d4eb99bfe86b5175a26505952a6f1eb",
				"nft_id": "62",
				"nft_count": "1",
				"collection_info_id": "393",
				"onft_type": "0",
				"onft_addr": "0x343312fd29e5b0c1b6059a9870e630b7281a5554",
				"onft_id": "13",
				"onft_md5": "0626ddd35e81b04dd71232b0827e48eb",
				"event_type": "Rent",
				"block_time": "1670986634",
				"hash": "0xe6c4e0031b6b5055cae75b24d5fda8264c55a1f69a441740c9294225d6b89bef",
				"from_addr": "0xff663934e17b1e1e5e91ee6140b8836e3436f140",
				"to_addr": "0x35f4b5edf7043429991220978b20d71d82a4a7e1",
				"rent_duration": 172800,
				"total_price": "200000000000000",
				"payment_token_info": {
					"chain_id": "97",
					"symbol": "BNB",
					"decimal": "18",
					"address": "0x0000000000000000000000000000000000000000",
					"price_usd": "300.4",
					"icon": "https://static.double.one/double/prod/homepage/payment-token/BNB.png"
				},
				"amount": "1",
				"collection_info": {
					"id": "393",
					"name_display": "bsctest_721",
					"name_url": "bsctest_721",
					"cycle_type": "2"
				},
				"name": "BOSSChick-13",
				"image": "https://cdn.doubleimg.com/97/0x343312fd29e5b0c1b6059a9870e630b7281a5554/13/0/aHR0cHM6Ly9pbWdtYXRpYy5sb3NlcmNoaWNrLmZpLzQtMTMtbA.png"
			},
			{
				"chain_id": "97",
				"nft_addr": "0xcba8d2b21d4eb99bfe86b5175a26505952a6f1eb",
				"nft_id": "54",
				"nft_count": "1",
				"collection_info_id": "393",
				"onft_type": "0",
				"onft_addr": "0x343312fd29e5b0c1b6059a9870e630b7281a5554",
				"onft_id": "7",
				"onft_md5": "6eb57ab03428e019469a7db8d9adc082",
				"event_type": "Rent",
				"block_time": "1670986142",
				"hash": "0x600293b1789ae2cd2174917029cc72d5610d866b00d7a49f682fe750a7f0ed96",
				"from_addr": "0x97dc7e8091af6ac6ff37f4bd9ea89a537a34775d",
				"to_addr": "0x35f4b5edf7043429991220978b20d71d82a4a7e1",
				"rent_duration": 172800,
				"total_price": "200000000000000",
				"payment_token_info": {
					"chain_id": "97",
					"symbol": "BNB",
					"decimal": "18",
					"address": "0x0000000000000000000000000000000000000000",
					"price_usd": "300.4",
					"icon": "https://static.double.one/double/prod/homepage/payment-token/BNB.png"
				},
				"amount": "1",
				"collection_info": {
					"id": "393",
					"name_display": "bsctest_721",
					"name_url": "bsctest_721",
					"cycle_type": "2"
				},
				"name": "BOSSChick-7",
				"image": "https://cdn.doubleimg.com/97/0x343312fd29e5b0c1b6059a9870e630b7281a5554/7/0/aHR0cHM6Ly9pbWdtYXRpYy5sb3NlcmNoaWNrLmZpLzQtNy1s.png"
			}
		]
	}
}

```