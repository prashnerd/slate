# Games

## Game Quests

```java
import java.io.**;
import java.net.URL;
import java.net.HttpURLConnection;

public class ApiTest {
    public static void main(String[] args) {
        System.out.println(executeGet("https://gametize.com/api2/games/2/quests.json"));
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
curl -i -H "Accept: application/json" -H "Content-Type: application/json" -H "Authorization: Bearer *-********-****-****-****-************" -X GET https://gametize.com/api2/games/2/quests.json
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
    "code": 200,
    "data": [
        {
            "unlockable": false,
            "private": false,
            "commentNo": 0,
            "iconImage": "https://gametize.com/somepath/someimage.png",
            "joined": true,
            "questType": "standard",
            "challengeNo": 12,
            "userChallengeCompletedNo": 9,
            "description": "Standard Topic Description",
            "id": 1,
            "createdAtFormatted": "18 Jan 2018",
            "title": "Standard Topic"
        }
    ],
    "more": false,
    "categories": [
        {
            "name": "Topic Category 2",
            "description": "Topic Category 2 Description",
            "id": 2,
            "selected": false
        }
    ],
    "team": {
        "userNo": 2,
        "name": "Team 1",
        "description": "Team 1 Description",
        "id": 1
    }
}
```

This endpoint retrieves a list of **quests in the specified game**.

### HTTP Request
`GET https://gametize.com/api2/games/ID/quests.json`

<aside class="notice">Remember to replace "<code>ID</code>" with the desired game ID!</aside>

### Parameter(s)

Name | Usage | Default | Example | Description
---|---|---|---|---
page | optional | 1 | 1 | Specify which page of results to retrieve.
limit | optional | 10 | 5 | Specify the number of results to be returned on each page.

### Header(s)

Name | Usage | Default | Example | Description
---|---|---|---|---
Authorization | optional | null | Bearer 2073-02fde5e7-097a-4971-a4d4-de7154113ed7 | Get data pertaining to you. This includes whether you have joined the game.

## Game Challenges

```java
import java.io.**;
import java.net.URL;
import java.net.HttpURLConnection;

public class ApiTest {
    public static void main(String[] args) {
        System.out.println(executeGet("https://gametize.com/api2/games/2/challenges.json", "page=6", "limit=2"));
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
curl -i -H "Accept: application/json" -H "Content-Type: application/json" -H "Authorization: Bearer *-********-****-****-****-************" -X GET https://gametize.com/api2/games/2/challenges.json?page=6&limit=2
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
    "code": 200,
    "data": [
        {
            "claimNo": 0,
            "locationOnly": false,
            "claimed": false,
            "title": "QR Code Challenge",
            "imageLarge": "https://gametize.com/somepath/someimage.png",
            "photoOnly": false,
            "createdAt": "2018-02-08 11:51:48.0",
            "unlockable": false,
            "ratings": 0,
            "claimedBefore": false,
            "repeat": false,
            "id": 13,
            "createdAtFormatted": "5 days ago",
            "imageType": "landscape",
            "noPhoto": false,
            "imageMedium": "https://gametize.com/somepath/someimage.png",
            "privateClaim": false,
            "commentNo": 0,
            "bookmarked": false,
            "ratedLike": false,
            "adminToClaim": false,
            "accepted": false,
            "challengeType": "qr",
            "footnote": "QR Code Challenge Description",
            "challengeTypeId": 7,
            "imageSmall": "https://gametize.com/somepath/someimage.png",
            "likeNo": 0
        },
        {
            "claimNo": 0,
            "locationOnly": false,
            "claimed": false,
            "title": "Custom Behavior (API) Challenge",
            "imageLarge": "https://gametize.com/somepath/someimage.png",
            "photoOnly": false,
            "createdAt": "2018-02-08 11:52:44.0",
            "unlockable": false,
            "ratings": 0,
            "claimedBefore": false,
            "repeat": false,
            "id": 14,
            "createdAtFormatted": "5 days ago",
            "imageType": "landscape",
            "noPhoto": false,
            "imageMedium": "https://gametize.com/somepath/someimage.png",
            "privateClaim": false,
            "commentNo": 0,
            "bookmarked": false,
            "ratedLike": false,
            "adminToClaim": false,
            "accepted": false,
            "challengeType": "api",
            "footnote": "Custom Behavior (API) Challenge Description",
            "challengeTypeId": 6,
            "imageSmall": "https://gametize.com/somepath/someimage.png",
            "likeNo": 0
        }
    ],
    "more": true
}
```

