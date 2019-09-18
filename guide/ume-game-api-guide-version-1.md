## Guide for Ume Game Api Version 1.0

### Api Portal 

> https://api.eportalmobile.com/v1/game

------

### Game List

**Method:**

> GET / POST

 **Required:**

```ini
app_id:       (string) app id
app_key:      (string) app key
```

**Optionals:** 

```ini
limit:	      (int) the number of games returned, default is 20
offset:	      (int) the number of offsets in games lists, default is 0
uid:          (string) user id, may be device id or UUID
ip:           (string) IP address requested by user
ua:           (string) User-Agent information requested by user
```

- **request**

> ?app_id={app_id}&app_key={app_key}&limit=5&offset=0

- **response**

```json
{
	"offset": 0,
	"items": [{
		"id": 6,
		"name": "Aqua Friends",
		"introduction": "Come help the lonely little creatures together so they are no longer alone",
		"url": "http://12.mosegame.com/detail?id=6",
		"categories": "Arcade",
		"rating": "10.0",
		"thumb": "https://images.quickgame.top/2019082009002228800.jpg"
	}, {
		"id": 88,
		"name": "Fruit Ninja",
		"introduction": "Welcome to the fruite ninja. Your objective: become a master of slicing fruit! What better way to do that than play Fruit Ninja, the original hit fruit-slicing game?",
		"url": "http://12.mosegame.com/detail?id=88",
		"categories": "Arcade",
		"rating": "10.0",
		"thumb": "https://images.quickgame.top/2018110809563244330.png"
	}, {
		"id": 355,
		"name": "Mini Racer",
		"introduction": "Drive a cool sports car, don't be hit by other vehicles, win the game",
		"url": "http://12.mosegame.com/detail?id=355",
		"categories": "Sports & Racing",
		"rating": "10.0",
		"thumb": "https://images.quickgame.top/2019030514003912405.png"
	}, {
		"id": 324,
		"name": "Prof. Bubble",
		"introduction": "Help the professor to match the elemental potions together",
		"url": "http://12.mosegame.com/detail?id=324",
		"categories": "Arcade",
		"rating": "10.0",
		"thumb": "https://images.quickgame.top/2019030803113368223.jpg"
	}, {
		"id": 255,
		"name": "Magic Tiles 3",
		"introduction": "In this music game, click on the black button to pop up beautiful songs.",
		"url": "http://12.mosegame.com/detail?id=255",
		"categories": "Music",
		"rating": "10.0",
		"thumb": "https://images.quickgame.top/2018102411054530856.jpeg"
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

