---
title: Gametize API 

language_tabs: # must be one of https://git.io/vQNgJ
  - java
  - python
  - javascript
  - shell

toc_footers:
  - <a href='#'>Where can I get my API key?</a>
  - <a href='https://github.com/lord/slate'>Documentation Powered by Slate</a>

includes:
  - errors

search: true
---
  
# Introduction<a name="introduction"></a>

<aside class="warning">
Gametize's current API specification is <strong>only open to licensed applications</strong>, and the instructions below are only applicable to those users. Don't worry though: the platform will soon be open to all!
</aside>

**Introduction to Gametize API** Here are some fluffy words for introducing the Gametize API and explaining how it should be used. This section has been deliberately made longer so that we can see how it looks like when there's more text.

And hey, here's another paragraph to *really* fill this bit out. LALALALA APIs ARE AWSOME WOOOOOOOOO.

# Terminology<a name="authentication"></a>

To aid in platform administration experience, Gametize has **redefined terms** found in the Admin Dashboard to showcase a more logical correlation between entities. However, **the terms are left unchanged in the API**, as it might be disruptive to live applications. Please take note of the following:

Name in API | Name in Admin Dashboard
:---:|:---:
Bundle | Project
Game | Topic
Challenge | Challenge (unchanged)

<aside class="notice">NOTICE <strong>NOTICE</strong> <em>NOTICE</em></aside>
<aside class="warning">WARNING <strong>WARNING</strong> <em>WARNING</em></aside>
<aside class="success">SUCCESS <strong>SUCCESS</strong> <em>SUCCESS</em></aside>
<aside class="dev">DEV <strong>DEV</strong> <em>DEV</em></aside>

# Authentication<a name="authentication"></a>

> To authorize your requests, pass in a login request to the API server using the following format:

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

> Make sure to replace `yourkey` with your API key!

In Gametize, all applications using the API are given an **API Key** (data type: `string`). This API key is used to verify the application when a user logs in through it. All actions done by the user through the API (such as claiming, commenting, and voting) use the **Session Key** (data type: `string`) to identify the user. This **Session Key** is returned when the user logs in via the API (refer to code samples). 

<aside class="success"> Following proper security conventions, Gametize recommends passing in your session_key as a HTTP Request <em>header</em> rather than as a <em>parameter</em>, though both are supported. <p><br>To quote Google on this convention:<br><i><q>After an application obtains an access token, it sends the token to a Google API in an HTTP authorization header. It is possible to send tokens as URI-string parameters, but we don't recommend it, because URI parameters can end up in log files that are not completely secure. Also, it is good REST practice to avoid creating unnecessary URI parameter names.</q></i></p></aside>

You can find your API key listed in the project view when logged into the Admin Dashboard, under the project view. Use a URL in the format `https://yourdomain.com/admin/` to access the Admin Dashboard.

<aside class="notice">
Replace "<code>yourdomain</code>" with your application's domain name!
</aside>

Views<a name="views"></a>

# Challenges<a name="challenges"></a>

Challenges are the lowest level of categorization for the Gametize platform. Challenges are activities for the user to complete, which can range from submitting a photograph and/or a text comment (*Standard Challenges*) to simply clicking on a button (*Confirmation Challenges*) to scanning a QR code (*QR Challenges*).

