# 数据同步结构及举例说明



## 前言

- 所有同步数据采用 POST base64(JSON) 格式传输, 除非携带debug=true参数
- Client POST数据与服务端Response回传数据结构格式一致
- Client 获取Response回传数据后，需要依据flag的值进行更新，删除等操作，操作成功之后，将flag置为0
- data节点里面的数据，不同业务节点不一样，有部分数据不用传输，比如：
> 1. type为word时，`lexicals` 节点可以省略
> 2. type为text时，`translation` 节点可以省略



## 单词翻译同步

### API接口

> https://user.wordlypro.com/sync/word?app_id=xxxxx&debug=true

### 数据结构

```json
{
	"token": "xxxx",
	"type": "word",
	"timestamp": 21321312321,
	"list": [{
			"cid": 3223234,
			"id": 5322432,
			"flag": 1,
			"version": 34,
			"updated_at": 1634234263,
			"data": [{
				"album": "xxx",
				"from": "en",
				"to": "zh",
				"name": "shoe",
        "usage": "xxx",
        "url": "xxx",
        "timestamp": 164000000,
				"lexicals": [{
					"category": "Nouns",
					"definitions": ["xxx", "yyy"],
					"examples": ["xxx", "yyy"]
				}]
			}]
		},
		{
			"cid": 3213213,
			"id": 1234567,
			"flag": 4,
			"version": 100,
			"updated_at": 1634234323,
			"data": [{
				"album": "xxx",
				"from": "en",
				"to": "zh",
				"name": "book",
        "usage": "xxx",
        "url": "xxx",
        "timestamp": 164000000,
				"lexicals": [{
						"category": "Nouns",
						"definitions": ["xxx", "yyy"],
						"examples": ["xxx", "yyy"]
					},
					{
						"category": "Verbs",
						"definitions": ["xxx", "yyy"],
						"examples": ["xxx", "yyy"]
					}
				]
			}]
		}
	]
}
```

**说明**

- app_id:  由服务端统一分配一个固定值，以区分POST数据来源

> Chrome插件： wordly_extension
> 取词器： wordly_screen
> 翻译浏览器：wordly_browser

- debug: 当为true时，POST与Response回传的数据将采用明文方式，不会进行Base64的加密

- cid: 由Client端创建, 服务端仅做双向透传

- id:  服务端创建值 (Client新建时默认为0)

- flag: 由Client端与服务端共同控制值 (取值 0:normal/synced  1:create  2:update   4:delete)

- version：服务端控制值 (Client新建时默认为0)

- updated_at: POST时为Client记录的十位时间戳

- data：为payload数据，不同类型，数据节点不一样，其中lexicals节点可以不POST

- data.timestamp：为Client端的十位时间戳，服务端不做任何处理，原样返回

  

## 文本翻译同步

### API接口

> https://user.wordlypro.com/sync/text?app_id=xxxxx&debug=true

### 数据结构

```json
{
	"token": "xxxx",
	"type": "text",
	"timestamp": 21321312321,
	"list": [{
			"cid": 3213213,
			"id": 5322432,
			"flag": 1,
			"version": 34,
			"updated_at": 1634234263,
			"data": [{
        "timestamp": 164000000,
				"from": "en",
				"to": "zh",
				"text": "hello,world",
				"translation": "你好，世界"
			}]
		},
		{
			"cid": 3213213,
			"id": 7463432,
			"flag": 4,
			"version": 15,
			"updated_at": 1634234263,
			"data": [{
        "timestamp": 164000000,
				"from": "en",
				"to": "zh",
				"text": "How old are you?",
				"translation": "你多大了？"
			}]
		}
	]
}
```

**说明**

- data：为payload数据，不同类型，数据节点不一样，其中translation节点可以不POST

## 书签数据同步

### API接口

> https://user.wordlypro.com/sync/bookmark?app_id=xxxxx&debug=true

### 数据结构

