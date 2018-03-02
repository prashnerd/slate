# Login

If you've been referred here from the <a href="#authentication">Authentication</a> section, please note that you will need your `API Key` to continue!

<aside class="notice">Remember, you can get your <code>API key</code> when you login to your Admin Dashboard!</aside>

## Perform User Login

>The password parameter in this example is obfuscated in this example, but make sure you include the proper password in your own requests!

```java
import java.io.**;
import java.net.URL;
import java.net.HttpURLConnection;

public class ApiTest {
    public static void main(String[] args) {
        System.out.println(executePost("https://gametize.com/api2/login.json", "api_key=********************************", "email=player1@gametize.com", "password=********"));
    }
    
    public static String executePost(String targetURL, String... params) {
        HttpURLConnection con = null;
        // Prepare request URL
        if (params != null) {
            targetURL += "?";
            for (String param : params) {
                targetURL += param + "&";
            }
        }
        try {
            // Attempt a connection to the API server
            URL url = new URL(targetURL);
            con = (HttpURLConnection) url.openConnection();
            con.setRequestMethod("POST");
            // Add header fields
            con.setRequestProperty("Accept", "application/json");
            con.setRequestProperty("Content-Type", "application/json");
            con.setRequestProperty("Authorization", "Bearer *-********-****-****-****-************");
            con.setUseCaches(false);

            // Get response
            if (con.getResponseCode() == 201) {
                // If success code is returned, use InputStream
                InputStream input = con.getInputStream();
                BufferedReader reader = new BufferedReader(new InputStreamReader(input));
                StringBuffer response = new StringBuffer();
                response.append(reader.readLine());
                reader.close();
                return response.toString();
            }
            else {
                // If an error code is returned, check the ErrorStream instead
                InputStream input = con.getErrorStream();
                BufferedReader reader = new BufferedReader(new InputStreamReader(input));
                StringBuffer response = new StringBuffer();
                response.append(reader.readLine());
                reader.close();
                return response.toString();
            }
        } catch (Exception e) {
            e.printStackTrace();
            return null;
        } finally {
            if (con != null) {
                con.disconnect();
            }
        }
    }
}
```

```python
```

```javascript
```

```shell
curl -i -H "Accept: application/json" -H "Content-Type: application/json" -X POST http://gametizeblank.com:8080/api2/login.json?api_key=********************************&email=player1@gametize.com&password=********
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
        "photoLarge": "https://gametize.com/somepath/someimage.png",
        "photoSmall": "https://gametize.com/somepath/someimage.png",
        "name": "firstName lastName",
        "id": *
    }
}
```

This endpoint **logs a user in** using email and password.

<aside class="success">Register your users on <a href="https://gametize.com/">gametize.com/</a>, or using the <a href="#register-user">user registration</a> API call in your application!</aside>

<aside class="dev">This endpoint currently returns response code <code>200</code> in the JSON model, but the server responds with a <code>201</code> code by default for POST requests, some cleanup/overriding may be necessary, so keep that in mind!</aside>

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
