## Guide for Ume Shopping Api Version 1.0

### Api Portal 

> https://api.eportalmobile.com/v1/amazon/product

------

### Product List

**Method:**

> GET / POST

 **Required:**

```ini
app_id:       (string) app id
app_key:      (string) app key
keyword:      (string) keyword to search product
```

**Optionals:** 

```ini
page:	        (int) the number of product returned, default page is 1, 10 items per page
uid:          (string) user id, may be device id or UUID
ip:           (string) IP address requested by user
ua:           (string) User-Agent information requested by user
```

- **parameter**

> keyword:  Search for keyword, the following example keyword is `shoe`

- **request**

> ?app_id={app_id}&app_key={app_key}&page=1&keyword=shoe

- **response**

```json
[{
		"asin": "B07566D3BX",
		"title": "Skechers Men's Classic Fit-Delson-Camden Sneaker,black/Grey,10 M US",
		"detailUrl": "https://www.amazon.com/Skechers-Classic-Fit-Delson-Camden-Sneaker-black/dp/B07566D3BX?psc=1&SubscriptionId=AKIAJ255YN3UDQTSJM4Q&tag=umewebagus-20&linkCode=xm2&camp=2025&creative=165953&creativeASIN=B07566D3BX",
		"largeImage": "https://images-na.ssl-images-amazon.com/images/I/41fBxLqn25L.jpg",
		"price": "$44.71"
	},
	{
		"asin": "B01N8PMBK9",
		"title": "ASICS Mens Gel-Venture 6 Running Shoe, Black/Phantom/Mid Grey, 10.5 D(M) US",
		"detailUrl": "https://www.amazon.com/ASICS-Gel-Venture-Running-Black-Phantom/dp/B01N8PMBK9?psc=1&SubscriptionId=AKIAJ255YN3UDQTSJM4Q&tag=umewebagus-20&linkCode=xm2&camp=2025&creative=165953&creativeASIN=B01N8PMBK9",
		"largeImage": "https://images-na.ssl-images-amazon.com/images/I/41Q4g5fmlPL.jpg",
		"price": "$50.89"
	},
	{
		"asin": "B07Q3WGV23",
		"title": "Skechers Women's Sure Track Trickel Slip Resistant Work Shoes, Black/Charcoal, 11 M US",
		"detailUrl": "https://www.amazon.com/Skechers-Womens-Trickel-Resistant-Charcoal/dp/B07Q3WGV23?psc=1&SubscriptionId=AKIAJ255YN3UDQTSJM4Q&tag=umewebagus-20&linkCode=xm2&camp=2025&creative=165953&creativeASIN=B07Q3WGV23",
		"largeImage": "https://images-na.ssl-images-amazon.com/images/I/41NSAoPTi7L.jpg",
		"price": "$59.95"
	},
	{
		"asin": "B01MT22X9Q",
		"title": "GW M1618-8 Fashion Sneaker 12 M",
		"detailUrl": "https://www.amazon.com/GW-M1618-8-Fashion-Sneaker-12/dp/B01MT22X9Q?psc=1&SubscriptionId=AKIAJ255YN3UDQTSJM4Q&tag=umewebagus-20&linkCode=xm2&camp=2025&creative=165953&creativeASIN=B01MT22X9Q",
		"largeImage": "https://images-na.ssl-images-amazon.com/images/I/41oBfkeycCL.jpg",
		"price": "$29.99"
	},
	{
		"asin": "1501135929",
		"title": "Shoe Dog: A Memoir by the Creator of Nike",
		"detailUrl": "https://www.amazon.com/Shoe-Dog-Memoir-Creator-Nike/dp/1501135929?SubscriptionId=AKIAJ255YN3UDQTSJM4Q&tag=umewebagus-20&linkCode=xm2&camp=2025&creative=165953&creativeASIN=1501135929",
		"largeImage": "https://images-na.ssl-images-amazon.com/images/I/51EioQX14%2BL.jpg",
		"price": "$10.94"
	},
	{
		"asin": "B07P5L1Z9J",
		"title": "SIMARI Anti Slip Water Shoes for Women Men Summer Outdoor Beach Swim Surf Pool SWS002 Circle dot dot Blue 8.5-9",
		"detailUrl": "https://www.amazon.com/SIMARI-Summer-Outdoor-SWS002-dot/dp/B07P5L1Z9J?psc=1&SubscriptionId=AKIAJ255YN3UDQTSJM4Q&tag=umewebagus-20&linkCode=xm2&camp=2025&creative=165953&creativeASIN=B07P5L1Z9J",
		"largeImage": "https://images-na.ssl-images-amazon.com/images/I/51P3ay-O%2BFL.jpg",
		"price": "$12.98"
	},
	{
		"asin": "B004LBKEPU",
		"title": "Nike Men's NIKE AIR MONARCH IV (4E) RUNNING SHOES -11;   White / Metallic Silver-Midnight Navy",
		"detailUrl": "https://www.amazon.com/Nike-MONARCH-RUNNING-Metallic-Silver-Midnight/dp/B004LBKEPU?psc=1&SubscriptionId=AKIAJ255YN3UDQTSJM4Q&tag=umewebagus-20&linkCode=xm2&camp=2025&creative=165953&creativeASIN=B004LBKEPU",
		"largeImage": "https://images-na.ssl-images-amazon.com/images/I/41v6Xtz-hSL.jpg",
		"price": "$54.98"
	},
	{
		"asin": "B07QMLWYST",
		"title": "Women Comfortable Walking Shoes Fashion Slip On Sneakers Platform Wedge Loafers Shoes 9 Purple",
		"detailUrl": "https://www.amazon.com/Comfortable-Walking-Fashion-Sneakers-Platform/dp/B07QMLWYST?psc=1&SubscriptionId=AKIAJ255YN3UDQTSJM4Q&tag=umewebagus-20&linkCode=xm2&camp=2025&creative=165953&creativeASIN=B07QMLWYST",
		"largeImage": "https://images-na.ssl-images-amazon.com/images/I/51qi5VaeASL.jpg",
		"price": "$33.98"
	},
	{
		"asin": "B00NUZCDHU",
		"title": "ASICS Men's Gel-Venture 5-M, Black/Onyx/Charcoal, 15 M US",
		"detailUrl": "https://www.amazon.com/ASICS-Gel-Venture-5-M-Black-Charcoal/dp/B00NUZCDHU?psc=1&SubscriptionId=AKIAJ255YN3UDQTSJM4Q&tag=umewebagus-20&linkCode=xm2&camp=2025&creative=165953&creativeASIN=B00NUZCDHU",
		"largeImage": "https://images-na.ssl-images-amazon.com/images/I/51cSOMfc8UL.jpg",
		"price": "$64.95"
	}
]
```

------

### Error Status Codes

| **Error Code** | **Error Msg**        |
| -------------- | -------------------- |
| 10001          | Illegal request      |
| 10002          | Unauthorized request |

- **e.g.**

```json
{
	"error_code": 10002,
	"error_msg": "Unauthorized request"
}
```

