# Challenges

Challenges are the lowest level of categorization for the Gametize platform. Challenges are activities for the user to complete, and there are a wide range of possible activities, depending on the challenge type.

Here are the possible challenge types (classified by which platforms they are available on):

1. **All** Platforms (Web + Mobile)
  * Standard Challenge - Users post text or upload a photo.
  * Photo Challenge - Users must upload a photo.
  * Quiz Challenge - Users select one option from a set of options, of which only one is the correct answer.
  * Prediction Challenge - Users select one option from a set of possible predictions. The correct outcome can be set at a later time.
  * Poll Challenge - Users select on or more options from a set of options.
  * Confirmation Challenge - Users click on a confirmation button to complete this challenge. Best paired with another unlockable challenge. 
  * Fixed Answer/Passcode Challenge - Users must enter the correct answer, and may keep attempting until they get the answer right.
  * Custom Form Challenge - Users need to fill in several questions.
2. **Web** Only
  * Invitation/Referral Challenge - Users nvite more users to your project via a unique referral link.
3. **Mobile** Only
  * QR Code Challenge - Users scan a QR code via the app.
  * Custom Behaviour (API) Challenge.

When a user completes a challenge, it referred to as a "**claim**" Claims can vary depending on the challenge type, since it depends on what the user has to submit to complete the challenge. Documentation for performing claims can be found <a href="#claim-challenge">here</a>.

If a challenge is set to have non-private completions, users may view other users' activity, which allow them to vote and comment on those users' completions.

Collecting the data from claims, votes, and comments on a challenge can be a rather slow operation if the project has a lot of users/activity. 

<aside class="quote"><em>It's a happy problem.</em> - <strong>Damon Widjaja, Co-founder of Gametize</strong></aside>

## Challenge Profile

```java
```

```python
```

```javascript
```

```shell
curl -i -H "Accept: application/json" -H "Content-Type: application/json" -H "Authorization: Bearer 1-010356ce-ffbd-4c18-b1da-b0dc71648785" -X GET https://gametize.com/api2/challenges/2.json
```

>The above code returns JSON structured like this:

```json
{
    "claimNo": 4,
    "game": {
        "bannerImage": "https://images.gametize.com/Form.png",
        "private": false,
        "teamEnabled": true,
        "id": 2,
        "title": "API Test Project",
        "searchEnabled": false,
        "guestEnabled": false
    },
    "code": 200,
    "locationOnly": false,
    "claimed": false,
    "title": "Standard Challenge",
    "imageLarge": "http://gblank.dev:8080/images/core/placeholders/placeholder_challenge_image_normal.png",
    "photoOnly": false,
    "quest": {
        "bannerImage": "https://s3-ap-southeast-1.amazonaws.com/prasanth-imagelib/Globe.png",
        "unlockable": false,
        "private": false,
        "questType": "standard",
        "challengeNo": 12,
        "description": "Standard Topic Description",
        "id": 1,
        "title": "Standard Topic"
    },
    "createdAt": "2018-01-19 15:06:57.0",
    "unlockable": false,
    "ratings": 4,
    "claimedBefore": false,
    "previousChallengeId": 5,
    "repeat": false,
    "id": 2,
    "createdAtFormatted": "19 Jan 2018",
    "imageType": "landscape",
    "noPhoto": false,
    "imageMedium": "http://gblank.dev:8080/images/core/placeholders/placeholder_challenge_image_normal.png",
    "privateClaim": false,
    "commentNo": 1,
    "nextChallengeId": 1,
    "bookmarked": false,
    "ratedLike": false,
    "adminToClaim": false,
    "accepted": false,
    "challengeType": "normal",
    "challengeTypeId": 1,
    "imageSmall": "http://gblank.dev:8080/images/core/placeholders/placeholder_challenge_image_normal.png",
    "likeNo": 0
}
```

