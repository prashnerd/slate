# Users

## User Profile

```java
import java.io.**;
import java.net.URL;
import java.net.HttpURLConnection;

public class ApiTest {
    public static void main(String[] args) {
        System.out.println(executeGet("https://gametize.com/api2/users/2.json"));
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
curl -i -H "Accept: application/json" -H "Content-Type: application/json" -H "Authorization: Bearer *-********-****-****-****-************" -X GET https://gametize.com/api2/users/2.json
```

>The above code returns JSON structured like this:

```json
{
    "claimNo": 0,
    "country": "UNKNOWN",
    "photoLarge": "https://gametize.com/somepath/someimage.png",
    "code": 200,
    "itemPhotos": [
        {
            "earned": true,
            "name": "Achievement 1",
            "imageSmall": "https://gametize.com/somepath/someimage.png",
            "id": 4,
            "imageLarge": "https://gametize.com/somepath/someimage.png"
        }
    ],
    "followingNo": 2,
    "photoSmall": "https://gametize.com/somepath/someimage.png",
    "followerNo": 3,
    "itemNo": 0,
    "points": 135,
    "followingPhotos": [
        {
            "photoLarge": "https://gametize.com/somepath/someimage.png",
            "photoSmall": "https://gametize.com/somepath/someimage.png",
            "name": "Player 3",
            "id": 4,
            "followed": true
        },
        {
            "photoLarge": "https://gametize.com/somepath/someimage.png",
            "photoSmall": "https://gametize.com/somepath/someimage.png",
            "name": "Player 2",
            "id": 3,
            "followed": true
        }
    ],
    "followersPhotos": [
        {
            "photoLarge": "https://gametize.com/somepath/someimage.png",
            "photoSmall": "https://gametize.com/somepath/someimage.png",
            "name": "Player 4",
            "id": 5,
            "followed": false
        },
        {
            "photoLarge": "https://gametize.com/somepath/someimage.png",
            "photoSmall": "https://gametize.com/somepath/someimage.png",
            "name": "Player 3",
            "id": 4,
            "followed": true
        },
        {
            "photoLarge": "https://gametize.com/somepath/someimage.png",
            "photoSmall": "https://gametize.com/somepath/someimage.png",
            "name": "Player 2",
            "id": 3,
            "followed": true
        }
    ],
    "name": "Player 1",
    "id": 2,
    "pointsAvailableInBundle": 0
}
```

This endpoint retrieves the **detailed profile of the specified user**.

### HTTP Request

`GET https://gametize.com/api2/users/ID.json`

<aside class="notice">Remember to replace "<code>ID</code>" with the desired user ID!</aside>

### Parameter(s)

Name | Usage | Default | Example | Description
---|---|---|---|---
bundle _id | optional | 0 | 3 | Get user data in respect to a bundle. For example, returns user points and items in a bundle.

### Header(s)

Name | Usage | Default | Example | Description
---|---|---|---|---
Authorization | optional | null | Bearer 2073-02fde5e7-097a-4971-a4d4-de7154113ed7 | Get data with respect to you. This includes whether you have followed this user or if this user has followed you.

## User Widget

```java
import java.io.**;
import java.net.URL;
import java.net.HttpURLConnection;

public class ApiTest {
    public static void main(String[] args) {
        System.out.println(executeGet("https://gametize.com/api2/users/2/widget.json"));
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
curl -i -H "Accept: application/json" -H "Content-Type: application/json" -H "Authorization: Bearer *-********-****-****-****-************" -X GET https://gametize.com/api2/users/2/widget.json
```

>The above code returns JSON structured like this:

```json
{
    "claimNo": 0,
    "photoLarge": "https://gametize.com/somepath/someimage.png",
    "code": 200,
    "photoSmall": "https://gametize.com/somepath/someimage.png",
    "name": "Player 1",
    "id": 2,
    "pointsAvailableInBundle": 0,
    "points": 135
}
```

This endpoint retrieves a **profile overview of the specified user**. 

