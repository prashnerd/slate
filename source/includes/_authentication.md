# Authentication

> To authorize your requests, pass in a login request to the API server using the following format:

```java
```

```python
```

```shell
```

```javascript
```

> Make sure to replace `yourkey` with your API key!

In Gametize, all applications using the API are given an **API Key** (data type: `string`). This API key is used to verify the application when a user logs in through it. All actions done by the user through the API (such as claiming, commenting, and voting) use the **session key** (data type: `string`) to identify the user. This **session key** is returned when the user logs in via the API (refer to code samples on the right). 

<aside class="success"> Following proper security conventions, Gametize recommends passing in your session_key as a HTTP Request <em><strong>header</strong></em> rather than as a <em><strong>parameter</strong></em>, though both are supported.</aside>

<aside class="quote"><em>After an application obtains an access token, it sends the token to a Google API in an HTTP authorization header. It is possible to send tokens as URI-string parameters, but we don't recommend it, because URI parameters can end up in log files that are not completely secure. Also, it is good REST practice to avoid creating unnecessary URI parameter names.</em> - <strong>Google, in their <a href="https://developers.google.com/identity/protocols/OAuth2" title="Using OAuth 2.0 to Access Google APIs">OAuth2 API Access Documentation Page</a></strong></aside>

You can find your API key listed in the project view when logged into the Admin Dashboard, under the project view. Use a URL in the format `https://yourdomain.gametize.com/admin/` to access the Admin Dashboard.

<aside class="notice">
Replace "<code>yourdomain</code>" with your application's domain name!
</aside>