This endpoint retrieves the detailed profile of a specific challenge identified by the challenge ID.

### HTTP Request

`GET https://gametize.com/api2/challenges/ID.json`

<aside class="notice">Remember to replace "<code>ID</code>" with the desired challenge ID!"</aside>

### Header(s)

Name | Usage | Default | Example | Description
---|---|---|---|---
Authorization | optional | null | Bearer 2073-02fde5e7-097a-4971-a4d4-de7154113ed7 | Get data pertaining to you. This includes whether you have voted and/or claimed the challenge.

## Challenge Claims

```java
```

```python
```

```javascript
```

```shell
curl -i -H "Accept: application/json" -H "Content-Type: application/json" -H "Authorization: Bearer 1-010356ce-ffbd-4c18-b1da-b0dc71648785" -X GET https://gametize.com/api2/challenges/2/claims.json?page=2&limit=2
```

>The above code returns JSON structured like this:

```json
{
    "game": {
        "bannerImage": "https://images.gametize.com/Form.png",
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
            "commentNo": 1,
            "ratedLike": false,
            "userPhotoLarge": "http://gblank.dev:8080/images/core/consumer/game/placeholders/default_avatar.png",
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
            "id": 32,
            "createdAtFormatted": "2 days ago",
            "userPhotoSmall": "http://gblank.dev:8080/images/core/consumer/game/placeholders/default_avatar.png",
            "message": "Cool Stuff!",
            "userName": "Player 2",
            "likeNo": 1,
            "userId": 3,
            "points": 11
        },
        {
            "commentNo": 0,
            "ratedLike": false,
            "userPhotoLarge": "http://gblank.dev:8080/images/core/consumer/game/placeholders/default_avatar.png",
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
            "id": 23,
            "createdAtFormatted": "2 days ago",
            "userPhotoSmall": "http://gblank.dev:8080/images/core/consumer/game/placeholders/default_avatar.png",
            "message": "Awesome!",
            "userName": "Player 1",
            "likeNo": 1,
            "userId": 2,
            "points": 11
        }
    ],
    "more": false,
    "quest": {
        "bannerImage": "https://s3-ap-southeast-1.amazonaws.com/prasanth-imagelib/Globe.png",
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

>In this example, we used the `page` and `limit` parameter to show you how it should be used and how the return would look, and to truncate how much data is being fetched so this section remains readable (which is similar to why you might use it in your own application).

This endpoint retrieves the list of claims for a challenge filtered by the given parameters. 

### HTTP Request

`GET https://gametize.com/api2/challenges/ID/claims.json`

<aside class="notice">Remember to replace "<code>ID</code>" with the desired challenge ID!</aside>

### Parameter(s)

Name | Usage | Default | Example | Description
---|---|---|---|---
page | optional| 1 | 1 | Specifies which page of results to retrieve.
limit | optional | 10 | 5 | Specify the number of results to be displayed on each page.
user_id | optional | 0 | 2 | Filter to get claims from a particular user.
filter | optional | latest | popular | Filter claims based on content type. Available filters: image.

### Header(s)
Name | Usage | Default | Example | Description
---|---|---|---|---
Authorization | optional | null | Bearer 2073-02fde5e7-097a-4971-a4d4-de7154113ed7 | Get data pertaining to you. This includes whether you have voted on the claim.

## Challenge Comments

```java
```

```python
```

```javascript
```

```shell
curl -i -H "Accept: application/json" -H "Content-Type: application/json" -H "Authorization: Bearer 1-010356ce-ffbd-4c18-b1da-b0dc71648785" -X GET https://gametize.com/api2/challenges/2/comments.json
```

>The above code returns JSON structured like this:

```json
{
    "code": 200,
    "data": [
        {
            "photoLarge": "http://gblank.dev:8080/images/core/consumer/game/placeholders/default_avatar.png",
            "photoSmall": "http://gblank.dev:8080/images/core/consumer/game/placeholders/default_avatar.png",
            "id": 5,
            "createdAtFormatted": "2 days ago",
            "message": "Has everyone done this?? LOL",
            "userName": "Player 1",
            "userId": 2
        }
    ],
    "more": false
}
```

