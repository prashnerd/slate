# Register

## Register User

```java
import java.io.**;
import java.net.URL;
import java.net.HttpURLConnection;

public class ApiTest {
    public static void main(String[] args) {
        System.out.println(executePost("https://gametize.com/api2/login.json", "api_key=********************************", "email=player5@gametize.com", "password=********", "user_name=Player 5"));
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
curl -i -H "Accept: application/json" -H "Content-Type: application/json" -X POST https://gametize.com/api2/register.json?api_key=********************************&email=player5@gametize.com&password=********&user_name=Player 5
```

>The above code returns JSON structured like this:

```json
{
    "gameId": 2,
    "code": 200,
    "sessionKey": "*-********-****-****-****-************",
    "firstLogin": true,
    "language": "en",
    "id": 6,
    "userId": 6,
    "user": {
        "photoLarge": "https://gametize.com/somepath/someimage.png",
        "photoSmall": "https://gametize.com/somepath/someimage.png",
        "name": "Player 5",
        "id": 6
    }
}
```

This endpoint **registers a new user** and keeps them logged in if users are not required to confirm their email (which is a project level setting).

### HTTP Request
`POST https://gametize.com/api2/register.json`

### Parameter(s)
Name | Usage | Default | Example | Description
---|---|---|---|---
api_key | **required** | null | 207302fde5e7-097a-4971-a4d4-de7154113ed7 | Validates the identity of the API client.
email | **required** | null | someone@somedomain.com | The email address of the new user.
password | **required** | null | qwRtys57! | The new password to set for the user. 
user_name | **required** | null | firstName lastName | The new user's name (will be displayed to the user).
