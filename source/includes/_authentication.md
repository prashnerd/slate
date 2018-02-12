# Authentication

>The sample code for authenticating the user can be found in the <a href="#login">login</a> section of this document, but is replicated here for easy access. Note that the password is obfuscated here, and is not *actually* comprised of 8 asterisks; you would include the password as plaintext in your own application. 

```java
```

```python
```

```javascript
```

```shell
curl -i -H "Accept: application/json" -H "Content-Type: application/json" -X POST https://gametize.com/api2/login.json?api_key=78f89720684c4034a75b3024a4cd857f&email=player1@gametize.com&password=********
```

>The above code returns a `session_key` enclosed within a JSON object if the user is authenticated successfully, shown below.

```json
{
    "gameId": 2,
    "code": 200,
    "sessionKey": "2-d55bd0aa-9dc1-4df9-83c2-3663cd754bed",
    "firstLogin": false,
    "newRegistration": false,
    "language": "en",
    "userId": 2,
    "user": {
        "country": "UNKNOWN",
        "photoLarge": "http://gblank.dev:8080/images/core/consumer/game/placeholders/default_avatar.png",
        "photoSmall": "http://gblank.dev:8080/images/core/consumer/game/placeholders/default_avatar.png",
        "name": "Player 1",
        "id": 2
    }
}
```

In Gametize, all applications using the API are given an **API Key** (data type: `string`). This API key is used to verify the application when a user logs in through it. All actions done by the user through the API (such as claiming, commenting, and voting) use the `session_key` (data type: `string`) to identify the user. This `session_key` is returned when the user is logged in via the API - ***refer to the <a href="#login">login</a> section for more details***. 

<aside class="success"> Following proper security conventions, Gametize recommends passing in your session_key as a HTTP Request <em><strong>header</strong></em> rather than as a <em><strong>parameter</strong></em>, though both are supported.</aside>

To quote Google on this practice:

<aside class="quote"><em>After an application obtains an access token, it sends the token to a Google API in an HTTP authorization header. It is possible to send tokens as URI-string parameters, but we don't recommend it, because URI parameters can end up in log files that are not completely secure. Also, it is good REST practice to avoid creating unnecessary URI parameter names.</em> - <strong>Google, in their <a href="https://developers.google.com/identity/protocols/OAuth2" title="Using OAuth 2.0 to Access Google APIs">OAuth2 API Access Documentation Page</a></strong></aside>

You can find your API key listed in the project view when logged into the Admin Dashboard, under the project view. Use the URL `https://gametize.com/login/` to access the Admin Dashboard after logging in.

<aside class="notice">
Replace "<code>yourdomain</code>" with your application's domain name!
</aside>
