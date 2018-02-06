# Challenges

Challenges are the lowest level of categorization for the Gametize platform. Challenges are activities for the user to complete, which can range from submitting a photograph and/or a text comment (*Standard Challenges*) to simply clicking on a button (*Confirmation Challenges*) to scanning a QR code (*QR Challenges*).

When a User completes a challenge, it referred to as a "**claim**" Claims can vary depending on the challenge type, since it depends on what the user has to submit to complete the challenge. Documentation for performing claims can be found <a href="#claim-challenge">here</a>.

If a challenge is set to have non-private completions, users may view other users' activity, which allow them to vote and comment on those users' completions.

Collecting the data from claims, votes and comments on a challenge can be a rather slow operation if the project has a lot of users/activity. 

<aside class="quote"><em>It's a happy problem.</em> - <strong>Damon Widjaja, Co-founder of Gametize</strong></aside>

## Challenge Profile

```java
```

```python
```

```shell
curl -i -H "Accept: application/json" -H "Content-Type: application/json" -H "Authorization: Bearer 178877-2f942e55-e166-4089-8efb-bceb1f15f811" -X GET http://gmaki.com:8080/api2/challenges/90204.json >> somefile
```

```javascript
```

>The above code returns JSON structured like this:

```json
{
{
	"claimNo": 0,
	"game": {
		"private": false,
		"teamEnabled": false,
		"id": 2311,
		"title": "Project 1",
		"searchEnabled": false,
		"guestEnabled": false
	},
	"code": 200,
	"locationOnly": false,
	"claimed": false,
	"title": "Standard Challenge 1",
	"imageLarge": "https://gametize.com/images/core/placeholders/placeholder_challenge_image_normal.png",
	"photoOnly": false,
	"quest": {
		"unlockable": false,
		"private": false,
		"questType": "standard",
		"challengeNo": 2,
		"id": 6526,
		"title": "Topic 1"
	},
	"createdAt": "2018-02-06 13:12:10.0",
	"unlockable": false,
	"ratings": 0,
	"claimedBefore": false,
	"repeat": false,
	"id": 90204,
	"createdAtFormatted": "9 minutes ago",
	"imageType": "landscape",
	"noPhoto": false,
	"imageMedium": "https://gametize.com/images/core/placeholders/placeholder_challenge_image_normal.png",
	"privateClaim": false,
	"commentNo": 0,
	"nextChallengeId": 90205,
	"bookmarked": false,
	"ratedLike": false,
	"adminToClaim": false,
	"accepted": false,
	"challengeType": "normal",
	"challengeTypeId": 1,
	"imageSmall": "https://gametize.com/images/core/placeholders/placeholder_challenge_image_normal.png",
	"likeNo": 0
}
```

This endpoint retrieves the detailed profile of a specific challenge identified by the challenge ID.

### HTTP Request

`GET https://yourdomain/api2/challenges/ID.json`

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

```shell
curl -i -H "Accept: application/json" -H "Content-Type: application/json" -H "Authorization: Bearer 178877-2f942e55-e166-4089-8efb-bceb1f15f811" -X GET http://gmaki.com:8080/api2/challen
ges/90204/claims.json >> somefile
```

```javascript
```

>The above code returns JSON structured like this:

```json
{
	"game": {
		"private": false,
		"teamEnabled": false,
		"id": 2311,
		"title": "Project 1",
		"searchEnabled": false,
		"guestEnabled": false
	},
	"code": 200,
	"data": [
		{
			"commentNo": 1,
			"ratedLike": true,
			"userPhotoLarge": "https://gametize.com/images/core/consumer/game/placeholders/default_avatar.png",
			"challenge": {
				"privateClaim": false,
				"challengeTypeId": 1,
				"locationOnly": false,
				"adminToClaim": false,
				"challengeType": "normal",
				"id": 90204,
				"confirmation": false,
				"title": "Standard Challenge 1",
				"photoOnly": false
			},
			"id": 668372,
			"createdAtFormatted": "40 seconds ago",
			"userPhotoSmall": "https://gametize.com/images/core/consumer/game/placeholders/default_avatar.png",
			"message": "Claim 1",
			"userName": "Prasanth Karthikeyan",
			"likeNo": 1,
			"userId": 178877,
			"points": 10
		}
	],
	"more": false,
	"quest": {
		"unlockable": false,
		"private": false,
		"questType": "standard",
		"challengeNo": 2,
		"id": 6526,
		"title": "Topic 1"
	}
}
```

This endpoint retrieves the list of claims for a challenge sorted and filtered by the given parameters. 

### HTTP Request

`GET https://yourdomain/api2/challenges/ID/claims.json`

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

```shell
curl -i -H "Accept: application/json" -H "Content-Type: application/json" -H "Authorization: Bearer 178877-2f942e55-e166-4089-8efb-bceb1f15f811" -X GET http://gmaki.com:8080/api2/challen
ges/90204/comments.json >> somefile
```

```javascript
```

>The above code returns JSON structured like this:

```json
{
    "code": 200,
    "data": [
        {
            "photoLarge": "https://gametize.com/images/core/consumer/game/placeholders/default_avatar.png",
            "photoSmall": "https://gametize.com/images/core/consumer/game/placeholders/default_avatar.png",
            "id": 9253,
            "createdAtFormatted": "3 hours ago",
            "message": "Comment 2",
            "userName": "Prasanth Karthikeyan",
            "userId": 178877
        },
        {
            "photoLarge": "https://gametize.com/images/core/consumer/game/placeholders/default_avatar.png",
            "photoSmall": "https://gametize.com/images/core/consumer/game/placeholders/default_avatar.png",
            "id": 9252,
            "createdAtFormatted": "3 hours ago",
            "message": "Comment 1",
            "userName": "Prasanth Karthikeyan",
            "userId": 178877
        }
    ],
    "more": false
}
```

This endpoint retrieves the comments on the specified challenge.

### HTTP Request

`GET https://yourdomain/challenges/ID/comments.json`

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

```java
```

```python
```

```shell
```

```javascript
```

>The above code returns JSON structured like this:

```json
```
  
### HTTP Request

`GET https://yourdomain/api2/challenges/ID/leaderboard.json`

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