### HTTP Request
`GET https://gametize.com/api2/users/ID/widget.json`

<aside class="notice">Remember to replace "<code>ID</code>" with the desired user ID!"</aside>

### Parameter(s)
Name | Usage | Default | Example | Description
---|---|---|---|---
game_id | optional | 0 | 3 | Get user data with respect to a game.

### Header(s)
Name | Usage | Default | Example | Description
---|---|---|---|---
Authorization | optional | null | Bearer 2073-02fde5e7-097a-4971-a4d4-de7154113ed7 | Get data with respect to you. This includes whether you have followed this user or if this user has followed you.

## Followers

```java
import java.io.**;
import java.net.URL;
import java.net.HttpURLConnection;

public class ApiTest {
    public static void main(String[] args) {
        System.out.println(executeGet("https://gametize.com/api2/users/2/followers.json"));
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
curl -i -H "Accept: application/json" -H "Content-Type: application/json" -H "Authorization: Bearer *-********-****-****-****-************" -X GET https://gametize.com/api2/users/2/followers.json
```

>The above code returns JSON structured like this:

```json
{
    "code": 200,
    "data": [
        {
            "photoLarge": "https://gametize.com/somepath/someimage.png",
            "photoSmall": "https://gametize.com/somepath/someimage.png",
            "name": "Player 2",
            "id": 3,
            "followed": true
        },
        {
            "photoLarge": "https://gametize.com/somepath/someimage.png",
            "photoSmall": "https://gametize.com/somepath/someimage.png",
            "name": "Player 3",
            "id": 4,
            "followed": true
        },
        {
            "photoLarge": "https://gametize.com/somepath/someimage.png",
            "photoSmall": "https://gametize.com/somepath/someimage.png",
            "name": "Player 4",
            "id": 5,
            "followed": false
        }
    ],
    "more": false
}
```

This endpoint retrieves a list of **users who follow the specified user**.

### HTTP Request
`GET https://gametize.com/api2/users/ID/followers.json`

<aside class="notice">Remember to replace "<code>ID</code>" with the desired user ID!"</aside>

### Parameter(s)
Name | Usage | Default | Example | Description
---|---|---|---|---
page | optional | 1 | 1 | Specify which page of results to retrieve.
limit | optional | 10 | 5 | Specify the number of results to be returned on each page.

### Header(s)
Name | Usage | Default | Example | Description
---|---|---|---|---
Authorization | optional | null | Bearer 2073-02fde5e7-097a-4971-a4d4-de7154113ed7 | Get data with respect to you. This includes whether you have followed this user or if this user has followed you.

## Following

```java
import java.io.**;
import java.net.URL;
import java.net.HttpURLConnection;

public class ApiTest {
    public static void main(String[] args) {
        System.out.println(executeGet("https://gametize.com/api2/users/2/following.json"));
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
curl -i -H "Accept: application/json" -H "Content-Type: application/json" -H "Authorization: Bearer *-********-****-****-****-************" -X GET https://gametize.com/api2/users/2/following.json
```

>The above code returns JSON structured like this:

```json
{
    "code": 200,
    "data": [
        {
            "photoLarge": "https://gametize.com/somepath/someimage.png",
            "photoSmall": "https://gametize.com/somepath/someimage.png",
            "name": "Player 2",
            "id": 3,
            "followed": true
        },
        {
            "photoLarge": "https://gametize.com/somepath/someimage.png",
            "photoSmall": "https://gametize.com/somepath/someimage.png",
            "name": "Player 3",
            "id": 4,
            "followed": true
        }
    ],
    "more": false
}
```

This endpoint retrieves a list of **users that the specified user follows**.

### HTTP Request
`GET https://gametize.com/api2/users/ID/following.json`

<aside class="notice">Remember to replace "<code>ID</code>" with the desired user ID!"</aside>

### Parameter(s)
Name | Usage | Default | Example | Description
---|---|---|---|---
page | optional | 1 | 1 | Specify which page of results to retrieve.
limit | optional | 10 | 5 | Specify the number of results to be returned on each page.

