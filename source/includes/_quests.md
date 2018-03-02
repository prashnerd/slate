# Quests

<aside class="dev">Change the name of this endpoint/section to topic? Seems more straightforward and understandable for users and developers alike...</aside>

## Quest Profile

```java
import java.io.**;
import java.net.URL;
import java.net.HttpURLConnection;

public class ApiTest {
    public static void main(String[] args) {
        System.out.println(executeGet("https://gametize.com/api2/quests/1.json"));
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
curl -i -H "Accept: application/json" -H "Content-Type: application/json" -H "Authorization: Bearer *-********-****-****-****-************" -X GET https://gametize.com/api2/quests/1.json
```

>The above code returns JSON structured like this:

```json
{
    "private": false,
    "commentNo": 0,
    "code": 200,
    "iconImage": "https://gametize.com/somepath/someimage.png",
    "joined": true,
    "questType": "standard",
    "challengeNo": 12,
    "userChallengeCompletedNo": 0,
    "description": "Standard Topic Description",
    "title": "Standard Topic",
    "unlockable": false,
    "id": 1,
    "createdAtFormatted": "18 Jan 2018"
}
```

This endpoint retrieves the **detailed profile the specified quest**.

<aside class="dev">Check if this endpoint is still accurate or needs to be revised.</aside>

### HTTP Request
`GET https://gametize.com/api2/quests/ID.json`

<aside class="notice">Remember to replace "<code>ID</code>" with the desired quest ID!"</aside>

### Header(s)
Name | Usage | Default | Example | Description
---|---|---|---|---
Authorization | optional | null | Bearer 2073-02fde5e7-097a-4971-a4d4-de7154113ed7 | Get data pertaining to you. This includes whether you have joined the quest etc.

## Quest Challenges

```java
import java.io.**;
import java.net.URL;
import java.net.HttpURLConnection;

public class ApiTest {
    public static void main(String[] args) {
        System.out.println(executeGet("https://gametize.com/api2/quests/1/challenges.json"));
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
curl -i -H "Accept: application/json" -H "Content-Type: application/json" -H "Authorization: Bearer *-********-****-****-****-************" -X GET https://gametize.com/api2/quests/1/challenges.json?page=3&limit=1
```

>The above code returns JSON structured like this:

```json
{
    "wins": [
        {
            "earned": true,
            "name": "Achievement 1",
            "imageSmall": "https://gametize.com/somepath/someimage.png",
            "id": 4,
            "imageLarge": "https://gametize.com/somepath/someimage.png"
        }
    ],
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
            "claimNo": 4,
            "locationOnly": false,
            "claimed": true,
            "title": "Photo Challenge",
            "imageLarge": "https://gametize.com/somepath/someimage.png",
            "photoOnly": true,
            "createdAt": "2018-01-19 10:53:12.0",
            "unlockable": false,
            "ratings": 4,
            "claimedBefore": true,
            "repeat": false,
            "id": 1,
            "createdAtFormatted": "19 Jan 2018",
            "imageType": "landscape",
            "noPhoto": false,
            "imageMedium": "https://gametize.com/somepath/someimage.png",
            "privateClaim": false,
            "commentNo": 0,
            "bookmarked": false,
            "ratedLike": false,
            "adminToClaim": false,
            "accepted": true,
            "challengeType": "normal",
            "challengeTypeId": 1,
            "imageSmall": "https://gametize.com/somepath/someimage.png",
            "likeNo": 0
        }
    ],
    "more": true,
    "quest": {
        "unlockable": false,
        "private": false,
        "questType": "standard",
        "challengeNo": 12,
        "userChallengeCompletedNo": 9,
        "description": "Standard Topic Description",
        "id": 1,
        "title": "Standard Topic"
    }
}
```

This endpoint retrieves a list of **challenges in the specified quest**.

### HTTP Request
`GET https://gametize.com/api2/quests/ID/challenges.json`

<aside class="notice">Remember to replace "<code>ID</code>" with the desired quest ID!"</aside>

### Parameter(s)

