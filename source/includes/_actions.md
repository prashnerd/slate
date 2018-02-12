# Actions

## Claim Challenge

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
`POST https://gametize.com/api2/action/claim.json`

<aside class="notice">Remember, a challenge needs to be <a href="#accept-challenge">accepted</a> before it can be claimed!</aside>

### Parameter(s)

**STANDARD CHALLENGE**

Name | Usage | Default | Example | Description
---|---|---|---|---
challenge_id | **required** | 0 | 2479 | The ID of the challenge to be claimed.
comment | **required** | 0 | null | My submission is the best! - *Must be longer than 5 characters!* | The description text of the claim to be submitted.
file | **required** if photo-only | null | [Image Data] | The photo image file of the claim to be submitted. Format: png, jpg, gif – *Max size: 2MB* (1MB or less recommended for reasonable mobile uploading experience.)
file_name | **required** if photo-only | null | claimphoto.jpg | The name of the image file being submitted.
tweet | optional | null | true | An optional metadata of claim for reference purposes only.
fb_wallpost | optional | null | true | An optional metadata of claim for reference purposes only.
latitude | optional | null | 1.3527652376 | An optional metadata of claim for reference purposes only.
longitude | optional | null | 103.1237128712 | An optional metadata of claim for reference purposes only.

<aside class="notice">A standard challenge is indicated by <code>challengeType: "normal"</code> <em>or</em> <code>challengeTypeId: 1</code>.</aside>

**QUIZ/PREDICTION CHALLENGE**

Name | Usage | Default | Example | Description
---|---|---|---|---
challenge_id | **required** | 0 | 2479 | The ID of the challenge to be claimed.
quiz_option_id | **required** | 0 | 145 | The ID of the quiz or prediction option selected for claiming.
tweet | optional | null | true | An optional metadata of claim for reference purposes only.
fb_wallpost | optional | null | true | An optional metadata of claim for reference purposes only.
latitude | optional | null | 1.3527652376 | An optional metadata of claim for reference purposes only.
longitude | optional | null | 103.1237128712 | An optional metadata of claim for reference purposes only.

<aside class="notice">A quiz challenge is indicated by <code>challengeType: "quiz"</code> <em>or</em> <code>challengeTypeId: 2</code> while a prediction challenge is indicated by <code>challengeType: "prediction"</code> <em>or</em> <code>challengeTypeId: 3</code>.</aside>

**Behaviour Challenge (API Challenge)** 

Name | Usage | Default | Example | Description
---|---|---|---|---
challenge_id | **required** | 0 | 2479 | The ID of the challenge to be claimed.
credits | optional | null | 50 | Defines the amount of credits to be awarded to the user for claiming.
latitude | optional | null | 1.3527652376 | An optional metadata of claim for reference purposes only.
longitude | optional | null | 103.1237128712 | An optional metadata of claim for reference purposes only.

<aside class="notice">A behaviour challenge is indicated by <code>challengeType: "api"</code> <em>or</em> <code>challengeTypeId: 6</code>.</aside>

**QR Challenge**

<aside class="success">The QR Challenge is a permutation of the Behaviour Challenge (API Challenge). In principle, the claim process is similar to a behavior challenge except the challenge identification is supplied through the plain text deciphered from the QR image.</aside>

Name | Usage | Default | Example | Description
---|---|---|---|---
comment | **required** | 0 | null | gm://qrchallenge/1234 | The plain text deciphered from the QR image - *the `challenge_id` is embedded within the `comment` parameter in this case.
credits | optional | null | 50 | Defines the amount of credits to be awarded to user for claiming.
latitude | optional | null | 1.3527652376 | An optional metadata of claim for reference purposes only.
longitude | optional | null | 103.1237128712 | An optional metadata of claim for reference purposes only.

<aside class="dev">Do you want to present each challenge type's claim format separately or consolidate as one type of claim? The latter will probably be better, but may be less readable/presentable...</aside>