### Header(s)
Name | Usage | Default | Example | Description
---|---|---|---|---
Authorization | optional | null | Bearer 2073-02fde5e7-097a-4971-a4d4-de7154113ed7 | Get data pertaining to you. This includes whether you have followed this user or if this user has followed you.

## Joined Games

```java
import java.io.**;
import java.net.URL;
import java.net.HttpURLConnection;

public class ApiTest {
    public static void main(String[] args) {
        System.out.println(executeGet("https://gametize.com/api2/users/2/games.json"));
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
curl -i -H "Accept: application/json" -H "Content-Type: application/json" -H "Authorization: Bearer *-********-****-****-****-************" -X GET https://gametize.com/api2/users/2/games.json
```

>The above code returns JSON structured like this:

```json
{
    "code": 200,
    "data": [
        {
            "bannerImage": "https://gametize.com/somepath/someimage.png",
            "private": false,
            "teamEnabled": false,
            "id": 2,
            "title": "API Test Project",
            "searchEnabled": false,
            "guestEnabled": false
        }
    ],
    "more": false
}
```

This endpoints retrieves the list of **games the specified user is participating/has participated in**.

### HTTP Request
`GET https://gametize.com/api2/users/ID/games.json`

<aside class="notice">Remember to replace "<code>ID</code>" with the desired user ID!"</aside>

### Parameter(s)
Name | Usage | Default | Example | Description
---|---|---|---|---
page | optional | 1 | 1 | Specify which page of results to retrieve.
limit | optional | 10 | 5 | Specify the number of results to be returned on each page.

### Header(s)
Name | Usage | Default | Example | Description
---|---|---|---|---
Authorization | optional | null | Bearer 2073-02fde5e7-097a-4971-a4d4-de7154113ed7 | Get data pertaining to you. This includes whether you have voted on the claim.

## Accepted Challenges

>In this example, we'll be including some optional parameters in our example so that the sample JSON being displayed isn't too long. You may perform this API call with or without the optional parameters!

```java
import java.io.**;
import java.net.URL;
import java.net.HttpURLConnection;

public class ApiTest {
    public static void main(String[] args) {
        System.out.println(executeGet("https://gametize.com/api2/users/2/accepts.json", "bundle_id=2", "page=1", "limit=2"));
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
curl -i -H "Accept: application/json" -H "Content-Type: application/json" -H "Authorization: Bearer *-********-****-****-****-************" -X GET https://gametize.com/api2/users/2/accepts.json?bundle_id=2&page=1&limit=2
```

>The above code returns JSON structured like this:

```json
{
    "code": 200,
    "data": [
        {
            "claimNo": 4,
            "locationOnly": false,
            "claimed": false,
            "title": "Photo Challenge",
            "imageLarge": "https://gametize.com/somepath/someimage.png",
            "photoOnly": true,
            "createdAt": "2018-02-09 17:13:37.0",
            "unlockable": false,
            "ratings": 4,
            "claimedBefore": false,
            "repeat": false,
            "id": 1,
            "createdAtFormatted": "3 days ago",
            "imageType": "landscape",
            "noPhoto": false,
            "imageMedium": "https://gametize.com/somepath/someimage.png",
            "privateClaim": false,
            "commentNo": 0,
            "bookmarked": false,
            "ratedLike": false,
            "adminToClaim": false,
            "accepted": false,
            "challengeType": "normal",
            "challengeTypeId": 1,
            "imageSmall": "https://gametize.com/somepath/someimage.png",
            "likeNo": 0
        },
        {
            "claimNo": 4,
            "locationOnly": false,
            "claimed": false,
            "title": "Standard Challenge",
            "imageLarge": "https://gametize.com/somepath/someimage.png",
            "photoOnly": false,
            "createdAt": "2018-02-09 17:13:28.0",
            "unlockable": false,
            "ratings": 4,
            "claimedBefore": false,
            "repeat": false,
            "id": 2,
            "createdAtFormatted": "3 days ago",
            "imageType": "landscape",
            "noPhoto": false,
            "imageMedium": "https://gametize.com/somepath/someimage.png",
            "privateClaim": false,
            "commentNo": 1,
            "bookmarked": false,
            "ratedLike": false,
            "adminToClaim": false,
            "accepted": false,
            "challengeType": "normal",
            "challengeTypeId": 1,
            "imageSmall": "https://gametize.com/somepath/someimage.png",
            "likeNo": 0
        }
    ],
    "more": true
}
```

