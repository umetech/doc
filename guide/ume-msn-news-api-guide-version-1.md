# Guide for Ume MSN News Api Version 1.0

## Supported Locales

```json
"de_DE", "ar_AR", "hi_IN", "ru_RU", "vi_VN", "th_TH", "pt_PT", "en_US", "id_ID", "fr_FR", "es_ES"
```

##  News Categories

```json
[ {
  "id" : 10001,
  "name" : "Top News"
}, {
  "id" : 10002,
  "name" : "Sports"
}, {
  "id" : 10003,
  "name" : "Lifestyle"
}, {
  "id" : 10004,
  "name" : "Finance"
}, {
  "id" : 10005,
  "name" : "Entertainment"
}, {
  "id" : 10006,
  "name" : "Health"
}, {
  "id" : 10007,
  "name" : "Dining"
}, {
  "id" : 10008,
  "name" : "Weather"
}, {
  "id" : 10009,
  "name" : "Travel"
}, {
  "id" : 10010,
  "name" : "Autos"
}, {
  "id" : 10011,
  "name" : "Video"
} ]
```

## Fetch News List

### Api Url

> https://api.eportalmobile.com/v1/msn/news/list

------

### News List

**Method:**

> GET / POST

 **Required:**

```ini
app_id:       (string) app id
app_key:      (string) app key
category_id:  (int) news category id
```

**Optionals:** 

```ini
country:      (string) two uppercase country codes, e.g. US, DE, MX. default is US
language:     (string) two language code, e.g. en,es,de,ru,fr,it. default is en
limit:	      (int) the number of news returned, default is 20
offset:	      (int) the number of offsets in news lists, default is 0
uid:          (string) user id, may be device id or UUID
ip:           (string) IP address requested by user
ua:           (string) User-Agent information requested by user
```

- **request**

> ?app_id={app_id}&app_key={app_key}&category_id=10001&country=US&language=en&limit=5&offset=0

- **response**

```json
{
  "country" : "US",
  "language" : "en",
  "list" : [ {
    "id" : 9742,
    "title" : "Trump looking for 11th-hour reset but mostly shuns debate prep",
    "description" : "",
    "url" : "https://api.airfind.com/stats/adrequest/v1?clientid=50012&type=click&adCampaign=msnNewsArticle-newspolitics&provider=msn&redirectURL=https%3A%2F%2Fwww.msn.com%2Fen-us%2Fnews%2Fpolitics%2Ftrump-looking-for-11th-hour-reset-but-mostly-shuns-debate-prep%2Far-BB19vUDQ%3Focid%3Daf-demo",
    "thumbnail" : "https://img-s-msn-com.akamaized.net/tenant/amp/entityid/BB19vhDf.img?w=150&h=150",
    "images" : "https://img-s-msn-com.akamaized.net/tenant/amp/entityid/BB19vhDf.img?w=750&h=750",
    "source" : "CNN",
    "category_id" : 10001,
    "hit_count" : 0,
    "published_at" : "2020-09-29 01:37:02"
  }, {
    "id" : 9741,
    "title" : "Calm before the storm? Racing braces for virus impact on sales",
    "description" : "",
    "url" : "https://api.airfind.com/stats/adrequest/v1?clientid=50012&type=click&adCampaign=msnNewsArticle-newsworld&provider=msn&redirectURL=https%3A%2F%2Fwww.msn.com%2Fen-us%2Fnews%2Fworld%2Fcalm-before-the-storm-racing-braces-for-virus-impact-on-sales%2Far-BB19w5kg%3Focid%3Daf-demo",
    "thumbnail" : "https://img-s-msn-com.akamaized.net/tenant/amp/entityid/BB19w9gR.img?w=150&h=150",
    "images" : "https://img-s-msn-com.akamaized.net/tenant/amp/entityid/BB19w9gR.img?w=750&h=750",
    "source" : "AFP",
    "category_id" : 10001,
    "hit_count" : 0,
    "published_at" : "2020-09-29 01:37:14"
  }, {
    "id" : 9740,
    "title" : "Barrett tied to faith group ex-members say subjugates women",
    "description" : "",
    "url" : "https://api.airfind.com/stats/adrequest/v1?clientid=50012&type=click&adCampaign=msnNewsArticle-newsus&provider=msn&redirectURL=https%3A%2F%2Fwww.msn.com%2Fen-us%2Fnews%2Fus%2Fbarrett-tied-to-faith-group-ex-members-say-subjugates-women%2Far-BB19w6s3%3Focid%3Daf-demo",
    "thumbnail" : "https://img-s-msn-com.akamaized.net/tenant/amp/entityid/BB19w9gB.img?w=150&h=150",
    "images" : "https://img-s-msn-com.akamaized.net/tenant/amp/entityid/BB19w9gB.img?w=750&h=750",
    "source" : "Associated Press",
    "category_id" : 10001,
    "hit_count" : 0,
    "published_at" : "2020-09-29 01:41:31"
  }, {
    "id" : 9739,
    "title" : "How Barrett and the Court Fight Are Influencing Swing Voters",
    "description" : "",
    "url" : "https://api.airfind.com/stats/adrequest/v1?clientid=50012&type=click&adCampaign=msnNewsArticle-newspolitics&provider=msn&redirectURL=https%3A%2F%2Fwww.msn.com%2Fen-us%2Fnews%2Fpolitics%2Fhow-barrett-and-the-court-fight-are-influencing-swing-voters%2Far-BB19vNnb%3Focid%3Daf-demo",
    "thumbnail" : "https://img-s-msn-com.akamaized.net/tenant/amp/entityid/BB19vYF7.img?w=150&h=150",
    "images" : "https://img-s-msn-com.akamaized.net/tenant/amp/entityid/BB19vYF7.img?w=750&h=750",
    "source" : "The New York Times",
    "category_id" : 10001,
    "hit_count" : 0,
    "published_at" : "2020-09-29 01:43:00"
  }, {
    "id" : 9738,
    "title" : "Trump Deflects Questions About Taxes, but First Debate Has a New Issue",
    "description" : "",
    "url" : "https://api.airfind.com/stats/adrequest/v1?clientid=50012&type=click&adCampaign=msnNewsArticle-newspolitics&provider=msn&redirectURL=https%3A%2F%2Fwww.msn.com%2Fen-us%2Fnews%2Fpolitics%2Ftrump-deflects-questions-about-taxes-but-first-debate-has-a-new-issue%2Far-BB19vQ97%3Focid%3Daf-demo",
    "thumbnail" : "https://img-s-msn-com.akamaized.net/tenant/amp/entityid/BB19vSeA.img?w=150&h=150",
    "images" : "https://img-s-msn-com.akamaized.net/tenant/amp/entityid/BB19vSeA.img?w=750&h=750",
    "source" : "The New York Times",
    "category_id" : 10001,
    "hit_count" : 0,
    "published_at" : "2020-09-29 01:45:00"
  } ]
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