<aside class="dev">These challenge claim actions are not defined in the current <em>API Documentation</em> Document, but more current definitions are coming soon...</aside>

**POLL CHALLENGE**

**CONFIRMATION CHALLENGE**

**CUSTOM FORM/MULTI-FIELD CHALLENGE**

**FIXED ANSWER/PASSCODE CHALLENGE**

**INVITATION/REFERRAL CHALLENGE**

### Header(s)
Name | Usage | Default | Example | Description
---|---|---|---|---
session_key | **required** | null | 2073-02fde5e7-097a-4971-a4d4-de7154113ed7 | Identifies the user performing the action.

<aside class="notice">This header is applicable for <em>all</em> claim types listed above.</aside>

## Purchase Item

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

This endpoint purchases an item available in the bundle store for the specified user.

### HTTP Request
`POST https://gametize.com/api2/action/purchase_item.json`

<aside class="notice">The specified user needs to have an adequate amount of credits awarded within the relevant bundle for the purchase to succeed!</aside>

### Parameter(s)
Name | Usage | Default | Example | Description 
---|---|---|---|---
type_id | **required** | 0 | 4567 | The ID of the item to be purchased.

### Header(s)
Name | Usage | Default | Example | Description
---|---|---|---|---
session_key | **required** | null | 2073-02fde5e7-097a-4971-a4d4-de7154113ed7 | Identifies the user performing the action.

## Update User

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

This endpoint updates the profile of the specified user.

### HTTP Request
`POST https://gametize.com/api2/action/update_user.json`

<aside class="notice">The specified user needs to have an adequate amount of credits awarded within the relevant bundle for the purchase to succeed!</aside>

### Parameter(s)
Name | Usage | Default | Example | Description 
---|---|---|---|---
user_name | optional | null | Someone Cool | The user's name.
photo_url | optional | null | http://myprofile.com/image.png | The URL to a user's photo. Giving a blank string `""` resets the user's photo to the default image. Providing the `file` and `file_name` parameters will omit the `photo_url`. 
country_id | optional | 0 | 192 | Country ID of the user - *contact support@gametize.com if you are unsure of what this parameter should be. 
telephone | optional | null | +6512345678 | Phone number of the user.
file | optional | null | [Image Data] | The photo image file for the user profile. Acceptable formats include: png, jpg, gif - *Maximum Size: 2MB*. 
file_name | optional | null | photo.jpg | The name of the image file for the user profile. 

### Header(s)
Name | Usage | Default | Example | Description
---|---|---|---|---
session_key | **required** | null | 2073-02fde5e7-097a-4971-a4d4-de7154113ed7 | Identifies the user performing the action.

## Post Comment

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

This endpoint posts a comment on a claim, challenge or game on behalf of a user.

### HTTP Request
`POST https://gametize.com/api2/action/comment.json`

### Parameter(s)
Name | Usage | Default | Example | Description
---|---|---|---|---
type | **required** | null | challenge | Acceptable types include: challenge, claim, game.
type_id | **required** | 0 | 2479 | The ID of the challenge, claim or game being commented on.
content | **required** | null | "Awesome!" | The text content of the comment.

### Header(s)
Name | Usage | Default | Example | Description
---|---|---|---|---
session_key | **required** | null | 2073-02fde5e7-097a-4971-a4d4-de7154113ed7 | Identifies the user performing the action.

## Like/Unlike

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

This endpoint likes/unlikes a challenge or claim for the specified user.

### HTTP Requests
`GET https://gametize.com/api2/action/rate.json`

### Parameter(s)
Name | Usage | Default | Example | Description
---|---|---|---|---
type | **required** | null | challenge | Acceptable types include: challenge, claim, game.
type_id | **required** | 0 | 2479 | The ID of the challenge, claim or game being liked/unliked.

