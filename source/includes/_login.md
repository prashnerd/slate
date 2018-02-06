# Login

If you've been referred here from the <a href="#authentication">Authentication</a> section, please note that you will need your `API Key` to continue!

<aside class="notice">Remember, you can get your <code>API key</code> when you login to your Admin Dashboard!</aside>

## Perform User Login

```java
```

```python
```

```shell
```

```javascript
```

>The above code returns JSON structured like this:

```json
```

This endpoint **logs a user** in using email and password - *registration needs to be done on <a href="https://gametize.com/">gametize.com</a>*. 

### HTTP Request
`POST https://yourdomain/api2/login.json`

<aside class="notice">Note that this is not a HTTP <code>GET</code> request like previous API calls, but a HTTP <code>POST</code>request!</aside>

### Parameter(s)
Name | Usage | Default | Example | Description
---|---|---|---|---
api_key | **required** | null | 207302fde5e7-097a-4971-a4d4-de7154113ed7 | Validates the identity of the API client.
email | **required** | null | someone@gametize.com | The email address of the user.
password | **required** | null | qwRtys57! | The password of the user. 
device_token | optional | null | asjh8712871D7812jJ | The token of an iOS device - *required for Push Notifications*.

<aside class="success">It is recommended to store user <code>session_key</code> in the API client’s system. Not only is the <code>session_key</code> required for most API requests, storing the <code>session_key</code> will make subsequent API login requests unnecessary as the <code>session_key</code> represents the validated user identity.</aside>

## Fetch User Session Key

```java
```

```python
```

```shell
```

```javascript
```

>The above code returns JSON structured like this:

```json
```

This endpoint performs the same action as (Perform User Login[#perform-user-login], but is meant to be used only to retrieve the stored `session-key`. 

<aside class="success">This API call is recommended for API clients!</aside>

### HTTP Request
`POST https://yourdomain/api2/login/session.json`

### Parameter(s)
Name | Usage | Default | Example | Description
---|---|---|---|---
api_key | **required** | null | 207302fde5e7-097a-4971-a4d4-de7154113ed7 | Validates the identity of the API client.
email | **required** | null | someone@gametize.com | The email address of the user.
user_name | **required** | null | SomeoneCool | The name of new user (Used only if user is new).
fb_id | optional | null | 12345678 | The Facebook ID of the new/returning user.
photo_url | optional | null | http://myprofile.com/image.png | The photo URL of the new/returning user. Blank text resets photo to default - *Photo is updateable*
device_token | optional | null | asjh8712871D7812jJ | The token of an iOS device - *required for Push Notifications*.

<aside class="dev">Check whether <code>user_name</code> is actually optional or if there is some langauge ambiguity/conflict.</aside>

<aside class="success">It is recommended to store user <code>session_key</code> in the API client’s system. Not only is the <code>session_key</code> required for most API requests, storing the <code>session_key</code> will make subsequent API login requests unnecessary as the <code>session_key</code> represents the validated user identity.</aside>