```json
{
	"token": "xxxx",
	"type": "bookmark",
	"timestamp": 21321312321,
	"list": [{
			"cid": 3213213,
			"id": 5322432,
			"flag": 1,
			"version": 34,
			"updated_at": 1634234263,
			"data": [{
        "timestamp": 164000000,
        "parent": null,
				"folder": "xxx",
				"name": "百度",
				"url": "https://baidu.com"
			}]
		},
		{
			"cid": 3213213,
			"id": 7463432,
			"flag": 4,
			"version": 15,
			"updated_at": 1634234263,
			"data": [{
        "timestamp": 164000000,
        "parent":"xxx",
				"folder": "xxx",
				"name": "新浪",
				"url": "https://sina.com"
			}]
		}
	]
}
```

- data：为payload数据，书签同步时，data里节点不可省略

## 同步过程

1. Client向服务端POST flag的非0数据A；
2. 服务端除重，更新，删除，合并，过滤等操作之后返回数据B, B数据中带有id与flag不同参数；
3. Client获取到数据B，根据id与flag进行相应的数据更新与合并操作，操作完成之后，将flag置为0，同步过程完成；

## 数据同步举例

这里以文本翻译（type=text）的数据同步来进行举例，其它单词翻译（type=word）与书签数据（type=bookmark）同步功能完成一致

#### POST URL

> https://user.wordlypro.com/sync/text?app_id=wordly_screen&debug=true

### 1. 初始化同步

> 初始化同步数据常用在初次安装应用、应用还原、应用被清理重置后需要进行初始化同步；初始化同步数据会从服务端拉出所有数据，请谨慎使用。

#### POST JOSN

```json
{
  "token": "fb37c8c03635406ebd2a2bb10ef01aee.1608260620.1",
  "type": "text",
  "timestamp": 0,
  "list": []
}
```

- 初始化同步，以timestamp为0做为判断条件，当POST JSON中的timestamp为0时，服务端会直接返回所有数据

#### Response Result

```json
{
    "size": 3,
    "token": "fb37c8c03635406ebd2a2bb10ef01aee.1608260620.1",
    "type": "text",
    "timestamp": 1608261650,
    "list": [
        {
            "origin": "wordly_extension",
            "cid": 1,
            "id": 1000001,
            "flag": 1,
            "version": 1,
            "data": [
                {
                  	"timestamp": 164000000,
                    "from": "en",
                    "to": "zh",
                    "text": "How are you?",
                    "translation": "你好吗？"
                }
            ],
            "updated_at": 1608261650
        },
        {
            "origin": "wordly_screen",
            "cid": 1,
            "id": 1000003,
            "flag": 1,
            "version": 1,
            "data": [
                {
                  	"timestamp": 164000000,
                    "from": "en",
                    "to": "zh",
                    "text": "hello,world",
                    "translation": "你好，世界"
                }
            ],
            "updated_at": 1608261650
        },
        {
            "origin": "wordly_extension",
            "cid": 2,
            "id": 1000002,
            "flag": 4,
            "version": 5,
            "data": [
                {
                  	"timestamp": 164000000,
                    "from": "en",
                    "to": "zh",
                    "text": "Nice to meet you.",
                    "translation": "见到你很高兴."
                }
            ],
            "updated_at": 1608261650
        }
    ]
}
```

-  返回的主节点中的 timestamp=1608261650, 需要应用保存好，下次发起数据同步时，需要使用

### 2. 数据同步

> 当应用有新增、更新名删除操作时，发起数据同步

#### POST JOSN

```json
{
  "token": "fb37c8c03635406ebd2a2bb10ef01aee.1608260620.1",
  "type": "text",
  "timestamp": 1608261650,
  "list": [{
    "cid": 1,
    "id": 0,
    "flag": 1,
    "version": 0,
    "updated_at": 0,
    "data": [{
      "timestamp": 164000000,
      "from": "en",
      "to": "zh",
      "text": "hello,world",
      "translation": "你好，世界"
    }]
  },
    {
      "cid": 2,
      "id": 1000002,
      "flag": 4,
      "version": 0,
      "updated_at": 0,
      "data": [{
        "timestamp": 164000000,
        "from": "en",
        "to": "zh",
        "text": "How old are you?",
        "translation": "你多大了呢？"
      }]
    }
  ]
}
```