### Header(s)
Name | Usage | Default | Example | Description
---|---|---|---|---
session_key | **required** | null | 2073-02fde5e7-097a-4971-a4d4-de7154113ed7 | Identifies the user performing the action.

## Accept Challenge

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

This endpoint accepts a challenge for the specified user.

<aside class="notice">This action must be performed for/by the user before that challenge can be claimed.</aside>

### HTTP Request
`GET https://gametize.com/api2/action/accept.json`

### Parameter(s)
Name | Usage | Default | Example | Description
---|---|---|---|---
type_id | **required** | 0 | 2479| The ID of the challenge to be accepted.

### Header(s)
Name | Usage | Default | Example | Description
---|---|---|---|---
session_key | **required** | null | 2073-02fde5e7-097a-4971-a4d4-de7154113ed7 | Identifies the user performing the action.

## Follow/Unfollow User

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

This endpoint follows/unfollows a user for the specified user.

### HTTP Request
`GET https://gametize.com/api2/action/follow.json`

### Parameter(s)
Name | Usage | Default | Example | Description
---|---|---|---|---
type_id | **required** | 0 | 2479 | The ID of the user to be followed/unfollowed.

### Header(s)
Name | Usage | Default | Example | Description
---|---|---|---|---
session_key | **required** | null | 2073-02fde5e7-097a-4971-a4d4-de7154113ed7 | Identifies the user performing the action.

## Join/Leave

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

This endpoint joins/leaves a game for the specified user.

### HTTP Request
`GET https://gametize.com/api2/action/join.json`

### Parameter(s)
Name | Usage | Default | Example | Description
---|---|---|---|---
type_id | **required** | 0 | 2479 | The ID of the game to be joined/left.
type | **required** | null | challenge | The alias of the game to be joined/left.

### Header(s)
Name | Usage | Default | Example | Description
---|---|---|---|---
session_key | **required** | null | 2073-02fde5e7-097a-4971-a4d4-de7154113ed7 | Identifies the user performing the action.

## Use Item

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

This endpoint uses a purchased item for the specified user.

### HTTP Request
`GET https://gametize.com/api2/action/use_item.json`

### Parameter(s)
Name | Usage | Default | Example | Description
---|---|---|---|---
type_id | **required** | 0 | 2479 | The ID of the item to be used - *item needs to have been purchased by the user*.

### Header(s)
Name | Usage | Default | Example | Description
---|---|---|---|---
session_key | **required** | null | 2073-02fde5e7-097a-4971-a4d4-de7154113ed7 | Identifies the user performing the action.

## Delete Claim

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

This endpoint deletes a claim for the specified user.

### HTTP Request
`GET https://gametize.com/api2/action/delete_claim.json`

### Parameter(s)
Name | Usage | Default | Example | Description
---|---|---|---|---
type_id | **required** | 0 | 2479 | The ID of the claim to be deleted.

### Header(s)
Name | Usage | Default | Example | Description
---|---|---|---|---
session_key | **required** | null | 2073-02fde5e7-097a-4971-a4d4-de7154113ed7 | Identifies the user performing the action.

## Add/Remove Bookmark

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

This endpoint joins/leaves a game for the specified user.

### HTTP Request
`GET https://gametize.com/api2/action/join.json`

### Parameter(s)
Name | Usage | Default | Example | Description
---|---|---|---|---
type_id | **required** | 0 | 2479 | The ID of the game to be joined/left.
flag | **required** | true/false | true | `true`: add bookmark;
`false`: remove bookmark.

<aside class="dev">The parameters of this API call are inconsistent with the style of similar API calls (ones which toggle a state). The others (like/unlike, join/leave) do not require a <code>true</code>/<code>false</code> flag, why does this? Consider revising to enforce homogenous styles for similar API calls.</aside>

### Header(s)
Name | Usage | Default | Example | Description
---|---|---|---|---
session_key | **required** | null | 2073-02fde5e7-097a-4971-a4d4-de7154113ed7 | Identifies the user performing the action.