This endpoint returns a list of **challenges in the specified game**.

<aside class="success">Use this API call to search for challenges, using the useful <code>keywords</code> parameter!</aside>

### HTTP Request
`GET https://gametize.com/api2/games/ID/challenges.json`

<aside class="notice">Remember to replace "<code>ID</code>" with the desired game ID!</aside>

### Parameter(s)
Name | Usage | null | Example | Description
---|---|---|---|---
page | optional | 1 | 1 | Specify which page of resultts to retrieve.
limit | optional | 10 | 5 | Specify the number of results to be returned on each page.
keywords | **required** | null | holiday | Specify the search keywords.
category_id | optional | null | 2 | Filter results to only show challenges under the specified catagory.
order | optional | null | id_asc | Sorts results by the specified order. <br>Supported orders: <ul><li>claims_asc (no. of claims, ascending), </li><li>claims_desc (no. of claims, descending), </li><li>id_asc (challenge ID, ascending), </li><li>id_desc (challenge ID descending).</li></ul>

<aside class="warning">Note that in this case the <code>keywords</code> parameter is <strong>REQUIRED</strong>! <br>Failure to provide a <code>keywords</code> parameter <b><em>will result in this API call failing</em></b>.</aside>

### Header(s)
Name | Usage | Default | Example | Description
---|---|---|---|---
Authorization | optional | null | Bearer 2073-02fde5e7-097a-4971-a4d4-de7154113ed7 | Get data pertaining to you. This includes whether you have joined the game.

## Game Claims

```java
import java.io.**;
import java.net.URL;
import java.net.HttpURLConnection;

public class ApiTest {
    public static void main(String[] args) {
        System.out.println(executeGet("https://gametize.com/api2/games/2/claims.json", "page=3", "limit=2"));
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
curl -i -H "Accept: application/json" -H "Content-Type: application/json" -H "Authorization: Bearer *-********-****-****-****-************" -X GET https://gametize.com/api2/games/2/claims.json?page=3&limit=2
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
    "code": 200,
    "data": [
        {
            "commentNo": 0,
            "ratedLike": false,
            "userPhotoLarge": "https://gametize.com/somepath/someimage.png",
            "challenge": {
                "privateClaim": false,
                "challengeTypeId": 1,
                "locationOnly": false,
                "adminToClaim": false,
                "challengeType": "normal",
                "id": 2,
                "confirmation": false,
                "title": "Standard Challenge",
                "photoOnly": false
            },
            "id": 48,
            "createdAtFormatted": "3 days ago",
            "userPhotoSmall": "https://gametize.com/somepath/someimage.png",
            "message": "Okay...",
            "userName": "Player 4",
            "likeNo": 0,
            "userId": 5,
            "points": 10
        },
        {
            "commentNo": 0,
            "ratedLike": false,
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
            "id": 47,
            "createdAtFormatted": "3 days ago",
            "userPhotoSmall": "https://gametize.com/somepath/someimage.png",
            "correctAnswer": false,
            "userName": "Player 4",
            "likeNo": 0,
            "userId": 5,
            "points": 10
        }
    ],
    "more": true
}
```

This endpoint returns a list of **claims for all challenges** in the specified game.

### HTTP Request
`GET https://gametize.com/api2/games/ID/claims.json`

<aside class="notice">Remember to replace "<code>ID</code>" with the desired game ID!</aside>

### Parameter(s)
Name | Usage | null | Example | Description
---|---|---|---|---
page | optional | 1 | 1 | Specify which page of resultts to retrieve.
limit | optional | 10 | 5 | Specify the number of results to be returned on each page.
type | optional | null | following | Get claims in respect to certain classification for the logged in user (session_key is required). Available options: following.
filter | optional | null | image | filter data based on content type. Available options: image.
user_id | **required** | 0 | 2 | Get claims in respect to a particular user in the game.

<aside class="warning">Note that in this case the <code>user_id</code> parameter is <strong>REQUIRED</strong>! <br>Failure to provide a <code>user_id</code> parameter <b><em>will result in this API call failing</em></b>.</aside>

### Header(s)
Name | Usage | Default | Example | Description
---|---|---|---|---
Authorization | optional | null | Bearer 2073-02fde5e7-097a-4971-a4d4-de7154113ed7 | Get data with respect to you. This includes whether you have voted on the claim.

## Game Items

