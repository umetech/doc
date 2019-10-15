# Guide for Ume GameBox Api Version 1.0

*-- Last updated: Oct 15,2019*

## Api Portal 

> https://api.eportalmobile.com/v1/gamebox

------

## Games for Banner

**Method:**

> GET / POST

 **Required:**

```ini
app_id:       (string) app id
app_key:      (string) app key
```

**Optionals:** 

```ini
limit:	      (int) the number of games returned, default is 5
uid:          (string) user id, may be device id or UUID
ip:           (string) IP address requested by user
ua:           (string) User-Agent information requested by user
```

- **request**

> /banner?app_id={app_id}&app_key={app_key}

- **response**

```json
{
	"code": 200,
	"msg": "数据获取成功",
	"data": [{
		"id": 3,
		"categories": "",
		"url": "https://test3",
		"name": "test3",
		"game_img_url": "",
		"main_color": "",
		"play_num": 0
	}, {
		"id": 2,
		"categories": "",
		"url": "https://test2",
		"name": "test2",
		"game_img_url": "",
		"main_color": "",
		"play_num": 0
	}, {
		"id": 1,
		"categories": "",
		"url": "https://test1",
		"name": "test1",
		"game_img_url": "",
		"main_color": "",
		"play_num": 0
	}]
}
```

------

## Games for All in One

**Method:**

> GET / POST

 **Required:**

```ini
app_id:       (string) app id
app_key:      (string) app key
```

**Optionals:** 

```ini
categories:   (string) game categories, will display default categories when it is empty
size:	        (int) the number of games returned for per category, default is 5
uid:          (string) user id, may be device id or UUID
ip:           (string) IP address requested by user
ua:           (string) User-Agent information requested by user
```

- **parameter**

> categories:  Define games that need to be returned by category names, with comma separations between each category, Default categories is `Arcade,Sports & Racing,Beauty & Girl,Strategy,Puzzle & Logic,Adventure,Action & Risk,Music` when catgories is empty

- **request**

> /all_in_one?app_id={app_id}&app_key={app_key}&size=2
>
> /all_in_one?app_id={app_id}&app_key={app_key}&categories=Racing,Sport,Girl&size=2

- **response**

```json
{
	"code": 200,
	"msg": "数据获取成功",
	"data": {
		"Arcade": {
			"category_icon": "",
			"data": [{
				"id": 344,
				"url": "http://12.mosegame.com/detail?id=444",
				"categories": "Arcade",
				"name": "Skip The Sprint",
				"game_img_url": "https://images.quickgame.top/2019090608513194405.jpg",
				"play_num": 641938,
				"main_color": null
			}, {
				"id": 310,
				"url": "http://12.mosegame.com/detail?id=433",
				"categories": "Arcade",
				"name": "Spiny",
				"game_img_url": "https://images.quickgame.top/2018102411453498008.jpg",
				"play_num": 437239,
				"main_color": null
			}]
		},
		"Sports & Racing": {
			"category_icon": "",
			"data": [{
				"id": 348,
				"url": "http://12.mosegame.com/detail?id=81",
				"categories": "Sports & Racing",
				"name": "Endless paper boat",
				"game_img_url": "https://images.quickgame.top/2018102410075431719.png",
				"play_num": 2191187,
				"main_color": null
			}, {
				"id": 320,
				"url": "http://12.mosegame.com/detail?id=365",
				"categories": "Sports & Racing",
				"name": "Cars",
				"game_img_url": "https://images.quickgame.top/2018102411304090374.png",
				"play_num": 704525,
				"main_color": null
			}]
		},
		"Beauty & Girl": {
			"category_icon": "",
			"data": [{
				"id": 343,
				"url": "http://12.mosegame.com/detail?id=508",
				"categories": "Beauty & Girl",
				"name": "Halloween Party",
				"game_img_url": "https://images.quickgame.top/2019082009012970505.jpeg",
				"play_num": 734219,
				"main_color": null
			}, {
				"id": 314,
				"url": "http://12.mosegame.com/detail?id=58",
				"categories": "Beauty & Girl",
				"name": "Kiss Kiss",
				"game_img_url": "https://images.quickgame.top/2018102410025440783.png",
				"play_num": 95026093,
				"main_color": null
			}]
		},
		"Strategy": {
			"category_icon": "",
			"data": [{
				"id": 357,
				"url": "http://12.mosegame.com/detail?id=420",
				"categories": "Strategy",
				"name": "Clash of Vikings",
				"game_img_url": "https://images.quickgame.top/2018102411423875669.jpg",
				"play_num": 688531,
				"main_color": null
			}, {
				"id": 350,
				"url": "http://12.mosegame.com/detail?id=375",
				"categories": "Strategy",
				"name": "Blitz Tactics",
				"game_img_url": "https://images.quickgame.top/2018102411325992673.jpeg",
				"play_num": 522795,
				"main_color": null
			}]
		},
		"Puzzle & Logic": {
			"category_icon": "",
			"data": [{
				"id": 359,
				"url": "http://12.mosegame.com/detail?id=201",
				"categories": "Puzzle & Logic",
				"name": "Slingshot Monster",
				"game_img_url": "https://images.quickgame.top/20190906084323421.png",
				"play_num": 557439,
				"main_color": null
			}, {
				"id": 358,
				"url": "http://12.mosegame.com/detail?id=388",
				"categories": "Puzzle & Logic",
				"name": "Fruita Crush",
				"game_img_url": "https://images.quickgame.top/2018102411354429409.jpg",
				"play_num": 678372,
				"main_color": null
			}]
		},
		"Adventure": {
			"category_icon": "",
			"data": [{
				"id": 356,
				"url": "http://12.mosegame.com/detail?id=259",
				"categories": "Adventure",
				"name": "Frozen Castle Adventure",
				"game_img_url": "https://images.quickgame.top/2018102411064269300.jpeg",
				"play_num": 420472,
				"main_color": null
			}, {
				"id": 353,
				"url": "http://12.mosegame.com/detail?id=350",
				"categories": "Adventure",
				"name": "Beautiful World",
				"game_img_url": "https://images.quickgame.top/201810241126239565.png",
				"play_num": 346949,
				"main_color": null
			}]
		},
		"Action & Risk": {
			"category_icon": "",
			"data": [{
				"id": 355,
				"url": "http://12.mosegame.com/detail?id=422",
				"categories": "Action & Risk",
				"name": "Exploration",
				"game_img_url": "https://images.quickgame.top/2019072308415594838.jpg",
				"play_num": 680174,
				"main_color": null
			}, {
				"id": 352,
				"url": "http://12.mosegame.com/detail?id=209",
				"categories": "Action & Risk",
				"name": "Jump With Justin",
				"game_img_url": "https://images.quickgame.top/201810241053054666.jpg",
				"play_num": 349278,
				"main_color": null
			}]
		},
		"Music": {
			"category_icon": "",
			"data": [{
				"id": 304,
				"url": "http://12.mosegame.com/detail?id=443",
				"categories": "Music",
				"name": "Snow Ball Champions",
				"game_img_url": "https://images.quickgame.top/2018102411474778529.jpeg",
				"play_num": 716554,
				"main_color": null
			}, {
				"id": 203,
				"url": "http://12.mosegame.com/detail?id=462",
				"categories": "Music",
				"name": "Bad Donut",
				"game_img_url": "https://images.quickgame.top/2018102411514564950.jpg",
				"play_num": 552476,
				"main_color": null
			}]
		}
	}
}
```

---

## Error Status Codes

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