Name | Usage | Default | Example | Description
---|---|---|---|---
page | optional | 1 | 1 | Specify which page of results to retrieve.
limit | optional | 10 | 5 | Specify the number of results to be returned on each page.
order | optional | null | id_asc | Sorts results by the specified order. <br>Supported orders: <ul><li>claims_asc (no. of claims, ascending), </li><li>claims_desc (no. of claims, descending), </li><li>id_asc (challenge ID, ascending), </li><li>id_desc (challenge ID descending).</li></ul>

### Header(s)
Name | Usage | Default | Example | Description
---|---|---|---|---
Authorization | optional | null | Bearer 2073-02fde5e7-097a-4971-a4d4-de7154113ed7 | Get data pertaining to you. This includes whether you have voted and/or claimed the challenge.

## Quest Claims

```java
import java.io.**;
import java.net.URL;
import java.net.HttpURLConnection;

public class ApiTest {
    public static void main(String[] args) {
        System.out.println(executeGet("https://gametize.com/api2/quests/1/claims.json", "page=2", "limit=2"));
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
curl -i -H "Accept: application/json" -H "Content-Type: application/json" -H "Authorization: Bearer *-********-****-****-****-************" -X GET https://gametize.com/api2/quests/1/claims.json?page=2&limit=2
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
                "challengeTypeId": 3,
                "locationOnly": false,
                "adminToClaim": false,
                "challengeType": "prediction",
                "id": 7,
                "confirmation": false,
                "title": "Prediction Challenge",
                "photoOnly": false
            },
            "id": 50,
            "createdAtFormatted": "3 days ago",
            "userPhotoSmall": "https://gametize.com/somepath/someimage.png",
            "userName": "Player 4",
            "likeNo": 0,
            "userId": 5,
            "points": 0
        },
        {
            "claimPhotoSmall": "https://gametize.com/somepath/someimage.png",
            "commentNo": 0,
            "claimPhotoType": "landscape",
            "ratedLike": false,
            "userPhotoSmall": "https://gametize.com/somepath/someimage.png",
            "message": "My favourite!",
            "userName": "Player 4",
            "userId": 5,
            "claimPhotoLarge": "https://gametize.com/somepath/someimage.png",
            "points": 10,
            "claimPhotoMedium": "https://gametize.com/somepath/someimage.png",
            "userPhotoLarge": "https://gametize.com/somepath/someimage.png",
            "challenge": {
                "privateClaim": false,
                "challengeTypeId": 1,
                "locationOnly": false,
                "adminToClaim": false,
                "challengeType": "normal",
                "id": 1,
                "confirmation": false,
                "title": "Photo Challenge",
                "photoOnly": true
            },
            "id": 49,
            "createdAtFormatted": "3 days ago",
            "likeNo": 0
        }
    ],
    "more": true,
    "quest": {
        "unlockable": false,
        "private": false,
        "questType": "standard",
        "challengeNo": 12,
        "description": "Standard Topic Description",
        "id": 1,
        "title": "Standard Topic"
    }
}
```

This endpoint retrieves a list of **claims for all challenges in the specified quest**.

### HTTP Request

`GET https://gametize.com/api2/api2/quests/ID/claims.json`

<aside class="notice">Remember to replace "<code>ID</code>" with the desired quest ID!</aside>

### Parameter(s)
Name | Usage | Default | Example | Description
---|---|---|---|---
page | optional | 1 | 1 | Specify which page of results to retrieve.
limit | optional | 10 | 5 | Specify the number of results to be returned on each page.
user_id | optional | 0 | 2 | Get claims in respect to a particular user in the quest.
filter | optional | null | image | Filter data based on content type. Available options: image.

### Header(s)
Name | Usage | Default | Example | Description
---|---|---|---|---
Authorization | optional | null | Bearer 2073-02fde5e7-097a-4971-a4d4-de7154113ed7 | Get data pertaining to you. This includes whether you have voted on the claim.

## Quest Users

```java
import java.io.**;
import java.net.URL;
import java.net.HttpURLConnection;

public class ApiTest {
    public static void main(String[] args) {
        System.out.println(executeGet("https://gametize.com/api2/quests/1/users.json", "page=1", "limit=2"));
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
curl -i -H "Accept: application/json" -H "Content-Type: application/json" -H "Authorization: Bearer *-********-****-****-****-************" -X GET https://gametize.com/api2/quests/1/users.json?page=1&limit=2
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
        }
    ],
    "more": true
}
```

This endpoint retrieves a list of **users in the specified quest**.

