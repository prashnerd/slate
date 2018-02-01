---
title: Gametize API 

language_tabs: # must be one of https://git.io/vQNgJ
  - java
  - python
  - javascript
  - shell

toc_footers:
  - <a href='#'>Where can I get my API key?</a>
  - <a href='https://github.com/prashnerd/slate'>Documentation Powered by Slate</a>

includes:
  - errors

search: true
---

# Introduction

<aside class="warning">
Gametize's current API specification is <strong>only open to licensed applications</strong>, and the instructions below are only applicable to those users. Don't worry though: the platform will soon be open to all!
</aside>

**Introduction to Gametize API** Here are some fluffy words for introducing the Gametize API and explaining how it should be used. This section has been deliberately made longer so that we can see how it looks like when there's more text.

And hey, here's another paragraph to *really* fill this bit out. LALALALA APIs ARE AWSOME WOOOOOOOOO.

# Authentication

> To authorize your requests, pass in a login request to the API server using the following format:

```java

```

```python

```

```shell

```

```javascript

```

> Make sure to replace `yourkey` with your API key.

In Gametize, all applications using the API are given an API Key (data type: `string`). This API key is used to verify the application when a user logs in through it. All actions done by the user through the API (such as claiming, commenting, and voting) use the Session Key (data type: `string`) to identify the user. This session key is returned when the user logs in via the API. 

You can find your API key listed in the project view when logged into the administrator Content Management System (CMS), under the project view. Use the link format `https://yourdomain.com/admin/login.xhtml`

<aside class="notice">
Replace "<code>yourdomain</code>" with your application's domain name.
</aside>

# Challenges

## Get challenges based on filters

```java
sampleJavaCode
```

```python
sample_python_code
```

```shell
sample shell --code
```

```javascript
sample javascript = code
```

> The above code returns JSON structured like this:

```json

```

This endpoint retrieves all challenges based on filters.

### HTTP Request

`GET https://gametize.com/api2/challenges.json`

### Query Parameters

Parameter | Usage | Default | Example | Description
---|---|---|---|---
session_key | optional | null | 2073-02fde5e7-097a-4971-a4d4-de7154113ed7 | Get data pertaining to you. This includes whether you have voted and/or claimed the challenge.
page | optional| 1 | 1 | Specifies which page of results to retrieve.
limit | optional | 10 | 5 | Specify the number of results to be displayed on each page.
filter | optional | latest | popular | Filter challenges according to one of these options: latest, popular, or trending.
tag_name | optional | blank | food | Filter challenges to only display those with this tag.

<aside class="warning">
This API call does not seem to work! <strong> ATTEMPT TO VERIFY USAGE! </strong>
</aside>

## Get a list of claims for a challenge

```java
sampleJavaCode obj = new Thing();
```

```python
sample_python_code = something
if (!makeSense):
  too_bad()
else:
  hooray()
```

```shell
sample shell --code="fancy"
```

```javascript
sample javascript = code;
something.randomFunc();
```

> The above command returns JSON structured like this:

```json
{
    "claimNo": 0,
    "game": {
        "private": false,
        "teamEnabled": false,
        "id": 1,
        "title": "Project Name",
        "searchEnabled": false,
        "guestEnabled": false
    },
    "code": 200,
    "locationOnly": false,
    "claimed": false,
    "title": "Challenge Name",
    "imageLarge": "image_URL",
    "photoOnly": false,
    "quest": {
        "unlockable": false,
        "private": false,
        "questType": "standard",
        "challengeNo": 1,
        "id": 1,
        "title": "New Topic"
    },
    "createdAt": "some_date",
    "unlockable": false,
    "ratings": 0,
    "claimedBefore": false,
    "repeat": false,
    "id": 1,
    "createdAtFormatted": "date",
    "imageType": "landscape",
    "noPhoto": false,
    "imageMedium": "image_URL",
    "privateClaim": false,
    "commentNo": 0,
    "bookmarked": false,
    "ratedLike": false,
    "adminToClaim": false,
    "accepted": false,
    "challengeType": "normal",
    "challengeTypeId": 1,
    "imageSmall": "image_URL",
    "likeNo": 0
}
```

This endpoint retrieves the detailed profile of a challenge.

### HTTP Request

`GET https://gametize.com/api2/challenges/challengeID.json`

<aside class="notice"> Remember to replace "<code>challengeID</code> with the desired challenge ID!"</aside>

### Query Parameters

Parameter | Usage | Default | Example | Description
---|---|---|---|---
session_key | optional | null | 2073-02fde5e7-097a-4971-a4d4-de7154113ed7 | Get data pertaining to you. This includes whether you have voted and/or claimed the challenge.

## Delete a Specific Kitten

```java
require 'kittn'

api = Kittn::APIClient.authorize!('meowmeowmeow')
api.kittens.delete(2)
```

```python
import kittn

api = kittn.authorize('meowmeowmeow')
api.kittens.delete(2)
```

```shell
curl "http://example.com/api/kittens/2"
  -X DELETE
  -H "Authorization: meowmeowmeow"
```

```javascript
const kittn = require('kittn');

let api = kittn.authorize('meowmeowmeow');
let max = api.kittens.delete(2);
```

> The above command returns JSON structured like this:

```json
{
  "id": 2,
  "deleted" : ":("
}
```

This endpoint deletes a specific kitten.

### HTTP Request

`DELETE http://example.com/kittens/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the kitten to delete