When a [User](#users) completes a challenge, it referred to as a "**Claim**"". 

## Challenge Profile

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

> The above code returns JSON structured like this:

```json
{
    "claimNo": 0,
}
```

This endpoint retrieves the detailed profile of a specific challenge identified by the challenge ID.

### HTTP Request

`GET https://gametize.com/api2/challenges/ID.json`

<aside class="notice"> Remember to replace "<code>ID</code>" with the desired challenge ID!"</aside>

### Header(s)

Name | Usage | Default | Example | Description
---|---|---|---|---
Authorization | optional | null | Bearer 2073-02fde5e7-097a-4971-a4d4-de7154113ed7 | Get data pertaining to you. This includes whether you have voted and/or claimed the challenge.

## Claims

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

> The above code returns JSON structured like this:

```json
{
  json: "example"
}
```

This endpoint retrieves the list of claims for a challenge sorted and filtered by the given parameters. 

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
Authorization | optional | null | Bearer 2073-02fde5e7-097a-4971-a4d4-de7154113ed7 | Get data pertaining to you. This includes whether you have voted and/or claimed the challenge.

## Comments

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

> The above code returns JSON structured like this:

```json
{
  json: "example"
}
```

This endpoint retrieves the comments on the specified challenge.

### HTTP Request

`GET https://gametize.com/challenges/ID/comments.json`

<aside class="notice">Remember to replace "<code>ID</code>" with the desired challenge ID!</aside>

### Parameter(s)
Name | Usage | Default | Example | Description
---|---|---|---|---
page | optional | 1 | 1 | Specify which page of results to retrieve.
limit | optional | 10 | 5 | Specify the number of results to be returned on each page.

### Header(s)

Name | Usage | Default | Example | Description
---|---|---|---|---
Authorization | optional | null | Bearer 2073-02fde5e7-097a-4971-a4d4-de7154113ed7 | Get data pertaining to you. This includes whether you have voted and/or claimed the challenge.

## Leaderboard

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

> The above code returns JSON structured like this:

```json
{
  json: "example"
}
```
  
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
Authorization | optional | null | Bearer 2073-02fde5e7-097a-4971-a4d4-de7154113ed7 | Get data pertaining to you. This includes whether you have voted and/or claimed the challenge.

# Users<a name="users"></a>

## User Profile

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

> The above code returns JSON structured like this:

```json
{
  json: "example"
}
```

This endpoint retrieves the detailed profile of a user, specified by ID.

### HTTP Request

`GET https://gametize.com/api2/users/ID.json`

<aside class="notice">Remember to replace "<code>ID</code>" with the desired user's ID!</aside>

### Parameter(s)

Name | Usage | Default | Example | Description
---|---|---|---|---
bundle _id | optional | 0 | 3 | Get user data with respect to a specific project. 

### Header(s)

Name | Usage | Default | Example | Description
---|---|---|---|---
Authorization | optional | null | Bearer 2073-02fde5e7-097a-4971-a4d4-de7154113ed7 | Get data pertaining to you. This includes whether you have voted and/or claimed the challenge.

## Profile Widget

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

> The above code returns JSON structured like this:

```json
{
  template: "example"
}
```

This endpoint retrieves a profile overview of a user, specified by ID. 

### HTTP Request
`GET https://gametize.com/api2/users/ID/widget.json`

<aside class="notice">Remember to replace "<code>ID</code>" with the desired user's ID!"</aside>

### Parameter(s)
Name | Usage | Default | Example | Description
---|---|---|---|---
game_id | optional | 0 | 3 | Get user data with respect to a game.

### Header(s)
Name | Usage | Default | Example | Description
---|---|---|---|---
Authorization | optional | null | Bearer 2073-02fde5e7-097a-4971-a4d4-de7154113ed7 | Get data pertaining to you. This includes whether you have voted and/or claimed the challenge.

## Followers

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

> The above code returns JSON structured like this:

```json
{
  template: "example"
}
```

This endpoint retrieves a list of users **who follow the specified user**.

### HTTP Request
`GET https://gametize.com/users/ID/followers.json`

<aside class="notice"> Remember to replace "<code>ID</code>" with the desired user's ID!"</aside>

### Parameter(s)
Name | Usage | Default | Example | Description
---|---|---|---|---
page | optional | 1 | 1 | Specify which page of results to retrieve.
limit | optional | 10 | 5 | Specify the number of results to be returned on each page.

### Header(s)
Name | Usage | Default | Example | Description
---|---|---|---|---
Authorization | optional | null | Bearer 2073-02fde5e7-097a-4971-a4d4-de7154113ed7 | Get data pertaining to you. This includes whether you have voted and/or claimed the challenge.

## Following

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

> The above code returns JSON structured like this:

```json
{
  template: "example"
}
```

This endpoint retrieves a list of users **this user follows**.

### HTTP Request
`GET https://gametize.com/users/ID/following.json`

<aside class="notice"> Remember to replace "<code>ID</code>" with the desired user's ID!"</aside>

### Parameter(s)
Name | Usage | Default | Example | Description
---|---|---|---|---
page | optional | 1 | 1 | Specify which page of results to retrieve.
limit | optional | 10 | 5 | Specify the number of results to be returned on each page.

### Header(s)
Name | Usage | Default | Example | Description
---|---|---|---|---
Authorization | optional | null | Bearer 2073-02fde5e7-097a-4971-a4d4-de7154113ed7 | Get data pertaining to you. This includes whether you have voted and/or claimed the challenge.

## Claims

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

> The above code returns JSON structured like this:

```json
{
    "code": 200,
    "data": [
        {
            "bannerImage": "https://s3.amazonaws.com/AKIAIYM3HDTA72TUNOEQ.gamemaki/files/gametize/151165/photos/0_151165_1500611500726.jpg",
            "private": true,
            "teamEnabled": false,
            "description": "Welcome to the quest of becoming a Gametize Grandmaster. To begin, you must learn the ways of the Gametize Ninja to execute your duties with skill, swiftness and precision. \r\n\r\nComplete these tasks well and bring your team to victory. Fulfilling rewards await you. Good luck!",
            "id": 333,
            "title": "Onboarding Mission",
            "searchEnabled": false,
            "guestEnabled": false
        },
        {
            "bannerImage": "https://s3.amazonaws.com/AKIAIYM3HDTA72TUNOEQ.gamemaki/users/47182/challenges/0_47182_1484903143960.jpg",
            "private": false,
            "teamEnabled": false,
            "description": "This project contains a series of personality quiz demo games for reference.",
            "id": 1379,
            "title": "Personality Quiz Demo",
            "searchEnabled": false,
            "guestEnabled": false
        },
        {
            "bannerImage": "https://s3.amazonaws.com/AKIAIYM3HDTA72TUNOEQ.gamemaki/users/36404/challenges/0_36404_1394182239366.jpg",
            "private": false,
            "teamEnabled": false,
            "description": "Want to be more attractive in public, and charm the people around you? Unlock your charisma with this game! [Credits to Eric Feng].",
            "id": 140,
            "title": "The Charisma Game",
            "searchEnabled": false,
            "guestEnabled": false
        },
        {
            "bannerImage": "https://s3.amazonaws.com/AKIAIYM3HDTA72TUNOEQ.gamemaki/users/36304/challenges/0_36304_1449730608862.jpg",
            "private": false,
            "teamEnabled": false,
            "description": "What is Gametize? What exactly do we do, and who are the people behind Gametize? Get to know us better in this section. \r\n\r\nPsst, if you're looking for something specific, you might want to select a Topic Category, to help you in your search!",
            "id": 826,
            "title": "The Gametize Handbook",
            "searchEnabled": false,
            "guestEnabled": false
        },
        {
            "bannerImage": "https://s3.amazonaws.com/AKIAIYM3HDTA72TUNOEQ.gamemaki/users/47097/challenges/0_47097_1423654909811.png",
            "private": false,
            "teamEnabled": false,
            "description": "This is the World's simplest game to learn Gamification #truestory #gamedesignerin5mins",
            "id": 671,
            "title": "The World's Simplest Game",
            "searchEnabled": false,
            "guestEnabled": false
        }
    ],
    "more": false
}
```

The description of this API call goes here.

### HTTP Request
`GET https://gametize.com/users/ID/claims.json`

<aside class="notice"> Remember to replace "<code>ID</code>" with the desired template ID!"</aside>

### Parameter(s)
Name | Usage | Default | Example | Description
---|---|---|---|---
page | optional | 1 | 1 | Specify which page of results to retrieve.
limit | optional | 10 | 5 | Specify the number of results to be returned on each page.
filter | optional | null | image | Filter data based on content type. Available options: image.

### Header(s)
Name | Usage | Default | Example | Description
---|---|---|---|---
Authorization | optional | null | Bearer 2073-02fde5e7-097a-4971-a4d4-de7154113ed7 | Get data pertaining to you. This includes whether you have voted and/or claimed the challenge.

## Bundles

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

> The above code returns JSON structured like this:

```json
{
  template: "example"
}
```

This endpoints retrieves the list of bundles the user is participating/has participated in.

### HTTP Request
`GET https://gametize.com/template/ID/function.json`

<aside class="notice"> Remember to replace "<code>ID</code>" with the desired template ID!"</aside>

### Parameter(s)
Name | Usage | Default | Example | Description
---|---|---|---|---
page | optional | 1 | 1 | Specify which page of results to retrieve.
limit | optional | 10 | 5 | Specify the number of results to be returned on each page.

### Header(s)
Name | Usage | Default | Example | Description
---|---|---|---|---
Authorization | optional | null | Bearer 2073-02fde5e7-097a-4971-a4d4-de7154113ed7 | Get data pertaining to you. This includes whether you have voted and/or claimed the challenge.

## Accepts

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

> The above code returns JSON structured like this:

```json
{
  template: "example"
}
```

This endpoint retrieves a list of challenges that the user has **accepted**.

### HTTP Request
`GET https://gametize.com/users/ID/accepts.json`

<aside class="notice"> Remember to replace "<code>ID</code>" with the desired user's ID!"</aside>

### Parameter(s)
Name | Usage | Default | Example | Description
---|---|---|---|---
page | optional | 1 | 1 | Specify which page of results to retrieve.
limit | optional | 10 | 5 | Specify the number of results to be returned on each page.
bundle_id | optional | 0 | 3 | Filter the accepted challenges by a specific bundle.

### Header(s)
Name | Usage | Default | Example | Description
---|---|---|---|---
Authorization | optional | null | Bearer 2073-02fde5e7-097a-4971-a4d4-de7154113ed7 | Get data pertaining to you. This includes whether you have voted and/or claimed the challenge.

## Bookmarks

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

> The above code returns JSON structured like this:

```json
{
  template: "example"
}
```

This endpoint retrieves a list of challenges that the user has **bookmarked**.

### HTTP Request
`GET https://gametize.com/users/ID/bookmarks.json`

<aside class="notice"> Remember to replace "<code>ID</code>" with the desired user's ID!"</aside>

### Parameter(s)

Name | Usage | Default | Example | Description
---|---|---|---|---
page | optional | 1 | 1 | Specify which page of results to retrieve.
limit | optional | 10 | 5 | Specify the number of results to be returned on each page.
bundle_id | optional | 0 | 3 | Filter the bookmarked challenges by a specific bundle.

### Header(s)
Name | Usage | Default | Example | Description
---|---|---|---|---
Authorization | optional | null | Bearer 2073-02fde5e7-097a-4971-a4d4-de7154113ed7 | Get data pertaining to you. This includes whether you have voted and/or claimed the challenge.

## Items

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

> The above code returns JSON structured like this:

```json
{
  template: "example"
}
```

This endpoint retrieves a list of items **earned** by the user. 

### HTTP Request
`GET https://gametize.com/users/ID/items.json`

<aside class="notice"> Remember to replace "<code>ID</code>" with the desired user's ID!"</aside>

### Header(s)
Name | Usage | Default | Example | Description
---|---|---|---|---
Authorization | optional | null | Bearer 2073-02fde5e7-097a-4971-a4d4-de7154113ed7 | Get data pertaining to you. This includes whether you have voted and/or claimed the challenge.

## Items Purchased

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

> The above code returns JSON structured like this:

```json
{
  template: "example"
}
```

This endpoint gets the list of items **purchased** by the user. Note that the user is prohibited from viewing other users' purchased items.

### HTTP Request
`GET https://gametize.com/users/ID/items_purchased.json`

<aside class="notice"> Remember to replace "<code>ID</code>" with the desired user's ID!"</aside>

### Parameter(s)
Name | Usage | Default | Example | Description
---|---|---|---|---
page | optional | 1 | 1 | Specifies which page of results to retrieve.
limit | optional | 10 | 5 | Specify the number of results to be returned on each page.
bundle_id | optional | 0 | 3 | Filter the purchased items by a specific bundle.

### Header(s)
Name | Usage | Default | Example | Description
---|---|---|---|---
Authorization | **required** | null | Bearer 2073-02fde5e7-097a-4971-a4d4-de7154113ed7 | Get data pertaining to you. This includes whether you have voted and/or claimed the challenge.

<aside class="warning">Note that in this case the <code>session_key</code> for a user is <strong>REQUIRED</strong>! Failure to provide a valid session_key <b><em>will result in this API call failing</em></b>.</aside>

# Claims<a name="claims"></a>

# Games<a name="games"></a>

# Bundles<a name="bundles"></a>

# Notifications<a name="notifications"></a>

# Items<a name="items"></a>

# Teams<a name="teams"></a>

Actions<a name="actions"></a>

# Login<a name="login"></a>

# Action<a name="action"></a>