### HTTP Request

`GET https://gametize.com/api2/quests/ID/users.json`

<aside class="notice">Remember to replace "<code>ID</code>" with the desired quest ID!</aside>

### Parameter(s)
Name | Usage | Default | Example | Description
---|---|---|---|---
page | optional | 1 | 1 | Specify which page of results to retrieve.
limit | optional | 10 | 5 | Specify the number of results to be returned on each page.

### Header(s)
Name | Usage | Default | Example | Description
---|---|---|---|---
Authorization | optional | null | Bearer 2073-02fde5e7-097a-4971-a4d4-de7154113ed7 | Get data pertaining to you. This includes whether you have followed this user or if this user has followed you.

## Quest Leaderboard

```java
import java.io.**;
import java.net.URL;
import java.net.HttpURLConnection;

public class ApiTest {
    public static void main(String[] args) {
        System.out.println(executeGet("https://gametize.com/api2/quests/1/leaderboard.json", "page=1", "limit=2"));
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
curl -i -H "Accept: application/json" -H "Content-Type: application/json" -H "Authorization: Bearer *-********-****-****-****-************" -X GET https://gametize.com/api2/quests/1/leaderboard.json?page=1&limit=2
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
            "rank": 1,
            "id": 2,
            "points": 135
        },
        {
            "photoLarge": "https://gametize.com/somepath/someimage.png",
            "photoSmall": "https://gametize.com/somepath/someimage.png",
            "name": "Player 3",
            "rank": 2,
            "id": 4,
            "points": 120
        }
    ],
    "more": true
}
```

This endpoint retrieves a list of players on the leaderboard for the specified quest.

### HTTP Request

`GET https://gametize.com/api2/quests/ID/leaderboard.json`

<aside class="notice">Remember to replace "<code>ID</code>" with the desired quest ID!</aside>

### Parameter(s)
Name | Usage | Default | Example | Description
---|---|---|---|---
page | optional | 1 | 1 | Specify which page of results to retrieve.
limit | optional | 10 | 5 | Specify the number of results to be returned on each page.

<aside class="dev">The 2.5.4 REST API Docs do not list <code>session_key</code> as one of the parameters for this HTTP request... Is this an error or is this accurate? Check with tech team...</aside>

## Quest Leaderboard Overview

```java
import java.io.**;
import java.net.URL;
import java.net.HttpURLConnection;

public class ApiTest {
    public static void main(String[] args) {
        System.out.println(executeGet("https://gametize.com/api2/quests/1/leaderboard_overiew.json", "user_id=2"));
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
curl -i -H "Accept: application/json" -H "Content-Type: application/json" -H "Authorization: Bearer *-********-****-****-****-************" -X GET https://gametize.com/api2/quests/1/leaderboard_overview.json?user_id=2
```

>The above code returns JSON structured like this:

```json
{
    "lowestRank": {
        "photoLarge": "https://gametize.com/somepath/someimage.png",
        "photoSmall": "https://gametize.com/somepath/someimage.png",
        "name": "Admin",
        "rank": 5,
        "alias": "admin",
        "id": 1,
        "points": 0
    },
    "mainBoard": [
        {
            "photoLarge": "https://gametize.com/somepath/someimage.png",
            "photoSmall": "https://gametize.com/somepath/someimage.png",
            "name": "Player 1",
            "rank": 1,
            "id": 2,
            "points": 135
        },
        {
            "photoLarge": "https://gametize.com/somepath/someimage.png",
            "photoSmall": "https://gametize.com/somepath/someimage.png",
            "name": "Player 3",
            "rank": 2,
            "id": 4,
            "points": 120
        },
        {
            "photoLarge": "https://gametize.com/somepath/someimage.png",
            "photoSmall": "https://gametize.com/somepath/someimage.png",
            "name": "Player 2",
            "rank": 3,
            "id": 3,
            "points": 71
        },
        {
            "photoLarge": "https://gametize.com/somepath/someimage.png",
            "photoSmall": "https://gametize.com/somepath/someimage.png",
            "name": "Player 4",
            "rank": 4,
            "id": 5,
            "points": 50
        },
    ],
    "code": 200,
    "highestRank": {
        "photoLarge": "https://gametize.com/somepath/someimage.png",
        "photoSmall": "https://gametize.com/somepath/someimage.png",
        "name": "Player 1",
        "rank": 1,
        "id": 2,
        "points": 135
    }
}
```

