## Guide for ShareCard Api Version 1.0

### Api 接口总 Url

> [https://sharecard.cc/v1]()

---

### Categories 分类列表Api

**Method**

> GET 与 POST

**Required(必须参数):**

```ini
app_id:       分配的app id
app_key:      分配的app key
```
**Options(可选参数):**

```ini
locale:       (字符串)国家语言区域代码, 如:en_US, de_De等,默认为en_US
uid:          (字符串)用户id
ip:           (字符串)用户请求的ip地址
ua:           (字符串)用户请求的user-agent信息
```
**request**

> https://sharecard.cc/v1/menu?app_id={app_id}&app_key={app_key}&locale=en_US

**response**

```json
{
	"config_id": 1,
	"timestamp": 1568615240057,
	"menus": [{
		"category": "like",
		"title": "Like",
		"icon": "https://sharecard.cc/logo/like.png",
		"index": 1
	}, {
		"category": "amazon",
		"title": "Amazon",
		"icon": "https://sharecard.cc/logo/amazon.png",
		"index": 2
	}, {
		"category": "bestbuy",
		"title": "BestBuy",
		"icon": "https://sharecard.cc/logo/bestbuy.png",
		"index": 3
	}, {
		"category": "bloomingdales",
		"title": "Bloomingdales",
		"icon": "https://sharecard.cc/logo/bloomingdales.png",
		"index": 4
	}],
	"time": "36ms"
}
```

---

### Search 搜索列表Api

**Required(必须参数):**

```ini
app_id:       分配的app id
app_key:      分配的app key
```


**Options(可选参数):**

```ini
keyword:       (字符串) 搜索关键词,默认为空
limit:         (整型)返回的游戏条数,  默认为10条
locale:        (字符串)国家语言区域代码, 如:en_US, de_De等,默认为en_US
prev:          (字符串)向前翻页标识,由API接口产生,请求时带上
next:          (字符串) 向后翻页标识,由API接口产生,请求时带上
uid:           (字符串)用户id
ip:            (字符串)用户请求的ip地址
ua:            (字符串)用户请求的user-agent信息
```

**Method**

> GET 与 POST

**parameter:**

> keyword: 为搜索的关键词, 下面的例子关键词为shoe

**request**

> https://sharecard.cc/v1/search?app_id={app_id}&app_key={app_key}&locale=en_US&category=amazon&keyword=shoe&limit=10

**response**

```json
{
	"category": "amazon",
	"keyword": "shoe",
	"locale": "en_US",
	"prev": "",
	"next": "10",
	"data": [{
		"id": "a4ba8f27d2657b6c9d4651176f60dacb",
		"title": "ASICS Mens Gel-Venture 6 Running Shoe, Black/Phantom/Mid Grey, 10.5 D(M) US",
		"image": "https://images-na.ssl-images-amazon.com/images/I/41-cQauRfpL.jpg",
		"url": "https://www.amazon.com/ASICS-Gel-Venture-Running-Black-Phantom/dp/B01N8PMBK9?psc=1&SubscriptionId=AKIAJ255YN3UDQTSJM4Q&tag=umewebagus-20&linkCode=xm2&camp=2025&creative=165953&creativeASIN=B01N8PMBK9",
		"optional": "{\"price\":\"$44.95\"}"
	}, {
		"id": "90d76e038b580f9aa7cda90688eb92bf",
		"title": "Nfinity Vengeance Cheer Shoe (Pair), White, 9",
		"image": "https://images-na.ssl-images-amazon.com/images/I/41C1pGnB5jL.jpg",
		"url": "https://www.amazon.com/Nfinity-Vengeance-Cheer-Shoe-White/dp/B006WAFGT2?psc=1&SubscriptionId=AKIAJ255YN3UDQTSJM4Q&tag=umewebagus-20&linkCode=xm2&camp=2025&creative=165953&creativeASIN=B006WAFGT2",
		"optional": "{\"price\":\"$99.99\"}"
	}, {
		"id": "c8fc6758f6c450a61d8072a73538ef74",
		"title": "Skechers for Work Men's Felton Shoe, Black, 11 M US",
		"image": "https://images-na.ssl-images-amazon.com/images/I/41fOKbB6%2BzL.jpg",
		"url": "https://www.amazon.com/Skechers-Work-Mens-Felton-Black/dp/B00HSX6YWA?psc=1&SubscriptionId=AKIAJ255YN3UDQTSJM4Q&tag=umewebagus-20&linkCode=xm2&camp=2025&creative=165953&creativeASIN=B00HSX6YWA",
		"optional": "{\"price\":\"$39.14\"}"
	}, {
		"id": "c7a22f435aa114fb4577fe3ce382d276",
		"title": "Feetmat Mens Tennis Shoes Ultra Lightweight Non Slip Sport Shoes Slip-On Sneakers for Boys Fashion Shoes Black Running Shoes Black 10M",
		"image": "https://images-na.ssl-images-amazon.com/images/I/41qs-boGF2L.jpg",
		"url": "https://www.amazon.com/Feetmat-Lightweight-Sneakers-Fashion-Running/dp/B07LBM8PVP?psc=1&SubscriptionId=AKIAJ255YN3UDQTSJM4Q&tag=umewebagus-20&linkCode=xm2&camp=2025&creative=165953&creativeASIN=B07LBM8PVP",
		"optional": "{\"price\":\"$35.99\"}"
	}, {
		"id": "a419be7320f57f993d296318b8d1af43",
		"title": "adidas Originals Men's Seeley Running Shoe, Ash Grey/White/Black, 10.5 M US",
		"image": "https://images-na.ssl-images-amazon.com/images/I/41%2Br6RzujIL.jpg",
		"url": "https://www.amazon.com/adidas-Originals-Seeley-Running-White/dp/B0106JK7S4?psc=1&SubscriptionId=AKIAJ255YN3UDQTSJM4Q&tag=umewebagus-20&linkCode=xm2&camp=2025&creative=165953&creativeASIN=B0106JK7S4",
		"optional": "{\"price\":\"$46.00\"}"
	}],
	"time": "920ms"
}
```

**注意**

>  返回的结果中有`prev`与`next`参数,`prev` 表示向前翻页的标识, `next`表示向后翻页的结识, 这两个参数的值为字符串, 当需要向后翻页时, 需要带上`next`参数, 比如这里`next`为10, 向后翻页, 则请求时的`Url`为:

>  https://sharecard.cc/v1/search?app_id={app_id}&app_key={app_key}&locale=en_US&category=amazon&keyword=shoe&limit=10&next=10 
>  
>  `prev`与`next`均是字符串的值

**特别注意**

> 返回的数据中有一个多选的参数 `optional`, 这里携带的数据为`price`, 不同的分类`optional`会携带不同的数据

---

###  短链接生成 Api

> 短链接主要为了服务于分享时之用, 短链接的格式为 https://sharecard.mobi/xxxxxx `xxxxxx` 为6位hex码字符串

**Method**

> 仅支持POST

**Required(必须参数):**

```ini
app_id:       分配的app id
app_key:      分配的app key
url:					目标长网址
```

**request**

> https://sharecard.cc/v1/shorturl

POST提交的数据

```ini
app_id={app_id}
app_key={app_key}
url=https://www.baidu.com
```

**response**

```json
{
	"url": "https://sharecard.mobi/000001"
}
```

返回的url为短网址

---

### Error Status Codes(错误代码)

| **Error Code** | **Error Msg**          |
| -------------- | ---------------------- |
| 10001          | Illegal   request      |
| 10002          | Unauthorized   request |

**For example:**

```json
{
	"error_code": 10002,
	"error_msg": "Unauthorized request"
}
```