- 数据同步，timestamp为应用保存的最新同步时间戳（记住，这个值不能为0，为0表示初始化同步）
- POST的数据中，flag=1表示新增的数据，flag=4表示删除的数据

#### Response Result

```json
{
    "size": 2,
    "token": "fb37c8c03635406ebd2a2bb10ef01aee.1608260620.1",
    "type": "text",
    "timestamp": 1608261641,
    "list": [
        {
            "origin": "wordly_screen",
            "cid": 2,
            "id": 1000002,
            "flag": 0,
            "version": 1,
            "data": [
                {
                    "timestamp": 164000000,
                    "from": "en",
                    "to": "zh",
                    "text": "How old are you?",
                    "translation": "你多大了呢？"
                }
            ],
            "updated_at": 1608261641
        },
        {
            "origin": "wordly_extension",
            "cid": 2,
            "id": 1000002,
            "flag": 4,
            "version": 5,
            "data": [
                {
                    "timestamp": 164000000,
                    "from": "en",
                    "to": "zh",
                    "text": "Nice to meet you.",
                    "translation": "见到你很高兴."
                }
            ],
            "updated_at": 1608261641
        }
    ]
}
```

- 服务端返回的主节点 timestamp=1608261641，应用应该保存起来，作为下次同步的主timestamp；
- POST服务端返回的数据中，id以及version都会进行更新，同时会提供数据创建的来源origin
- flag为0表示服务器已经同步新增成功完成，应用需要将本地的记录中的flag设置为0
- flag为4表示服务器已经同步删除成功完成，应用可以删除本地数据了

### 3. 空同步

> 应用发起同步时，必须是flag!=0的数据，当本地的所有数据flag都为0时，应用也可以发起同步操作，此是发起的空同步请求，往往是同步其它应用上新增、更新或删除的数据

#### POST JSON

```json
{
  "token": "fb37c8c03635406ebd2a2bb10ef01aee.1608260620.1",
  "type": "text",
  "timestamp": 1608261641,
  "list": []
}
```

- 空同步，其中的timestamp=1608261641为最新应用同步获取的服务器timestamp

- 空同步因为应用flag都为0，所以list节点数据为空，所以叫做空同步

#### Response Result

（1）如果服务器上无其它应用同步的数据，将会返回一个空数据结果集

```json
{
    "size": 0,
    "token": "fb37c8c03635406ebd2a2bb10ef01aee.0.1",
    "type": "text",
    "timestamp": 1608260184,
    "list": []
}
```

(2) 如果有其它应用同步过了数据，将会返回一个有数据的结果集, 比如：

```json
{
    "size": 2,
    "token": "fb37c8c03635406ebd2a2bb10ef01aee.1608260620.1",
    "type": "text",
    "timestamp": 1608270490,
    "list": [
        {
            "origin": "wordly_extension",
            "cid": 1,
            "id": 1000001,
            "flag": 1,
            "version": 1,
            "data": [
                {
                    "timestamp": 164000000,
                    "from": "en",
                    "to": "zh",
                    "text": "How are you?",
                    "translation": "你好吗？"
                }
            ],
            "updated_at": 1608270490
        },
        {
            "origin": "wordly_extension",
            "cid": 2,
            "id": 1000002,
            "flag": 4,
            "version": 6,
            "data": [
                {
                    "timestamp": 164000000,
                    "from": "en",
                    "to": "zh",
                    "text": "Nice to meet you.",
                    "translation": "见到你很高兴."
                }
            ],
            "updated_at": 1608270490
        }
    ]
}
```