```java
import java.io.**;
import java.net.URL;
import java.net.HttpURLConnection;

public class ApiTest {
    public static void main(String[] args) {
        System.out.println(executeGet("https://gametize.com/api2/games/2/items.json", "user_id=2"));
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
curl -i -H "Accept: application/json" -H "Content-Type: application/json" -H "Authorization: Bearer *-********-****-****-****-************" -X GET https://gametize.com/api2/games/2/items.json?user_id=2
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

This endpoint retrieves a list of **items in the specified game** with respect to the specified user. 

### HTTP Request
`GET https://gametize.com/api2/games/ID/items.json`

<aside class="notice">Remember to replace "<code>ID</code>" with the desired game ID!</aside>

### Parameter(s)
Name | Usage | null | Example | Description
---|---|---|---|---
user_id | **required** | 0 | 2 | Get items with respect to a particular user in the game.

<aside class="warning">Note that in this case the <code>user_id</code> parameter is <strong>REQUIRED</strong>! <br>Failure to provide a <code>user_id</code> parameter <b><em>will result in this API call failing</em></b>.</aside>

### Header(s)
Name | Usage | Default | Example | Description
---|---|---|---|---
Authorization | optional | null | Bearer 2073-02fde5e7-097a-4971-a4d4-de7154113ed7 | Get data with respect to you. This includes whether you have earned this item or not.

## Game Store

```java
import java.io.**;
import java.net.URL;
import java.net.HttpURLConnection;

public class ApiTest {
    public static void main(String[] args) {
        System.out.println(executeGet("https://gametize.com/api2/games/2/store.json"));
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
curl -i -H "Accept: application/json" -H "Content-Type: application/json" -H "Authorization: Bearer *-********-****-****-****-************" -X GET https://gametize.com/api2/games/2/store.json
```

>The above code returns JSON structured like this:

```json
{
    "code": 200,
    "data": [
        {
            "ownedQuantity": 1,
            "createdAt": "2018-02-09 12:09:12.0",
            "price": 10,
            "name": "Reward 1",
            "imageSmall": "https://gametize.com/somepath/someimage.png",
            "description": "Reward 1 Description",
            "id": 1,
            "createdAtFormatted": "4 days ago",
            "imageLarge": "https://gametize.com/somepath/someimage.png",
            "adminToAward": false
        },
        {
            "ownedQuantity": 1,
            "createdAt": "2018-02-09 12:09:46.0",
            "price": 20,
            "name": "Reward 2",
            "imageSmall": "https://gametize.com/somepath/someimage.png",
            "description": "Reward 2 Description",
            "id": 2,
            "createdAtFormatted": "4 days ago",
            "imageLarge": "https://gametize.com/somepath/someimage.png",
            "adminToAward": false
        },
        {
            "ownedQuantity": 1,
            "createdAt": "2018-02-09 12:10:14.0",
            "price": 20,
            "name": "Reward 3",
            "imageSmall": "https://gametize.com/somepath/someimage.png",
            "description": "Reward 3 Description",
            "id": 3,
            "createdAtFormatted": "4 days ago",
            "imageLarge": "https://gametize.com/somepath/someimage.png",
            "adminToAward": false
        }
    ],
    "more": false,
    "categories": [
        {
            "name": "Reward Type 1",
            "description": "Reward Type 1 Description",
            "id": 1,
            "selected": false
        },
        {
            "name": "Reward Type 2",
            "description": "Reward Type 2 Description",
            "id": 2,
            "selected": false
        }
    ],
    "pointsAvailableInBundle": 85,
    "user": {
        "claimNo": 0,
        "photoLarge": "https://gametize.com/somepath/someimage.png",
        "photoSmall": "https://gametize.com/somepath/someimage.png",
        "name": "Player 1",
        "id": 2,
        "pointsAvailableInBundle": 85,
        "points": 0
    }
}
```

This endpoint retrieves a list of **purchasable items** in a game.

### HTTP Request
`GET https://gametize.com/api2/games/ID/store.json`

<aside class="notice">Remember to replace "<code>ID</code>" with the desired game ID!</aside>

### Paramater(s)
Name | Usage | Default | Example | Description
---|---|---|---|---
page | optional | 1 | 1 | Specify which page of results to retrieve.
limit | optional | 10 | 5 | Specify the number of results to be returned on each page.

