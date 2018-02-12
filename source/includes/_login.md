# Login

If you've been referred here from the <a href="#authentication">Authentication</a> section, please note that you will need your `API Key` to continue!

<aside class="notice">Remember, you can get your <code>API key</code> when you login to your Admin Dashboard!</aside>

## Perform User Login

```java
```

```python
```

```shell
curl -i -H "Accept: application/json" -H "Content-Type: application/json" -X POST http://gametize.com/api2/login.json?api_key=********************************&email=someone@somedomain.com&password=********
```

```javascript
```

>The above code returns JSON structured like this:

```json
{
    "gameId": *,
    "code": 200,
    "sessionKey": "*-********-****-****-****-************",
    "firstLogin": false,
    "newRegistration": false,
    "language": "en",
    "userId": *,
    "user": {
        "country": "UNKNOWN",
        "photoLarge": "http://somedomain/images/playeravatarlarge.png",
        "photoSmall": "http://somedomain/images/playeravatarsmall.png",
        "name": "firstName lastName",
        "id": *
    }
}
```

This endpoint **logs a user** in using email and password.

<aside class="success">Register your users on <a href="https://gametize.com/">gametize.com/</a>, or using the <a href="#register-user">user registration</a> API call in your application!</aside>

### HTTP Request
`POST https://gametize.com/api2/login.json`

<aside class="notice">Note that this is not a HTTP <code>GET</code> request like previous API calls, but a HTTP <code>POST</code>request!</aside>

### Parameter(s)
Name | Usage | Default | Example | Description
---|---|---|---|---
api_key | **required** | null | 207302fde5e7-097a-4971-a4d4-de7154113ed7 | Validates the identity of the API client.
email | **required** | null | someone@somedomain.com | The email address of the user.
password | **required** | null | qwRtys57! | The password of the user. 
device_token | optional | null | asjh8712871D7812jJ | The token of an iOS device - *required for Push Notifications*.

<aside class="success">It is recommended to store user <code>session_key</code> in the API client’s system. Not only is the <code>session_key</code> required for most API requests, storing the <code>session_key</code> will make subsequent API login requests unnecessary as the <code>session_key</code> represents the validated user identity.</aside>