This endpoint retrieves the leaderboard overview of a quest. Overview view types which my be returned include:

1. A single array of **Top 5** users if
  * the user **is** in the top 5 or,
  * the user has not earned any points.
2. An array of **Top 3** users *and* an array which includes the user's current position if
  * the user **is not** in the top 5.

### HTTP Request

`GET https://gametize.com/api2/quests/ID/leaderboard_overview.json`

<aside class="notice">Remember to replace "<code>ID</code>" with the desired quest ID!</aside>

### Parameter(s)
Name | Usage | Default | Example | Description
---|---|---|---|---
user_id | **required** | 0 | 2 | Get the leaderboard overview with respect to a particular user in quest.

<aside class="dev">Some params are still undocumented (as of 05/02/2018); consult Gametize library source code and update here.</aside>

<aside class="dev">The 2.5.4 REST API Docs do not list <code>session_key</code> as one of the parameters for this HTTP request... Is this an error or is this accurate? Check with tech team...</aside>

## Quest Items

```java
import java.io.**;
import java.net.URL;
import java.net.HttpURLConnection;

public class ApiTest {
    public static void main(String[] args) {
        System.out.println(executeGet("https://gametize.com/api2/quests/1/items.json"));
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
curl -i -H "Accept: application/json" -H "Content-Type: application/json" -H "Authorization: Bearer *-********-****-****-****-************" -X GET https://gametize.com/api2/quests/1/items.json
```

>The above code returns JSON structured like this:

```json
{
    "code": 200,
    "data": [
        {
            "earned": false,
            "name": "Achievement 1",
            "imageSmall": "https://gametize.com/somepath/someimage.png",
            "id": 4,
            "imageLarge": "https://gametize.com/somepath/someimage.png"
        }
    ],
    "more": false
}
```

This endpoint retrieves the list of items **to be earned** in the specified quest. Another user's ID may be specified if 

### HTTP Request

`GET https://gametize.com/api2/quests/ID/items.json`

<aside class="notice">Remember to replace "<code>ID</code>" with the desired quest ID!</aside>

### Parameter(s)
Name | Usage | Default | Example | Description
---|---|---|---|---
user_id | required | 0 | 2 | The user_id with respect to whom the items will be retrieved.

### Header(s)
Name | Usage | Default | Example | Description
---|---|---|---|---
Authorization | optional | null | Bearer 2073-02fde5e7-097a-4971-a4d4-de7154113ed7 | Get data pertaining to you. This includes whether you have earned this item or not.

## Quest Comments

```java
import java.io.**;
import java.net.URL;
import java.net.HttpURLConnection;

public class ApiTest {
    public static void main(String[] args) {
        System.out.println(executeGet("https://gametize.com/api2/quests/1/comments.json"));
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
curl -i -H "Accept: application/json" -H "Content-Type: application/json" -H "Authorization: Bearer *-********-****-****-****-************" -X GET https://gametize.com/api2/quests/1/comments.json
```

>The above code returns JSON structured like this:

```json
{
    "code": 200,
    "data": [
        {
            "photoLarge": "https://gametize.com/somepath/someimage.png",
            "photoSmall": "https://gametize.com/somepath/someimage.png",
            "id": 2,
            "createdAtFormatted": "3 days ago",
            "message": "Pretty fun!",
            "userName": "Player 1",
            "userId": 2
        }
    ],
    "more": false
}
```

This endpoint retrieves the list of comments for the specified quest.

### HTTP Request

`GET https://gametize.com/api2/quests/ID/comments.json`

<aside class="notice">Remember to replace "<code>ID</code>" with the desired quest ID!</aside>

### Parameter(s)
Name | Usage | Default | Example | Description
---|---|---|---|---
page | optional | 1 | 1 | Specify which page of results to retrieve.
limit | optional | 10 | 5 | Specify the number of results to be returned on each page.

## Header(s)
Name | Usage | Default | Example | Description
---|---|---|---|---
Authorization | optional | null | Bearer 2073-02fde5e7-097a-4971-a4d4-de7154113ed7 | Get data pertaining to you. This includes whether you have earned this item or not.