This endpoint retrieves the comments on the specified challenge.

### HTTP Request

`GET https://gametize.com/api2/challenges/ID/comments.json`

<aside class="notice">Remember to replace "<code>ID</code>" with the desired challenge ID!</aside>

### Parameter(s)
Name | Usage | Default | Example | Description
---|---|---|---|---
page | optional | 1 | 1 | Specify which page of results to retrieve.
limit | optional | 10 | 5 | Specify the number of results to be returned on each page.

### Header(s)

Name | Usage | Default | Example | Description
---|---|---|---|---
Authorization | optional | null | Bearer 2073-02fde5e7-097a-4971-a4d4-de7154113ed7 | Get data pertaining to you.

## Challenge Leaderboard

>Do note that you would rarely need to call the leaderboard API from the challenge level unless your targeted project makes use of it. You may refer to the <a href="#game-leaderboard">topic-level</a> or <a href="bundle-leaderboard">project-level</a> leaderboard API calls if they are more relevant to you. 

```java
```

```python
```

```javascript
```

```shell
curl -i -H "Accept: application/json" -H "Content-Type: application/json" -H "Authorization: Bearer 1-010356ce-ffbd-4c18-b1da-b0dc71648785" GET https://gametize.com/api2/challenges/2/leaderbaord.json
```

>The above code returns JSON structured like this:

```json
{
    "code": 200,
    "data": [
        {
            "photoLarge": "http://gblank.dev:8080/images/core/consumer/game/placeholders/default_avatar.png",
            "photoSmall": "http://gblank.dev:8080/images/core/consumer/game/placeholders/default_avatar.png",
            "name": "Player 1",
            "rank": 1,
            "id": 2,
            "points": 11
        },
        {
            "photoLarge": "http://gblank.dev:8080/images/core/consumer/game/placeholders/default_avatar.png",
            "photoSmall": "http://gblank.dev:8080/images/core/consumer/game/placeholders/default_avatar.png",
            "name": "Player 2",
            "rank": 2,
            "id": 3,
            "points": 11
        },
        {
            "photoLarge": "http://gblank.dev:8080/images/core/consumer/game/placeholders/default_avatar.png",
            "photoSmall": "http://gblank.dev:8080/images/core/consumer/game/placeholders/default_avatar.png",
            "name": "Player 3",
            "rank": 3,
            "id": 4,
            "points": 10
        },
        {
            "photoLarge": "http://gblank.dev:8080/images/core/consumer/game/placeholders/default_avatar.png",
            "photoSmall": "http://gblank.dev:8080/images/core/consumer/game/placeholders/default_avatar.png",
            "name": "Player 4",
            "rank": 4,
            "id": 5,
            "points": 10
        }
    ],
    "more": false
}
```

>Note that the `"more"` flag indicates if there are more entries in the leaderboard. This can be especially useful if you are using the `page` and `limit` parameters and need to know if more pages need to be displayed!

This endpoint retrieves a list of users on the leaderboard of the specified challenge.

### HTTP Request

`GET https://gametize.com/api2/challenges/ID/leaderboard.json`

<aside class="notice">Remember to replace "<code>ID</code>" with the desired challenge ID!</aside>

### Parameter(s)
Name | Usage | Default | Example | Description
---|---|---|---|---
page | optional | 1 | 1 | Specify which page of results to retrieve.
limit | optional | 10 | 5 | Specify the number of results to be returned on each page.

### Header(s)
Name | Usage | Default | Example | Description
---|---|---|---|---
Authorization | optional | null | Bearer 2073-02fde5e7-097a-4971-a4d4-de7154113ed7 | Get data pertaining to you.