This endpoint retrieves a list of **challenges that the specified user has accepted** within the specified project.

### HTTP Request
`GET https://gametize.com/api2/users/ID/accepts.json`

<aside class="notice">Remember to replace "<code>ID</code>" with the desired user ID!"</aside>

### Parameter(s)
Name | Usage | Default | Example | Description
---|---|---|---|---
bundle_id | **required** | 0 | 3 | Filter the accepted challenges by a specific bundle.
page | optional | 1 | 1 | Specify which page of results to retrieve.
limit | optional | 10 | 5 | Specify the number of results to be returned on each page.

### Header(s)
Name | Usage | Default | Example | Description
---|---|---|---|---
Authorization | optional | null | Bearer 2073-02fde5e7-097a-4971-a4d4-de7154113ed7 | Get data pertaining to you. This includes whether you have claimed the challenge.

## Bookmarked Challenges

```java
import java.io.**;
import java.net.URL;
import java.net.HttpURLConnection;

public class ApiTest {
    public static void main(String[] args) {
        System.out.println(executeGet("https://gametize.com/api2/users/2/bookmarks.json", "bundle_id=2"));
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
curl -i -H "Accept: application/json" -H "Content-Type: application/json" -H "Authorization: Bearer *-********-****-****-****-************" -X GET https://gametize.com/api2/users/2/bookmarks.json?bundle_id=2
```

>The above code returns JSON structured like this:

```json
{
    "code": 200,
    "data": [
        {
            "claimNo": 0,
            "locationOnly": false,
            "claimed": false,
            "title": "Flashcard!",
            "imageLarge": "https://gametize.com/somepath/someimage.png",
            "photoOnly": false,
            "repeatEveryFormatted": "1 hour",
            "createdAt": "2018-02-09 17:34:54.0",
            "unlockable": false,
            "ratings": 2,
            "claimedBefore": false,
            "repeat": true,
            "id": 5,
            "createdAtFormatted": "3 days ago",
            "imageType": "landscape",
            "noPhoto": false,
            "imageMedium": "https://gametize.com/somepath/someimage.png",
            "privateClaim": false,
            "commentNo": 1,
            "bookmarked": true,
            "ratedLike": true,
            "adminToClaim": false,
            "accepted": true,
            "challengeType": "non-interactive",
            "footnote": "Flashcard Description",
            "challengeTypeId": 4,
            "imageSmall": "https://gametize.com/somepath/someimage.png",
            "likeNo": 3
        }
    ],
    "more": false
}
```

This endpoint retrieves a list of **challenges that the specified user has bookmarked**.

### HTTP Request
`GET https://gametize.com/api2/users/ID/bookmarks.json`

<aside class="notice">Remember to replace "<code>ID</code>" with the desired user ID!"</aside>

### Parameter(s)

Name | Usage | Default | Example | Description
---|---|---|---|---
bundle_id | **required** | 0 | 3 | Filter the bookmarked challenges by a specific bundle.
page | optional | 1 | 1 | Specify which page of results to retrieve.
limit | optional | 10 | 5 | Specify the number of results to be returned on each page.

### Header(s)
Name | Usage | Default | Example | Description
---|---|---|---|---
Authorization | optional | null | Bearer 2073-02fde5e7-097a-4971-a4d4-de7154113ed7 | Get data pertaining to you. This includes whether you have claimed the challenge.

## Earned Items

