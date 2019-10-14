# Guide for Ume GameBox Api Version 1.0

*-- Last updated: Oct 14,2019*

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
[{
	"id": 3,
	"title": "test3",
	"url": "https://test3",
	"cover": null,
	"main_color": null
}, {
	"id": 2,
	"title": "test2",
	"url": "https://test2",
	"cover": null,
	"main_color": null
}, {
	"id": 1,
	"title": "test1",
	"url": "https://test1",
	"cover": null,
	"main_color": null
}]
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

> categories:  Define games that need to be returned by category names, with comma separations between each category

- **request**

> /all_in_one?app_id={app_id}&app_key={app_key}&size=5
>
> /all_in_one?app_id={app_id}&app_key={app_key}&categories=Racing,Sport,Girl&size=5

- **response**

```json
{
	"Arcade": [{
		"id": 344,
		"title": "Skip The Sprint",
		"content": "Jump ahead, sprint, and score higher.",
		"url": "http://12.mosegame.com/detail?id=444",
		"cover": "https://images.quickgame.top/2019090608513194405.jpg",
		"categories": "Arcade",
		"play_count": 641844,
		"main_color": null
	}, {
		"id": 310,
		"title": "Spiny",
		"content": "Help the little hedgehog eat more food on the way home.",
		"url": "http://12.mosegame.com/detail?id=433",
		"cover": "https://images.quickgame.top/2018102411453498008.jpg",
		"categories": "Arcade",
		"play_count": 437173,
		"main_color": null
	}, {
		"id": 306,
		"title": "Tower Blocks",
		"content": "Stack the blocks one by one.",
		"url": "http://12.mosegame.com/detail?id=497",
		"cover": "https://images.quickgame.top/2019010502330153710.png",
		"categories": "Arcade",
		"play_count": 1717823,
		"main_color": null
	}],
	"Sports & Racing": [{
		"id": 348,
		"title": "Endless paper boat",
		"content": "You have a boat, you have to drive it and move forward.",
		"url": "http://12.mosegame.com/detail?id=81",
		"cover": "https://images.quickgame.top/2018102410075431719.png",
		"categories": "Sports & Racing",
		"play_count": 2191099,
		"main_color": null
	}, {
		"id": 320,
		"title": "Cars",
		"content": "Be careful not to hit other vehicles, than they get the highest score",
		"url": "http://12.mosegame.com/detail?id=365",
		"cover": "https://images.quickgame.top/2018102411304090374.png",
		"categories": "Sports & Racing",
		"play_count": 704375,
		"main_color": null
	}, {
		"id": 317,
		"title": "Crazy Freekick",
		"content": "Show your skills and get a higher score in this football game",
		"url": "http://12.mosegame.com/detail?id=286",
		"cover": "https://images.quickgame.top/2018102411123017181.jpg",
		"categories": "Sports & Racing",
		"play_count": 440138,
		"main_color": null
	}],
	"Beauty & Girl": [{
		"id": 343,
		"title": "Halloween Party",
		"content": "Happy Halloween! Now, they are busy preparing for the party. Can you help them? Help them put on Halloween makeup and then put on Halloween costumes.",
		"url": "http://12.mosegame.com/detail?id=508",
		"cover": "https://images.quickgame.top/2019082009012970505.jpeg",
		"categories": "Beauty & Girl",
		"play_count": 734063,
		"main_color": null
	}, {
		"id": 314,
		"title": "Kiss Kiss",
		"content": "Body touching, lip smacking, and body shaking! That's the moves they make when girls and boys experience such a good chemistry. Try this game to experience this passionate and lovable feeling. ",
		"url": "http://12.mosegame.com/detail?id=58",
		"cover": "https://images.quickgame.top/2018102410025440783.png",
		"categories": "Beauty & Girl",
		"play_count": 95021502,
		"main_color": null
	}, {
		"id": 292,
		"title": "Princess Cake",
		"content": "Today, the princess wants to make one of the most delicious and decorated cakes! Can you help her? First choose the right chef outfit for her, then it's time to design a cake!",
		"url": "http://12.mosegame.com/detail?id=510",
		"cover": "https://images.quickgame.top/2019030601552992379.png",
		"categories": "Beauty & Girl",
		"play_count": 823129,
		"main_color": null
	}],
	"Strategy": [{
		"id": 357,
		"title": "Clash of Vikings",
		"content": "In this tower defense war, use strategy to win this war.",
		"url": "http://12.mosegame.com/detail?id=420",
		"cover": "https://images.quickgame.top/2018102411423875669.jpg",
		"categories": "Strategy",
		"play_count": 688006,
		"main_color": null
	}, {
		"id": 350,
		"title": "Blitz Tactics",
		"content": "Attack enemy bases and don't confront heads",
		"url": "http://12.mosegame.com/detail?id=375",
		"cover": "https://images.quickgame.top/2018102411325992673.jpeg",
		"categories": "Strategy",
		"play_count": 522690,
		"main_color": null
	}, {
		"id": 294,
		"title": "Battle for Kingdom",
		"content": "Recruit more soldiers, stop enemies and destroy them",
		"url": "http://12.mosegame.com/detail?id=416",
		"cover": "https://images.quickgame.top/2019030803405515838.png",
		"categories": "Strategy",
		"play_count": 605668,
		"main_color": null
	}],
	"Puzzle & Logic": [{
		"id": 359,
		"title": "Slingshot Monster",
		"content": "Has helping the needy always been on your checklist! These Dragons caged these poor birds who are now seeking your help to escape their cages. With the Slingshot Monster you can aim and release those birds out in the free wind. Just click and aim the sling such that it hits the right cage for the birds to escape out of it. The number of birds you release the more you score! ",
		"url": "http://12.mosegame.com/detail?id=201",
		"cover": "https://images.quickgame.top/20190906084323421.png",
		"categories": "Puzzle & Logic",
		"play_count": 556677,
		"main_color": null
	}, {
		"id": 358,
		"title": "Fruita Crush",
		"content": "Collect three or more fruits to get higher scores and challenge more levels",
		"url": "http://12.mosegame.com/detail?id=388",
		"cover": "https://images.quickgame.top/2018102411354429409.jpg",
		"categories": "Puzzle & Logic",
		"play_count": 678213,
		"main_color": null
	}, {
		"id": 354,
		"title": "Pet Party Columns",
		"content": "Animals of the same colour will disappear when placed together. You can change their placements using the rotational keys, you can decide where they settle using the arrow keys and once placed together they will disappear and party. These pet party columns will make you thinking of the best possible way to keep the animals of the same colour together. ",
		"url": "http://12.mosegame.com/detail?id=266",
		"cover": "https://images.quickgame.top/2018102411080913416.jpg",
		"categories": "Puzzle & Logic",
		"play_count": 346306,
		"main_color": null
	}],
	"Adventure": [{
		"id": 356,
		"title": "Frozen Castle Adventure",
		"content": "Oh look it’s a frozen castle but, it’s not all beautiful and blissful as even the frozen castle has snow monsters. You have to jump up but, be sure not to be caught by snow monsters. These snow monsters are deadly so beware. Just jump up and be quick to escape those monsters to have a safe win. Once you reach to the top you get to the next level.",
		"url": "http://12.mosegame.com/detail?id=259",
		"cover": "https://images.quickgame.top/2018102411064269300.jpeg",
		"categories": "Adventure",
		"play_count": 419722,
		"main_color": null
	}, {
		"id": 353,
		"title": "Beautiful World",
		"content": "Let us help aliens swim in the beautiful new world.",
		"url": "http://12.mosegame.com/detail?id=350",
		"cover": "https://images.quickgame.top/201810241126239565.png",
		"categories": "Adventure",
		"play_count": 346771,
		"main_color": null
	}, {
		"id": 340,
		"title": "Fishy Rush",
		"content": "Help the fish collect more gold coins, but be careful of obstacles or you will die",
		"url": "http://12.mosegame.com/detail?id=326",
		"cover": "https://images.quickgame.top/2018102411210355570.jpg",
		"categories": "Adventure",
		"play_count": 428866,
		"main_color": null
	}],
	"Action & Risk": [{
		"id": 355,
		"title": "Exploration",
		"content": "There is a huge treasure in the depths of the earth. Go and dig it.",
		"url": "http://12.mosegame.com/detail?id=422",
		"cover": "https://images.quickgame.top/2019072308415594838.jpg",
		"categories": "Action & Risk",
		"play_count": 680114,
		"main_color": null
	}, {
		"id": 352,
		"title": "Jump With Justin",
		"content": "How does it feel up in the air, how does it feel to go against gravity and experience the space. Well, Justin can answer your questions but, for that you will have to help him jump. Justin wants to be a high jumper but, he needs you to aim and get it done. He has props in place, you just need to help him out in collecting those and jump as high as possible.",
		"url": "http://12.mosegame.com/detail?id=209",
		"cover": "https://images.quickgame.top/201810241053054666.jpg",
		"categories": "Action & Risk",
		"play_count": 348488,
		"main_color": null
	}, {
		"id": 345,
		"title": "Spacescape",
		"content": "Help our friends return home",
		"url": "http://12.mosegame.com/detail?id=406",
		"cover": "https://images.quickgame.top/2018102411393373876.jpg",
		"categories": "Action & Risk",
		"play_count": 504247,
		"main_color": null
	}],
	"Music": [{
		"id": 304,
		"title": "Snow Ball Champions",
		"content": "Snowballing is a very fun game, come join us.",
		"url": "http://12.mosegame.com/detail?id=443",
		"cover": "https://images.quickgame.top/2018102411474778529.jpeg",
		"categories": "Music",
		"play_count": 716411,
		"main_color": null
	}, {
		"id": 203,
		"title": "Bad Donut",
		"content": "Leave a good donut and throw away the bad doughnuts",
		"url": "http://12.mosegame.com/detail?id=462",
		"cover": "https://images.quickgame.top/2018102411514564950.jpg",
		"categories": "Music",
		"play_count": 552258,
		"main_color": null
	}, {
		"id": 148,
		"title": "Raster Rush",
		"content": "Bunny likes to bounce, let us help it go home soon.",
		"url": "http://12.mosegame.com/detail?id=414",
		"cover": "https://images.quickgame.top/2018102411413032002.png",
		"categories": "Music",
		"play_count": 932576,
		"main_color": null
	}]
}
```

------

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

