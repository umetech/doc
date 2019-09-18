## Guide for Ume Search Suggestion Api Version 1.0

### Api Portal 

> https://search.eportalmobile.com/v1/suggestion

------

### Search Suggestion List

**Method:**

> GET / POST

 **Required:**

```ini
app_id:       (string) app id
app_key:      (string) app key
keyword:      (string) keyword to search
```

**Optionals:** 

```ini
limit:	      (int) the number of suggestions returned, the default is 5, the maximum is 10
shopping:			(int) Whether to return shopping suggestion, default is 1, disable is 0
offset:	      (int) the number of offsets in games lists, the default is 0
toggle:				(int) whether to open the association words, the default is 0, enable is 1
size:					(int) limit the number of association words, the default is 5, the maximum is 20
uid:          (string) user id, may be device id or UUID
ip:           (string) IP address requested by user
ua:           (string) User-Agent information requested by user
```

### example 1

- **request**

> ?app_id={app_id}&app_key={app_key}&keyword=shoe

- **response**

```json
{
	"query": "shoe",
	"suggestions": [{
		"id": 682804,
		"type": 1,
		"title": "jcpenney.com - Shop Deals on Brands You Love",
		"url": "https://search.eportalmobile.com/v1/redirect?app_id=test&app_key=e01ce9d6a3f8f99d23ab26bdab9325da&id=cb15e5a9125d4fbda7c27b091a030ec7",
		"logo": "https://cdn.45tu1c0.com/account/23740/200/1521228087119.jpg",
		"image": "https://cdn.45tu1c0.com/account/23740/200/1521228087119.jpg"
	}, {
		"id": 682805,
		"type": 1,
		"title": "kohls.com - Online Exclusive Offers",
		"url": "https://search.eportalmobile.com/v1/redirect?app_id=test&app_key=e01ce9d6a3f8f99d23ab26bdab9325da&id=7adeb83a1d2743f29ec17f573c95f6bb",
		"logo": "https://cdn.45tu1c0.com/account/74004/200/1521228087224.jpg",
		"image": "https://cdn.45tu1c0.com/account/74004/200/1521228087224.jpg"
	}, {
		"id": 682806,
		"type": 3,
		"title": "Shoedazzle",
		"url": "https://search.eportalmobile.com/v1/redirect?app_id=test&app_key=e01ce9d6a3f8f99d23ab26bdab9325da&id=9bbc53b9fe584e6e81f899ed4dd26a43",
		"logo": "http://static.siteplug.com/96x96/68c77d2e75f6c059.png",
		"image": "http://static.siteplug.com/96x96/68c77d2e75f6c059.png"
	}, {
		"id": 682807,
		"type": 3,
		"title": "Shoespie",
		"url": "https://search.eportalmobile.com/v1/redirect?app_id=test&app_key=e01ce9d6a3f8f99d23ab26bdab9325da&id=6ff69c161aba4749bdab878cbbd1dcaa",
		"logo": "http://static.siteplug.com/96x96/763e27ba9fbac1b1.png",
		"image": "http://static.siteplug.com/96x96/763e27ba9fbac1b1.png"
	}, {
		"id": 682808,
		"type": 2,
		"title": "Shoes, Boots, Sneakers, Sandals, and more | Shoe Carnival",
		"url": "https://search.eportalmobile.com/v1/redirect?app_id=test&app_key=e01ce9d6a3f8f99d23ab26bdab9325da&id=ce4d2d40433e4adfa6a9a41913533270",
		"logo": "https://i.instantsearch.net/fav128/www_shoecarnival_com.png?sig=W5ohu1M3",
		"image": "https://i.instantsearch.net/fav128/www_shoecarnival_com.png?sig=W5ohu1M3"
	}],
	"time": "3ms"
}
```

### example 2

- **request**

> ?app_id={app_id}&app_key={app_key}&keyword=shoe&toggle=1&size=8

- **response**

```json
{
	"query": "shoe",
	"suggestions": [{
		"id": 682804,
		"type": 1,
		"title": "jcpenney.com - Shop Deals on Brands You Love",
		"url": "https://search.eportalmobile.com/v1/redirect?app_id=test&app_key=e01ce9d6a3f8f99d23ab26bdab9325da&id=cb15e5a9125d4fbda7c27b091a030ec7",
		"logo": "https://cdn.45tu1c0.com/account/23740/200/1521228087119.jpg",
		"image": "https://cdn.45tu1c0.com/account/23740/200/1521228087119.jpg"
	}, {
		"id": 682805,
		"type": 1,
		"title": "kohls.com - Online Exclusive Offers",
		"url": "https://search.eportalmobile.com/v1/redirect?app_id=test&app_key=e01ce9d6a3f8f99d23ab26bdab9325da&id=7adeb83a1d2743f29ec17f573c95f6bb",
		"logo": "https://cdn.45tu1c0.com/account/74004/200/1521228087224.jpg",
		"image": "https://cdn.45tu1c0.com/account/74004/200/1521228087224.jpg"
	}, {
		"id": 682806,
		"type": 3,
		"title": "Shoedazzle",
		"url": "https://search.eportalmobile.com/v1/redirect?app_id=test&app_key=e01ce9d6a3f8f99d23ab26bdab9325da&id=9bbc53b9fe584e6e81f899ed4dd26a43",
		"logo": "http://static.siteplug.com/96x96/68c77d2e75f6c059.png",
		"image": "http://static.siteplug.com/96x96/68c77d2e75f6c059.png"
	}, {
		"id": 682807,
		"type": 3,
		"title": "Shoespie",
		"url": "https://search.eportalmobile.com/v1/redirect?app_id=test&app_key=e01ce9d6a3f8f99d23ab26bdab9325da&id=6ff69c161aba4749bdab878cbbd1dcaa",
		"logo": "http://static.siteplug.com/96x96/763e27ba9fbac1b1.png",
		"image": "http://static.siteplug.com/96x96/763e27ba9fbac1b1.png"
	}, {
		"id": 682808,
		"type": 2,
		"title": "Shoes, Boots, Sneakers, Sandals, and more | Shoe Carnival",
		"url": "https://search.eportalmobile.com/v1/redirect?app_id=test&app_key=e01ce9d6a3f8f99d23ab26bdab9325da&id=ce4d2d40433e4adfa6a9a41913533270",
		"logo": "https://i.instantsearch.net/fav128/www_shoecarnival_com.png?sig=W5ohu1M3",
		"image": "https://i.instantsearch.net/fav128/www_shoecarnival_com.png?sig=W5ohu1M3"
	}],
	"keywords": ["shoe carnival", "shoe palace", "shoe stores", "shoe411", "shoe4africa inc", "shoe4africa org", "shoe4u", "shoeacadamy.org/footlocker"],
	"time": "4ms"
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

