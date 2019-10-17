# Guide for App Feedback Api Version 1.0

*-- Last updated: Oct 17,2019*

## Api Portal

> https://api.eportalmobile.com/v1/app_feedback

---

## Post Commet

**Method:**

> Only Support POST

**Required:**

```ini
package_name:   (string) Package name of App
content:        (string) Content of user posted comments
stars:          (int) Number of user posted stars
```

- **request**

> /post

**Example**

Data of post

```ini
package_name: com.ume.browser.international
content: good
stars: 3
```

- **response**

```json
{
	"code": 0,
	"msg": "Success"
}
```

---

## Status Codes

| **Code** | **Msg**         |
| -------- | --------------- |
| 0        | Success         |
| 10001    | Illegal request |
| 10009    | Too many times  |

- **e.g.**

```json
{
	"code": 10001,
	"msg": "Illegal request"
}
```

