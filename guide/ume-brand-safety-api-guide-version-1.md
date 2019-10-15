# Guide for Ume Brand Safety Api Version 1.0

*-- Last updated: Oct 15,2019*

## Api Portal 

> https://search.eportalmobile.com/v1/keyword

------

## Detecting Brand Safety

**Method:**

> GET / POST

 **Required:**

```ini
q:      (string) keyword for search
```

### example 1

- **request**

> /detect?q=shoe

- **response**

```json
{"brand_safety":true}
```

### example 2

- **request**

> /detect?q=xnxx

- **response**

```json
{"brand_safety":false}
```
------

## List Brand Resource for Search

**Method:**

> GET / POST

 **Required:**

```ini
q:      (string) keyword for search
```

**Optionals:** 

```ini
limit:	(int) the number of brand resources returned, default is 10
```

- **request**

> /list?q=xnxx&limit=5
>

- **response**

```json
[{
	"id": 13087,
	"keyword": "xnxx",
	"provider": 2,
	"title": "Xnxx",
	"url": "https://www.xnxx.com/",
	"description": "XNXX delivers free sex movies and fast free porn videos (tube porn). Now 10 million+ sex vids available for free! Featuring hot pussy, sexy girls in xxx rated porn ...",
	"host": "www.xnxx.com",
	"domain": "xnxx.com",
	"category": "Pornography"
}, {
	"id": 13088,
	"keyword": "xnxx",
	"provider": 2,
	"title": "XNXX - Free XNXX Porn Movies - XNXX Videos - Sex Loving",
	"url": "https://www.sexloving.net/xnxx/",
	"description": "XNXX Porn Awesome. ... BRAZZERS / Pornhub / Redtube / XNXX / Xvideos / Youporn. ... BRAZZERS / British / Hardcore / HD / Lesbian / Pornhub / Redtube / Russian / Teen / XNXX / Xvideos / Youporn.",
	"host": "www.sexloving.net",
	"domain": "sexloving.net",
	"category": "Pornography"
}, {
	"id": 13089,
	"keyword": "xnxx",
	"provider": 2,
	"title": "xnxx videos - XVIDEOS.COM",
	"url": "https://www.xvideos.com/tags/xnxx",
	"description": "XVIDEOS xnxx videos, free. ... vlc-record-2016-03-26-06h37m58s-Old Couple Hooks Up Online For Sex - XNXX.COM.flv-. 44 secMtotowamwas - 459.3k Views -.",
	"host": "www.xvideos.com",
	"domain": "xvideos.com",
	"category": "Pornography"
}, {
	"id": 13090,
	"keyword": "xnxx",
	"provider": 2,
	"title": "XNXX Full HD | New XNXX.COM xxx sex video 3gp 2019 - porn",
	"url": "https://xbombo.com/video_tag/bb-xnxx-hd/",
	"description": "The best XNXX’s porn videos. ... The newest HD XXX videos from Xnxx.com. We offer to you the best porn videos and newest hd xxx Adult Movies from xnxx com, many genres so you can choose the one that fits better your fantasies.",
	"host": "xbombo.com",
	"domain": "xbombo.com",
	"category": "Pornography"
}, {
	"id": 13091,
	"keyword": "xnxx",
	"provider": 2,
	"title": "XNXX Videos Porno Gratis",
	"url": "https://xnxx.porno333.com/",
	"description": "Xvideos Porno! Estrellas porn XXX de grandes tetas y deliciosos culos redondos enexcitantes y recientes vídeos porno de XNXX.com, disponibles gratis, ...",
	"host": "xnxx.porno333.com",
	"domain": "porno333.com",
	"category": "Pornography"
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

