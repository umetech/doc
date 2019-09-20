## Guide for Ume Game Api Version 2.0
*-- Last updated: September 20,2019*

### Api Portal 

> https://api.eportalmobile.com/v2/game

-------
### Game Categories

**Method:**

> GET / POST

 **Required:**

```ini
app_id:       (string) app id
app_key:      (string) app key
```

**Optionals:** 

```ini
uid:          (string) user id, may be device id or UUID
ip:           (string) IP address requested by user
ua:           (string) User-Agent information requested by user
```

- **request**

> /categories?app_id={app_id}&app_key={app_key}

- **response**
```json
["Action", "Word", "Shooting", "Board", "Racing", "Action & Risk", "Jump&Run", "Sports", "Hidden Object", "Puzzle & Logic", "Adventure", "Sports & Racing", "Dice", "Educational", "Pairs", "Trivia", "Kids", "Girls", "Arcade", "Match 3", "Card", "Beauty & Girl", "Puzzle", "Simulation", "Casino", "Music", "Family", "Strategy", "Role Playing"]
```
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
category:     (string) game category, will display all categories when it is empty
limit:	      (int) the number of games returned, default is 20
offset:	      (int) the number of offsets in games lists, default is 0
uid:          (string) user id, may be device id or UUID
ip:           (string) IP address requested by user
ua:           (string) User-Agent information requested by user
```

- **request**

> /list?app_id={app_id}&app_key={app_key}&limit=5&offset=0
>
> /list?app_id={app_id}&app_key={app_key}&category=Racing&limit=5&offset=0

- **response**

```json
[{
	"id": 1,
	"icon": "https://d1bjj4kazoovdg.cloudfront.net/assets/games/garden-tales/big_icon.jpg?p=umebrowser",
	"thumb": "http://d1bjj4kazoovdg.cloudfront.net/assets/games/garden-tales/teaser@2x.jpg?p=umebrowser",
	"title": "Garden Tales",
	"url": "https://games.softgames.com/games/garden-tales/gamesites/5896/"
}, {
	"id": 2,
	"icon": "https://d1bjj4kazoovdg.cloudfront.net/assets/games/cookie-crush-3/big_icon.jpg?p=umebrowser",
	"thumb": "http://d1bjj4kazoovdg.cloudfront.net/assets/games/cookie-crush-3/teaser@2x.jpg?p=umebrowser",
	"title": "Cookie Crush 3",
	"url": "https://games.softgames.com/games/cookie-crush-3/gamesites/5896/"
}, {
	"id": 3,
	"icon": "https://d1bjj4kazoovdg.cloudfront.net/assets/games/solitaire-tripeaks/big_icon.jpg?p=umebrowser",
	"thumb": "http://d1bjj4kazoovdg.cloudfront.net/assets/games/solitaire-tripeaks/teaser@2x.jpg?p=umebrowser",
	"title": "Solitaire Story - TriPeaks",
	"url": "https://games.softgames.com/games/solitaire-tripeaks/gamesites/5896/"
}, {
	"id": 4,
	"icon": "https://d1bjj4kazoovdg.cloudfront.net/assets/games/jewels-blitz-3/big_icon.jpg?p=umebrowser",
	"thumb": "http://d1bjj4kazoovdg.cloudfront.net/assets/games/jewels-blitz-3/teaser@2x.jpg?p=umebrowser",
	"title": "Jewels Blitz 3",
	"url": "https://games.softgames.com/games/jewels-blitz-3/gamesites/5896/"
}, {
	"id": 5,
	"icon": "https://d1bjj4kazoovdg.cloudfront.net/assets/games/bubble-shooter-hd/big_icon.jpg?p=umebrowser",
	"thumb": "http://d1bjj4kazoovdg.cloudfront.net/assets/games/bubble-shooter-hd/teaser@2x.jpg?p=umebrowser",
	"title": "Bubble Shooter HD",
	"url": "https://games.softgames.com/games/bubble-shooter-hd/gamesites/5896/"
}]
```

------
### Search List

**Method:**

> GET / POST

 **Required:**

```ini
app_id:       (string) app id
app_key:      (string) app key
keyword:      (string) keyword to search game
```

**Optionals:** 

```ini
category:     (string) game category, will search all categories when it is empty
limit:	      (int) the number of games returned, default is 20
offset:	      (int) the number of offsets in games lists, default is 0
uid:          (string) user id, may be device id or UUID
ip:           (string) IP address requested by user
ua:           (string) User-Agent information requested by user
```

- **parameter**

> keyword:  search for keyword, the following example keyword is `girl`

- **request**

> /search?app_id={app_id}&app_key={app_key}&keyword=girl&limit=5&offset=0
>
> /search?app_id={app_id}&app_key={app_key}&category=Racing&keyword=girl&limit=5&offset=0

- **response**

```json
[{
	"id": 109,
	"icon": "https://d1bjj4kazoovdg.cloudfront.net/assets/games/room-makeover-maries-girl-games/big_icon.jpg?p=umebrowser",
	"thumb": "http://d1bjj4kazoovdg.cloudfront.net/assets/games/room-makeover-maries-girl-games/teaser@2x.jpg?p=umebrowser",
	"title": "Room Makeover - Marie's Girl Games",
	"url": "https://games.softgames.com/games/room-makeover-maries-girl-games/gamesites/5896/"
}, {
	"id": 136,
	"icon": "https://d1bjj4kazoovdg.cloudfront.net/assets/games/nail-salon-maries-girl-games/big_icon.jpg?p=umebrowser",
	"thumb": "http://d1bjj4kazoovdg.cloudfront.net/assets/games/nail-salon-maries-girl-games/teaser@2x.jpg?p=umebrowser",
	"title": "Nail Salon - Marie's Girl Games",
	"url": "https://games.softgames.com/games/nail-salon-maries-girl-games/gamesites/5896/"
}, {
	"id": 180,
	"icon": "https://d1bjj4kazoovdg.cloudfront.net/assets/games/shoe-designer-maries-girl-games/big_icon.jpg?p=umebrowser",
	"thumb": "http://d1bjj4kazoovdg.cloudfront.net/assets/games/shoe-designer-maries-girl-games/teaser@2x.jpg?p=umebrowser",
	"title": "Shoe Designer - Marie's Girl Games",
	"url": "https://games.softgames.com/games/shoe-designer-maries-girl-games/gamesites/5896/"
}, {
	"id": 362,
	"icon": "https://d1bjj4kazoovdg.cloudfront.net/assets/games/girls-on-job/big_icon.jpg?p=umebrowser",
	"thumb": "http://d1bjj4kazoovdg.cloudfront.net/assets/games/girls-on-job/teaser@2x.jpg?p=umebrowser",
	"title": "Girls on Job",
	"url": "https://games.softgames.com/games/girls-on-job/gamesites/5896/"
}, {
	"id": 432,
	"icon": "https://images.quickgame.top/2018102411291055491.jpg",
	"thumb": "https://images.quickgame.top/2018102411291055491.jpg",
	"title": "Girl's Dash Puzzle",
	"url": "http://12.mosegame.com/detail?id=361"
}]
```

------
### Game Detail

**Method:**

> GET / POST

 **Required:**

```ini
app_id:       (string) app id
app_key:      (string) app key
id:						(int) game id
```

**Optionals:** 

```ini
uid:          (string) user id, may be device id or UUID
ip:           (string) IP address requested by user
ua:           (string) User-Agent information requested by user
```

- **request**

> /detail?app_id={app_id}&app_key={app_key}&id=3

- **response**

```json
{
	"id": 3,
	"icon": "https://d1bjj4kazoovdg.cloudfront.net/assets/games/solitaire-tripeaks/big_icon.jpg?p=umebrowser",
	"thumb": "http://d1bjj4kazoovdg.cloudfront.net/assets/games/solitaire-tripeaks/teaser@2x.jpg?p=umebrowser",
	"title": "Solitaire Story - TriPeaks",
	"url": "https://games.softgames.com/games/solitaire-tripeaks/gamesites/5896/",
	"screenshots": "https://d1bjj4kazoovdg.cloudfront.net/assets/games/solitaire-tripeaks/gal_01.jpg?p=umebrowser,https://d1bjj4kazoovdg.cloudfront.net/assets/games/solitaire-tripeaks/gal_02.jpg?p=umebrowser,https://d1bjj4kazoovdg.cloudfront.net/assets/games/solitaire-tripeaks/gal_03.jpg?p=umebrowser",
	"categories": "Card,Casino,Board,Strategy",
	"content": "Solitaire Story - the famous messenger game is now also available here! Play your favorite card game and explore distant countries, fantastic landscapes, and famous landmarks. You have to draw cards one at a time from your stockpile. Select the cards that are one higher or one lower in value to your drawn card to remove it from the playing field. To complete a level you need to remove all the cards from the playing field without running out of cards from your stockpile. Complete the daily missions and events to unlock new deck designs and prizes that help you solve those tricky levels. Play Solitaire Story now for free and join the thousands of Friends of Solitaire!"
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