### Header(s)
Name | Usage | Default | Example | Description
---|---|---|---|---
Authorization | optional | null | Bearer 2073-02fde5e7-097a-4971-a4d4-de7154113ed7 | Get data with respect to you. This includes whether you have earned this item or not.

## Game Users

```java
import java.io.**;
import java.net.URL;
import java.net.HttpURLConnection;

public class ApiTest {
    public static void main(String[] args) {
        System.out.println(executeGet("https://gametize.com/api2/games/2/users.json"));
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
curl -i -H "Accept: application/json" -H "Content-Type: application/json" -H "Authorization: Bearer *-********-****-****-****-************" -X GET https://gametize.com/api2/games/2/users.json
```

>The above code returns JSON structured like this:

```json
{
    "code": 200,
    "data": [
        {
            "photoLarge": "https://gametize.com/somepath/someimage.png",
            "photoSmall": "https://gametize.com/somepath/someimage.png",
            "name": "Player 1",
            "id": 2
        },
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

This endpoint retrieves a list of **users in the specified game**.

### HTTP Request
`GET https://gametize.com/api2/games/ID/users.json`

<aside class="notice">Remember to replace "<code>ID</code>" with the desired game ID!</aside>

### Parameter(s)
Name | Usage | Default | Example | Description
---|---|---|---|---
page | optional | 1 | 1 | Specify which page of resultts to retrieve.
limit | optional | 10 | 5 | Specify the number of results to be returned on each page.

### Header(s)
Name | Usage | Default | Example | Description
---|---|---|---|---
Authorization | optional | null | Bearer 2073-02fde5e7-097a-4971-a4d4-de7154113ed7 | Get data with respect to you. This includes whether you have followed this user or if this user has followed you.

## Game Teams

```java
import java.io.**;
import java.net.URL;
import java.net.HttpURLConnection;

public class ApiTest {
    public static void main(String[] args) {
        System.out.println(executeGet("https://gametize.com/api2/games/2/teams.json"));
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
curl -i -H "Accept: application/json" -H "Content-Type: application/json" -H "Authorization: Bearer *-********-****-****-****-************" -X GET https://gametize.com/api2/games/2/teams.json
```

>The above code returns JSON structured like this:

```json
{
    "code": 200,
    "data": [
        {
            "userNo": 2,
            "name": "Team 1",
            "description": "Team 1 Description",
            "id": 1
        },
        {
            "userNo": 2,
            "name": "Team 2",
            "description": "Team 2 Description",
            "id": 2
        }
    ],
    "more": false
}
```

This endpoint retrieves a list of **teams in the specified game**.

### HTTP Request
`GET https://gametize.com/api2/games/ID/teams.json`

<aside class="notice">Remember to replace "<code>ID</code>" with the desired game ID!</aside>

### Parameter(s)
Name | Usage | Default | Example | Description
---|---|---|---|---
page | optional | 1 | 1 | Specify which page of results to retrieve.
limit | optional | 10 | 5 | Specify the number of results to be returned on each page.

### Header(s)
Name | Usage | Default | Example | Description
---|---|---|---|---
Authorization | optional | null | Bearer 2073-02fde5e7-097a-4971-a4d4-de7154113ed7 | Get data with respect to you.

## Validate User

```java
import java.io.**;
import java.net.URL;
import java.net.HttpURLConnection;

public class ApiTest {
    public static void main(String[] args) {
        System.out.println(executeGet("https://gametize.com/api2/games/2/validate.json"));
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
curl -i -H "Accept: application/json" -H "Content-Type: application/json" -H "Authorization: Bearer *-********-****-****-****-************" -X GET https://gametize.com/api2/games/2/validate.json
```

>The above code returns JSON structured like this:

```json
{
    "code": 200,
    "id": 2,
    "title": "API Test Project"
}
```

This endpoint retrieves the **game status** with respect to a logged-in user. 

### HTTP Request
`GET https://gametize.com/api2/games/(ID or ALIAS)/validate.json`

<aside class="notice">Remember to replace "<code>ID</code>" with the desired game ID or alias!</aside>

### Header(s)
Name | Usage | Default | Example | Description
---|---|---|---|---
Authorization | **required** | null | Bearer 2073-02fde5e7-097a-4971-a4d4-de7154113ed7 | Get data with respect to you.

<aside class="warning">Note that in this case the <code>session_key</code> parameter is <strong>REQUIRED</strong>! <br>Failure to provide a <code>session_key</code> parameter <b><em>will result in this API call failing</em></b>.</aside>
