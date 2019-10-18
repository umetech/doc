# Guide for Ume GamePix Api Version 1.0

*-- Last updated: Oct 18,2019*

## Api Portal 

> https://api.eportalmobile.com/v1/gamepix

------

### Game Categories

**Method:**

> GET / POST

- **request**

> /categories

- **response**

```json
[{
	"name": "Adventure",
	"icon": "",
	"color": null,
	"game_count": 50
}, {
	"name": "Arcade",
	"icon": "",
	"color": null,
	"game_count": 103
}, {
	"name": "Casino",
	"icon": "",
	"color": null,
	"game_count": 20
}, {
	"name": "Classics",
	"icon": "",
	"color": null,
	"game_count": 36
}, {
	"name": "Junior",
	"icon": "",
	"color": null,
	"game_count": 28
}, {
	"name": "Puzzles",
	"icon": "",
	"color": null,
	"game_count": 90
}, {
	"name": "Slots",
	"icon": "",
	"color": null,
	"game_count": 1
}, {
	"name": "Sports",
	"icon": "",
	"color": null,
	"game_count": 41
}, {
	"name": "Strategy",
	"icon": "",
	"color": null,
	"game_count": 15
}]
```

------

### List Game By Category & Type

**Method:**

> GET / POST

 **Optionals:** 

```ini
category:			(string) the category of game, list all games when category is empty
type:					(int) the type of game, default is 0
limit:	      (int) the number of games returned, default is 10
offset:				(int) the number of offsets in games lists, default is 0
```

- **parameter**

> type: The default is `0`, which means that it is a normal game, When type is `1`, it means banner game, When type is `2`, it means featured game

- **request**

> /list?category={category}&type={type}&limit={limit}&offset={offset}

### some examples of request

  >/list               							
  >
  >/list?type=1&limit=5
  >
  >/list?category=Sports&limit=10

(1). List all games with default values type=0,limit=10,offset=0

(2). List games with type=0, limit=5

(3). List all games with category=Sports, limit=10

- **response**

```json
[{
	"title": "Calming Lia",
	"url": "https://play.gamepix.com/calming-lia/embed?sid=110900",
	"id": 40355,
	"play_count": 4760
}, {
	"title": "Cut the Rope Experiments",
	"url": "https://play.gamepix.com/cut-the-rope-experiments/embed?sid=110900",
	"id": 40337,
	"play_count": 4740
}, {
	"title": "Guns n Glory Heroes",
	"url": "https://play.gamepix.com/guns-n-glory-heroes/embed?sid=110900",
	"id": 40302,
	"play_count": 4720
}, {
	"title": "Tom & Jerry Mouse Maze",
	"url": "https://play.gamepix.com/tom-jerry-mouse-maze/embed?sid=110900",
	"id": 40363,
	"play_count": 4700
}, {
	"title": "Badland",
	"url": "https://play.gamepix.com/badland/embed?sid=110900",
	"id": 40274,
	"play_count": 4680
}]
```

------

## Game Detail

**Method:**

> GET / POST

 **Required:**

```ini
id:       		(int) game id
```

- **request**

> /detail?id={id}
>

- **response**

```json
{
	"id": 40355,
	"title": "Calming Lia",
	"categories": "Puzzles",
	"url": "https://play.gamepix.com/calming-lia/embed?sid=110900",
	"description": "Save a little girl from her nightmares! Calming Lia is a relaxing match-three game. Like a lullaby, it is best played at night before sleeping. Help Lia and her plush friend, Bao the bear, rescue her dreams from the horrors of the evil Boogie Man!",
	"play_count": 4760
}
```

---

## Game Images

There are four types of game images for each game

1. cover (768 × 256):   https://cdn.eportalmobile.com/gamepix/cover_{id}.png
2. icon (400 × 246): https://cdn.eportalmobile.com/gamepix/icon_{id}.png
3. thumbnail (250 x 250): https://cdn.eportalmobile.com/gamepix/thumbnail_{id}.png
4. logo (369 × 200) : https://cdn.eportalmobile.com/gamepix/logo_{id}.png

**Notice** : Just only featured games have `logo` images

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

