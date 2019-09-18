## Guide for Ume Sponsored Content Api

### Api 接口总 Url

> [https://api.eportalmobile.com/v1/sponsored/content]()

---

### 软件列表获取Api

**Method**

> GET 与 POST

 **Required(必须参数):**

```ini
app_id:       分配的app id
app_key:      分配的app key
```

**Options(可选参数):** 


```ini
language:     二位语言代码, 当前支持:en,es,de,ru,fr,pt,it 默认为en
limit:        (整型)返回的软文条数,  默认为5条
ip:           (字符串)用户请求的ip地址
ua:           (字符串)用户请求的user-agent信息
```
**request**

> https://api.eportalmobile.com/v1/sponsored/content?app_id={app_id}&app_key={app_key}&language=en&limit=3


**response**

```json
{
    "session": "v2_e8f70f3aa721ef9592ab63bf497fe16d_98f6cdb5-6665-4033-be42-011495f4dcdf-tuct3dfc56e_1558593518_1558593518_CNawjgYQqpdJGIL7ppuuLSABKAEw4QE4kaQOQIuwDkjznhdQpwZYAGAA", 
    "id": "__2f6ee5e97657763b9d7a5353e4a34bd5__2b53e08cd8f75db9873eea38d073e6cb__~~V1~~-1663167211467333076~~kbQJit9sj18VNIP4ozqBhbm3dYxuSSzNQRHblP7VNObTxvAnL2wqac4MyzR7uD46gj3kUkbS3FhelBtnsiJV6MhkDZRZzzIqDobN6rWmCPCpeEZir5b60KyDGrC7BYO4wkxMXSFq7rxqWODm3IwrVpk9EMKw34qTnd7Hk-AHUugL3AAFzxJEad_BluoQiA7U_kubDf8j_gGNG3g9CbYSig,~~V1~~6128240484488358826~~AMGoohiznPmduMHjzQvmOjxOf3iegds0wgpWKWvYw-_TxvAnL2wqac4MyzR7uD46gj3kUkbS3FhelBtnsiJV6MhkDZRZzzIqDobN6rWmCPBTgCTAKydMYiLYTeExUuY40IluLo4VDAjNB70MUQmecGxIhsk3iItHhTDhmhY25NAGDEN7nmuf84F5cWs6C38U_kubDf8j_gGNG3g9CbYSig,~~V1~~-2992653769364935375~~_9Z94HIN8iXyCRM6BdZBP1anH93uI2p0PzRDW7uyD7rTxvAnL2wqac4MyzR7uD46gj3kUkbS3FhelBtnsiJV6MhkDZRZzzIqDobN6rWmCPBREBjOAQ5PBaVdEQ5cDNJsgqN2IXLojsSxhiWmmWV7T1SrMBmtrKRSG3Bi0oJyWNC6prIeg4J4FTQEdJCJA5YLUw8YFpDWAGvCz6I2-dsmDw__photo,photo,photo", 
    "ui": "rest-api", 
    "list": [
        {
            "thumbnail": [
                {
                    "url": "http://images.taboola.com/taboola/image/fetch/f_jpg%2Cq_auto%2Cc_fill%2Cg_faces:auto%2Ce_sharpen/https%3A%2F%2Fs3.amazonaws.com%2Fwp-images-bucket%2Fyael%2Flgbt%2Bcouples%2Flgbt%2Bcouples21_1000x600.jpg", 
                    "width": "1000", 
                    "height": "600"
                }
            ], 
            "type": "photo", 
            "name": "LGBT Celebs Who Are Couples", 
            "created": "Wed, 20 Feb 2019 12:23:20 UTC", 
            "branding": "DomesticatedCompanion", 
            "duration": "0", 
            "categories": [
                "entertainment"
            ], 
            "views": "0", 
            "id": "~~V1~~-1663167211467333076~~kbQJit9sj18VNIP4ozqBhbm3dYxuSSzNQRHblP7VNObTxvAnL2wqac4MyzR7uD46gj3kUkbS3FhelBtnsiJV6MhkDZRZzzIqDobN6rWmCPCpeEZir5b60KyDGrC7BYO4wkxMXSFq7rxqWODm3IwrVpk9EMKw34qTnd7Hk-AHUugL3AAFzxJEad_BluoQiA7U_kubDf8j_gGNG3g9CbYSig", 
            "origin": "sponsored", 
            "url": "http://api.taboola.com/1.2/json/ume-technologies-eportal-sc-zte/recommendations.notify-click?app.type=mobile&app.apikey=6ee11ccf9b5ad86b42469fe62d5fce0f59481f02&response.id=__2f6ee5e97657763b9d7a5353e4a34bd5__2b53e08cd8f75db9873eea38d073e6cb&response.session=v2_e8f70f3aa721ef9592ab63bf497fe16d_98f6cdb5-6665-4033-be42-011495f4dcdf-tuct3dfc56e_1558593518_1558593518_CNawjgYQqpdJGIL7ppuuLSABKAEw4QE4kaQOQIuwDkjznhdQpwZYAGAA&item.id=%7E%7EV1%7E%7E-1663167211467333076%7E%7EkbQJit9sj18VNIP4ozqBhbm3dYxuSSzNQRHblP7VNObTxvAnL2wqac4MyzR7uD46gj3kUkbS3FhelBtnsiJV6MhkDZRZzzIqDobN6rWmCPCpeEZir5b60KyDGrC7BYO4wkxMXSFq7rxqWODm3IwrVpk9EMKw34qTnd7Hk-AHUugL3AAFzxJEad_BluoQiA7U_kubDf8j_gGNG3g9CbYSig&item.type=photo&sig=05f5be5457624c37557934df002afd48327eaf241ef4&redir=https%3A%2F%2Fwww.domesticatedcompanion.com%2Flove-is-in-the-air-the-partners-of-famous-lgbt-entertainers%2F%3Futm_source%3D198%26utm_medium%3Dtaboola%26utm_term%3Dume-technologies-eportal-sc-zte%26utm_content%3DLGBT%2BCelebs%2BWho%2BAre%2BCouples%26utm_campaign%3D201902201222491x0xdefault_1896188"
        }, 
        {
            "thumbnail": [
                {
                    "url": "http://images.taboola.com/taboola/image/fetch/f_jpg%2Cq_auto%2Cc_fill%2Cg_faces:auto%2Ce_sharpen/http%3A%2F%2Fcdn.taboola.com%2Flibtrc%2Fstatic%2Fthumbnails%2Fb95c6779a06bff42dfeff74bc1baa3a1.png", 
                    "width": "400", 
                    "height": "262"
                }
            ], 
            "description": "Animals never cease to entertain us with their antics. They certainly have a way about them. One could argue that animal pictures are taking over the internet. Just take these twenty animals for example. Why wouldn’t they go viral? Advertisement", 
            "type": "photo", 
            "name": "Hilarious Animals Pics Proving That If It Fits I Sit", 
            "created": "Wed, 14 Mar 2018 20:27:11 UTC", 
            "branding": "daowl.com", 
            "duration": "0", 
            "categories": [
                "pets"
            ], 
            "views": "0", 
            "id": "~~V1~~6128240484488358826~~AMGoohiznPmduMHjzQvmOjxOf3iegds0wgpWKWvYw-_TxvAnL2wqac4MyzR7uD46gj3kUkbS3FhelBtnsiJV6MhkDZRZzzIqDobN6rWmCPBTgCTAKydMYiLYTeExUuY40IluLo4VDAjNB70MUQmecGxIhsk3iItHhTDhmhY25NAGDEN7nmuf84F5cWs6C38U_kubDf8j_gGNG3g9CbYSig", 
            "origin": "sponsored", 
            "url": "http://api.taboola.com/1.2/json/ume-technologies-eportal-sc-zte/recommendations.notify-click?app.type=mobile&app.apikey=6ee11ccf9b5ad86b42469fe62d5fce0f59481f02&response.id=__2f6ee5e97657763b9d7a5353e4a34bd5__2b53e08cd8f75db9873eea38d073e6cb&response.session=v2_e8f70f3aa721ef9592ab63bf497fe16d_98f6cdb5-6665-4033-be42-011495f4dcdf-tuct3dfc56e_1558593518_1558593518_CNawjgYQqpdJGIL7ppuuLSABKAEw4QE4kaQOQIuwDkjznhdQpwZYAGAA&item.id=%7E%7EV1%7E%7E6128240484488358826%7E%7EAMGoohiznPmduMHjzQvmOjxOf3iegds0wgpWKWvYw-_TxvAnL2wqac4MyzR7uD46gj3kUkbS3FhelBtnsiJV6MhkDZRZzzIqDobN6rWmCPBTgCTAKydMYiLYTeExUuY40IluLo4VDAjNB70MUQmecGxIhsk3iItHhTDhmhY25NAGDEN7nmuf84F5cWs6C38U_kubDf8j_gGNG3g9CbYSig&item.type=photo&sig=cfc9ec87a94e8aba6991e6493bb9d699ae3f6406bff5&redir=https%3A%2F%2Fdaowl.com%2F20-animals-proving-if-i-fits-i-sits%2F%3Futm_source%3Dtaboola%26utm_medium%3Dreferral%26utm_content%3DHilarious%2BAnimals%2BPics%2BProving%2BThat%2BIf%2BIt%2BFits%2BI%2BSit%2Bhttp%253A%252F%252Fcdn.taboola.com%252Flibtrc%252Fstatic%252Fthumbnails%252Fb95c6779a06bff42dfeff74bc1baa3a1.png%26utm_term%3Dume-technologies-eportal-sc-zte%26utm_campaign%3DDogisitT1"
        }, 
        {
            "thumbnail": [
                {
                    "url": "http://images.taboola.com/taboola/image/fetch/f_jpg%2Cq_auto%2Cc_fill%2Cg_faces:auto%2Ce_sharpen/https%3A%2F%2Fnew.viral80.site%2Fwp-content%2Fuploads%2F2019%2F02%2Fimage-1.jpg", 
                    "width": "1024", 
                    "height": "558"
                }
            ], 
            "type": "photo", 
            "name": "Top 10 Street Food You Have To Try In Germany!", 
            "created": "Thu, 14 Feb 2019 14:34:24 UTC", 
            "branding": "News FinanceFiasta", 
            "duration": "0", 
            "categories": [
                "entertainment"
            ], 
            "views": "0", 
            "id": "~~V1~~-2992653769364935375~~_9Z94HIN8iXyCRM6BdZBP1anH93uI2p0PzRDW7uyD7rTxvAnL2wqac4MyzR7uD46gj3kUkbS3FhelBtnsiJV6MhkDZRZzzIqDobN6rWmCPBREBjOAQ5PBaVdEQ5cDNJsgqN2IXLojsSxhiWmmWV7T1SrMBmtrKRSG3Bi0oJyWNC6prIeg4J4FTQEdJCJA5YLUw8YFpDWAGvCz6I2-dsmDw", 
            "origin": "sponsored", 
            "url": "http://api.taboola.com/1.2/json/ume-technologies-eportal-sc-zte/recommendations.notify-click?app.type=mobile&app.apikey=6ee11ccf9b5ad86b42469fe62d5fce0f59481f02&response.id=__2f6ee5e97657763b9d7a5353e4a34bd5__2b53e08cd8f75db9873eea38d073e6cb&response.session=v2_e8f70f3aa721ef9592ab63bf497fe16d_98f6cdb5-6665-4033-be42-011495f4dcdf-tuct3dfc56e_1558593518_1558593518_CNawjgYQqpdJGIL7ppuuLSABKAEw4QE4kaQOQIuwDkjznhdQpwZYAGAA&item.id=%7E%7EV1%7E%7E-2992653769364935375%7E%7E_9Z94HIN8iXyCRM6BdZBP1anH93uI2p0PzRDW7uyD7rTxvAnL2wqac4MyzR7uD46gj3kUkbS3FhelBtnsiJV6MhkDZRZzzIqDobN6rWmCPBREBjOAQ5PBaVdEQ5cDNJsgqN2IXLojsSxhiWmmWV7T1SrMBmtrKRSG3Bi0oJyWNC6prIeg4J4FTQEdJCJA5YLUw8YFpDWAGvCz6I2-dsmDw&item.type=photo&sig=893d5058d340a8491b3c6a5187838b64e3ce15738588&redir=https%3A%2F%2Fnew.viral80.site%2Ftop-10-street-food-you-have-to-try-in-germany%2F%3Futm_source%3Dtaboola%26utm_medium%3Dreferral"
        }
    ]
}
```

---

### Error Status Codes(错误代码)

| **Error Code** | **Error Msg**        |
| -------------- | -------------------- |
| 10001          | Illegal request      |
| 10002          | Unauthorized request |

 **For example:**

```json
{
	"error_code": 10002,
	"error_msg": "Unauthorized request"
}
```