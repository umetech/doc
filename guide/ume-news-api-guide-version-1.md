## Guide for Ume News Api Version 1.0

### Api Portal 

> https://api.eportalmobile.com/v1/news

------

### News List

**Method:**

> GET / POST

 **Required:**

```ini
app_id:       (string) app id
app_key:      (string) app key
```

**Optionals:** 

```ini
country:      (string) two uppercase country codes, e.g. US, DE, MX. default is US
language:     (string) two language code, e.g. en,es,de,ru,fr,it. default is en
limit:	      (int) the number of news returned, default is 20
offset:	      (int) the number of offsets in news lists, default is 0
width:	      (int) news thumbnail image's width, default is 150(px)
height:	      (int) news thumbnail image's height, default is 100(px)
uid:          (string) user id, may be device id or UUID
ip:           (string) IP address requested by user
ua:           (string) User-Agent information requested by user
```

- **request**

> ?app_id={app_id}&app_key={app_key}&country=US&language=en&limit=20&offset=0&width=150&height=100
>

- **response**
```json
{
	"totalItems": 2,
	"content": [{
		"contentId": "f0c7fd1b-d07a-4281-b49c-5ba7f0e05a3d",
		"title": "Indonesian haze closes schools, sparks fears for Singapore F1",
		"summary": "Toxic haze from Indonesian forest fires closed thousands of schools across the country and in neighbouring Malaysia Wednesday, while air",
		"contentSource": "AFP",
		"contentSourceDisplay": "AFP",
		"contentSourceLogo": "",
		"categories": ["Top News"],
		"categoriesEnglish": ["Top News"],
		"verticals": ["News"],
		"verticalsEnglish": ["News"],
		"images": {
			"mainImage": {
				"url": "https://imageca.thestartmagazine.com/upload/d_magazineDefault.jpg,c_fill,g_face:auto,fl_lossy,q_70,w_480/v1568784807/AFP_984bb0e1653affd5a0713089d4debe92e4b6816b.jpg",
				"width": 768,
				"height": 510
			},
			"mainImageThumbnail": {
				"url": "https://imageca.thestartmagazine.com/upload/d_magazineDefault.jpg,c_fill,g_face:auto,fl_lossy,q_95,w_150,h_100/v1568784807/AFP_984bb0e1653affd5a0713089d4debe92e4b6816b.jpg",
				"width": 150,
				"height": 100,
				"quality": 95
			},
			"additionalImages": [{
				"offset": 2627,
				"url": "https://imageca.thestartmagazine.com/upload/d_magazineDefault.jpg,c_fill,g_face:auto,fl_lossy,q_70,w_480/v1568619207/AFP_41a03d7fe676648adee2cda7e4f72e0cbc83c7d8.jpg",
				"width": 768,
				"height": 765
			}, {
				"offset": 977,
				"url": "https://imageca.thestartmagazine.com/upload/d_magazineDefault.jpg,c_fill,g_face:auto,fl_lossy,q_70,w_480/v1568784807/AFP_67de376bff28dea38474fd680b3386ad7a794b95.jpg",
				"width": 768,
				"height": 512
			}, {
				"offset": 2072,
				"url": "https://imageca.thestartmagazine.com/upload/d_magazineDefault.jpg,c_fill,g_face:auto,fl_lossy,q_70,w_480/v1568784808/AFP_5e26f1d24c945a7f83353c587ea5cf4b003b1ce8.jpg",
				"width": 768,
				"height": 512
			}]
		},
		"countries": ["CA", "GH", "ZM", "PK", "NG", "ML", "CM", "CI", "TZ", "KE", "GB", "GR", "TG", "SN", "MY", "SD", "US"],
		"locale": "en_US",
		"publishedAt": 1568792442,
		"tags": ["malaysia", "singapore", "indonesia", "environment", "pollution", "epus-news"],
		"topics": [{
			"id": "Q643546",
			"name": "haze"
		}, {
			"id": "Q36117",
			"name": "Borneo"
		}, {
			"id": "Q169994",
			"name": "smog"
		}, {
			"id": "Q833",
			"name": "Malaysia"
		}],
		"views": 0,
		"isPreview": false,
		"contentURL": "https://www.thestartmagazine.com/article/f0c7fd1b-d07a-4281-b49c-5ba7f0e05a3d?ref=WlRFLVdlYiUkJURPeDBHVzhqWXlac1E1Rmp4SzROSU1KcmtHdWFJRDU3JSQlMTM1Nzk4NjQy&countryCode=US&language=en&userId=3C70CC34E04FB6DCFF98E05F5806251C&recommendationId=TIME_BL",
		"recommendationId": "TIME_BL"
	}, {
		"contentId": "9a6712d2-b5c0-4848-87bf-66ebd2bdd997",
		"title": "Edward Snowden: US Gov’t Lawsuit to Block Book Is ‘Good for Bitcoin’",
		"summary": "Whistleblower Edward Snowden has hinted he might place his wealth in Bitcoin (BTC) to avoid the United States government confiscating the funds.",
		"contentSource": "CoinTelegraph",
		"contentSourceDisplay": "CoinTelegraph",
		"contentSourceLogo": "https://imageca.thestartmagazine.com/upload/app/CT.png",
		"categories": ["Finance", "Technology"],
		"categoriesEnglish": ["Finance", "Technology"],
		"verticals": ["Finance", "Technology"],
		"verticalsEnglish": ["Finance", "Technology"],
		"iabCategories": [596, 82],
		"images": {
			"mainImage": {
				"url": "https://imageca.thestartmagazine.com/fetch/d_magazineDefault.jpg,c_fill,g_face:auto,fl_lossy,q_70,w_480/https%3A%2F%2Fimages.cointelegraph.com%2Fimages%2F528_aHR0cHM6Ly9zMy5jb2ludGVsZWdyYXBoLmNvbS9zdG9yYWdlL3VwbG9hZHMvdmlldy9mYTQzZjI1YmNhNjBlMzAxN2M5OWYyYzI4OTUzM2FiYS5qcGc%3D.jpg",
				"width": 528,
				"height": 352
			},
			"mainImageThumbnail": {
				"url": "https://imageca.thestartmagazine.com/fetch/d_magazineDefault.jpg,c_fill,g_face:auto,fl_lossy,q_95,w_150,h_100/https%3A%2F%2Fimages.cointelegraph.com%2Fimages%2F528_aHR0cHM6Ly9zMy5jb2ludGVsZWdyYXBoLmNvbS9zdG9yYWdlL3VwbG9hZHMvdmlldy9mYTQzZjI1YmNhNjBlMzAxN2M5OWYyYzI4OTUzM2FiYS5qcGc%3D.jpg",
				"width": 150,
				"height": 100,
				"quality": 95
			},
			"additionalImages": []
		},
		"countries": ["AE", "AU", "BS", "CA", "CI", "CM", "CY", "EG", "GB", "GH", "GR", "ID", "IE", "IL", "IN", "JM", "JO", "KE", "KW", "LK", "ML", "MY", "NG", "NZ", "PH", "PK", "QA", "SA", "SG", "SN", "TG", "TH", "TZ", "US", "VN", "ZA", "ZM"],
		"locale": "en_US",
		"publishedAt": 1568792331,
		"tags": ["bitcoin", "edward snowden", "united states", "epus-crypto"],
		"persons": [{
			"id": "Q13424289",
			"name": "Edward Snowden"
		}],
		"topics": [{
			"id": "Q121194",
			"name": "National Security Agency"
		}, {
			"id": "Q131723",
			"name": "Bitcoin"
		}, {
			"id": "Q26102",
			"name": "whistleblower"
		}],
		"views": 0,
		"isPreview": false,
		"contentURL": "https://www.thestartmagazine.com/article/9a6712d2-b5c0-4848-87bf-66ebd2bdd997?ref=WlRFLVdlYiUkJURPeDBHVzhqWXlac1E1Rmp4SzROSU1KcmtHdWFJRDU3JSQlMTM1Nzk4NjQy&countryCode=US&language=en&userId=3C70CC34E04FB6DCFF98E05F5806251C&recommendationId=TIME_BL",
		"recommendationId": "TIME_BL"
	}]
}
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

