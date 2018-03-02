# Notifications

## All Notifications

```java
import java.io.**;
import java.net.URL;
import java.net.HttpURLConnection;

public class ApiTest {
    public static void main(String[] args) {
        System.out.println(executeGet("https://gametize.com/api2/notifications.json", "page=3", "limit=2"));
    }
    
    public static String executeGet(String targetURL, String... params) {
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
            con.setRequestMethod("GET");
            // Add header fields
            con.setRequestProperty("Accept", "application/json");
            con.setRequestProperty("Content-Type", "application/json");
            con.setRequestProperty("Authorization", "Bearer *-********-****-****-****-************");
            con.setUseCaches(false);

            // Get response
            if (con.getResponseCode() == 200) {
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
curl -i -H "Accept: application/json" "Content-Type: application/json" -H "Authorization: Bearer *-********-****-****-****-************" -X GET https://gametize.com/api2/notifications.json?page=3&limit=2
```

>The above code returns JSON structured like this:

```json
{
    "code": 200,
    "data": [
        {
            "createdAt": "2018-02-09 18:15:36.0",
            "challengeId": 17,
            "photoLarge": "https://gametize.com/somepath/someimage.png",
            "read": true,
            "photoSmall": "https://gametize.com/somepath/someimage.png",
            "id": 31,
            "createdAtFormatted": "3 days ago",
            "type": "claim",
            "userId": 4,
            "content": "Player 3 voted up your submission to \"test challenge\" for 1 points"
        },
        {
            "createdAt": "2018-02-09 18:03:11.0",
            "challengeId": 11,
            "photoLarge": "https://gametize.com/somepath/someimage.png",
            "read": true,
            "photoSmall": "https://gametize.com/somepath/someimage.png",
            "id": 30,
            "createdAtFormatted": "3 days ago",
            "type": "claim",
            "userId": 3,
            "content": "Player 2 commented on your submission to \"Custom Form Challenge\""
        }
    ],
    "more": true
}
```

This endpoint retrieves the list of notifications for the specified user.

### HTTP Request
`GET https://gametize.com/api2/notifications.json`

### Parameter(s)
Name | Usage | Default | Example | Description
---|---|---|---|---
page | optional | 1 | 1 | Specify which page of results to retrieve.
limit | optional | 1 | 1 | Specify the number of results to be returned on each page.
game_id | optional | 0 | 124 | Get notifications with respect to a particular game.

### Header(s)
Name | Usage | Default | Example | Description
---|---|---|---|---
Authorization | **required** | null | Bearer 2073-02fde5e7-097a-4971-a4d4-de7154113ed7| Get your notifications.

## Unread Notification Count

```java
import java.io.**;
import java.net.URL;
import java.net.HttpURLConnection;

public class ApiTest {
    public static void main(String[] args) {
        System.out.println(executeGet("https://gametize.com/api2/notifications/unread.json"));
    }
    
    public static String executeGet(String targetURL, String... params) {
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
            con.setRequestMethod("GET");
            // Add header fields
            con.setRequestProperty("Accept", "application/json");
            con.setRequestProperty("Content-Type", "application/json");
            con.setRequestProperty("Authorization", "Bearer *-********-****-****-****-************");
            con.setUseCaches(false);

            // Get response
            if (con.getResponseCode() == 200) {
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
curl -i -H "Accept: application/json" "Content-Type: application/json" -H "Authorization: Bearer *-********-****-****-****-************" -X GET https://gametize.com/api2/notifications/unread.json
```

>The above code returns JSON structured like this:

```json
{
    "code": 200,
    "unread": 11
}
```

This endpoint retrieves the **number of unread notifications** for the specified user.

### HTTP Request
`GET https://gametize.com/api2/notifications/unread.json`

### Parameter(s)
Name | Usage | Default | Example | Description
---|---|---|---|---
game_id | optional | 0 | 124 | Get notifications with respect to a particular game.

<aside class="dev">No <code>page</code> and <code>limit</code> parameters for this, but required above for all notifications? May require fix/standardization.</aside>

### Header(s)
Name | Usage | Default | Example | Description
---|---|---|---|---
Authorization | **required** | null | Bearer 2073-02fde5e7-097a-4971-a4d4-de7154113ed7| Get your notifications.
