## Guide for Ume Smart Links Version 1.0

### Api Portal 

> https://api.eportalmobile.com/v1/smartlinks

------

### Smart Links Api

**Method:**

> GET / POST

 **Required:**

```ini
app_id:       (string) app id
app_key:      (string) app key
```

**Optionals:** 

```ini
language:     (string) two language code, supported:en,es,de,ru,fr,pt,it,etc. default is en
ip:           (string) IP address requested by user
ua:           (string) User-Agent information requested by user
```

- **request**

> ?app_id={app_id}&app_key={app_key}&language=en
>
> ?app_id={app_id}&app_key={app_key}&language=fr

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