```java
import java.io.**;
import java.net.URL;
import java.net.HttpURLConnection;

public class ApiTest {
    public static void main(String[] args) {
        System.out.println(executeGet("https://gametize.com/api2/users/2/items.json"));
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
curl -i -H "Accept: application/json" -H "Content-Type: application/json" -H "Authorization: Bearer *-********-****-****-****-************" -X GET https://gametize.com/api2/users/2/items.json
```

>The above code returns JSON structured like this:

```json
{
    "code": 200,
    "data": [
        {
            "earned": true,
            "name": "Achievement 1",
            "imageSmall": "https://gametize.com/somepath/someimage.png",
            "id": 4,
            "imageLarge": "https://gametize.com/somepath/someimage.png"
        }
    ],
    "more": false
}
```

This endpoint retrieves a list of **items earned by the specified user**. 

### HTTP Request
`GET https://gametize.com/api2/users/ID/items.json`

<aside class="notice">Remember to replace "<code>ID</code>" with the desired user ID!"</aside>

### Header(s)
Name | Usage | Default | Example | Description
---|---|---|---|---
Authorization | optional | null | Bearer 2073-02fde5e7-097a-4971-a4d4-de7154113ed7 | Get data pertaining to you. This includes whether you have earned this item or not.

## Purchased Items

```java
import java.io.**;
import java.net.URL;
import java.net.HttpURLConnection;

public class ApiTest {
    public static void main(String[] args) {
        System.out.println(executeGet("https://gametize.com/api2/users/2/items_purchased.json"));
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
curl -i -H "Accept: application/json" -H "Content-Type: application/json" -H "Authorization: Bearer *-********-****-****-****-************" -X GET https://gametize.com/api2/users/items_purchased.json
```

>The above code returns JSON structured like this:

```json
{
    "code": 200,
    "data": [
        {
            "itemId": 1,
            "name": "Reward 1",
            "imageSmall": "https://gametize.com/somepath/someimage.png",
            "description": "Reward 1 Description",
            "id": 10,
            "imageLarge": "https://gametize.com/somepath/someimage.png"
        },
        {
            "itemId": 2,
            "name": "Reward 2",
            "imageSmall": "https://images.gametize.com/Burger.png",
            "description": "Reward 2 Description",
            "id": 11,
            "imageLarge": "https://images.gametize.com/Burger.png"
        },
        {
            "itemId": 3,
            "name": "Reward 3",
            "imageSmall": "https://images.gametize.com/Coffee.png",
            "description": "Reward 3 Description",
            "id": 12,
            "imageLarge": "https://images.gametize.com/Coffee.png"
        }
    ],
    "more": false,
    "user": {
        "claimNo": 0,
        "photoLarge": "https://gametize.com/somepath/someimage.png",
        "photoSmall": "https://gametize.com/somepath/someimage.png",
        "name": "Player 1",
        "id": 2,
        "pointsAvailableInBundle": 0,
        "points": 0
    }
}
```

This endpoint gets the list of **items purchased by the specified user**. Note that the user is prohibited from viewing other users' purchased items.

### HTTP Request
`GET https://gametize.com/api2/users/ID/items_purchased.json`

<aside class="notice">Remember to replace "<code>ID</code>" with the desired user ID!"</aside>

### Parameter(s)
Name | Usage | Default | Example | Description
---|---|---|---|---
page | optional | 1 | 1 | Specifies which page of results to retrieve.
limit | optional | 10 | 5 | Specify the number of results to be returned on each page.
bundle_id | optional | 0 | 3 | Filter the purchased items by a specific bundle.

### Header(s)
Name | Usage | Default | Example | Description
---|---|---|---|---
Authorization | **required** | null | Bearer 2073-02fde5e7-097a-4971-a4d4-de7154113ed7 | Get data pertaining to you. This includes whether you have earned this item or not.

<aside class="warning">Note that in this case the <code>session_key</code> for a user is <strong>REQUIRED</strong>! <br>Failure to provide a valid <code>session_key</code> <b><em>will result in this API call failing</em></b>.</aside>
