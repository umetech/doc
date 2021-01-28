# 书签云存储服务

*-- Last updated: Jan 26,2021*

## 1. 书签上传

### POST：

> https://nextword.me/v1/cloud/storage/bookmark/push?token={token}

### BODY: (form-data)

> file: {your-upload-bookmark-file}

### Response

```json
{
    "status": "success",
    "url": "https://nextword.me/i/bookmark/{token}/202101260326193914.html"
}
```

## 2. 书签拉取

### GET：

> https://nextword.me/v1/cloud/storage/bookmark/pull?token={token}

### Response

```json
{
  "url": "https://nextword.me/i/bookmark/{token}/202101260322459605.html",
  "size": 359,
  "time": 1611631365,
  "md5": "c2638d7dfac18615898db3194ea400f3"
}
```



## Error


```json
{
    "error": "The 'token' parameter is invalid."
}
```

