# Claims

## Claim Profile

```java
import java.io.**;
import java.net.URL;
import java.net.HttpURLConnection;

public class ApiTest {
    public static void main(String[] args) {
        System.out.println(executeGet("https://gametize.com/api2/claims/25.json"));
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
curl -i -H "Accept: application/json" -H "Content-Type: application/json" -H "Authorization: Bearer *-********-****-****-****-************" -X GET https://gametize.com/api2/claims/25.json
```

>The above code returns JSON structured like this:

```json
{
    "game": {
        "bannerImage": "https://gametize.com/somepath/someimage.png",
        "private": false,
        "teamEnabled": true,
        "id": 2,
        "title": "API Test Project",
        "searchEnabled": false,
        "guestEnabled": false
    },
    "commentNo": 0,
    "code": 200,
    "ratedLike": false,
    "userPhotoSmall": "https://gametize.com/somepath/someimage.png",
    "userName": "Player 1",
    "userId": 2,
    "quest": {
        "bannerImage": "https://gametize.com/somepath/someimage.png",
        "unlockable": false,
        "private": false,
        "questType": "standard",
        "challengeNo": 12,
        "description": "Standard Topic Description",
        "id": 1,
        "title": "Standard Topic"
    },
    "points": 20,
    "answerTitle": "Option 2",
    "userPhotoLarge": "https://gametize.com/somepath/someimage.png",
    "challenge": {
        "privateClaim": false,
        "challengeTypeId": 2,
        "locationOnly": false,
        "adminToClaim": false,
        "challengeType": "quiz",
        "id": 6,
        "confirmation": false,
        "title": "Quiz Challenge",
        "photoOnly": false
    },
    "id": 25,
    "createdAtFormatted": "3 days ago",
    "correctAnswer": true,
    "likeNo": 0
}
```

This endpoint retrieves the **detailed profile of a specific claim**.

### HTTP Request
`GET https://gametize.com/api2/claims/ID.json`

<aside class="notice">Remember to replace "<code>ID</code>" with the desired claim ID!"</aside>

### Header(s)
Name | Usage | Default | Example | Description
---|---|---|---|---
Authorization | optional | null | Bearer 2073-02fde5e7-097a-4971-a4d4-de7154113ed7 | Get data pertaining to you. This includes whether you have voted on the claim.

## Claim Comments

```java
import java.io.**;
import java.net.URL;
import java.net.HttpURLConnection;

public class ApiTest {
    public static void main(String[] args) {
        System.out.println(executeGet("https://gametize.com/api2/claims/30/comments.json"));
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
curl -i -H "Accept: application/json" -H "Content-Type: application/json" -H "Authorization: Bearer *-********-****-****-****-************" -X GET https://gametize.com/api2/claims/30/comments.json
```

>The above code returns JSON structured like this:

```json
{
    "code": 200,
    "data": [
        {
            "photoLarge": "https://gametize.com/somepath/someimage.png",
            "photoSmall": "https://gametize.com/somepath/someimage.png",
            "id": 6,
            "createdAtFormatted": "3 days ago",
            "message": "trippppppy",
            "userName": "Player 3",
            "userId": 4
        },
        {
            "photoLarge": "https://gametize.com/somepath/someimage.png",
            "photoSmall": "https://gametize.com/somepath/someimage.png",
            "id": 5,
            "createdAtFormatted": "3 days ago",
            "message": "So cool!",
            "userName": "Player 2",
            "userId": 3
        }
    ],
    "more": false
}
```

This endpoint retrieves a **list of comments on the specified claim**.

### HTTP Request
`GET https://gametize.com/api2/users/ID/bookmarks.json`

<aside class="notice">Remember to replace "<code>ID</code>" with the desired claim ID!"</aside>

### Parameter(s)

Name | Usage | Default | Example | Description
---|---|---|---|---
page | optional | 1 | 1 | Specify which page of results to retrieve.
limit | optional | 10 | 5 | Specify the number of results to be returned on each page.

### Header(s)
Name | Usage | Default | Example | Description
---|---|---|---|---
Authorization | optional | null | Bearer 2073-02fde5e7-097a-4971-a4d4-de7154113ed7 | Get data pertaining to you.

<aside class="dev">The 2.5.4 REST API Docs do not list <code>session_key</code> as one of the parameters for this HTTP request... Is this an error or is this accurate? Check with tech team...</aside>
