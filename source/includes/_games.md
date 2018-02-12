# Games

<aside class="dev">Change the name of this endpoint/section to topic? Seems more straightforward and understandable for users <em>and</em> developers...</aside>

## Games Profile

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

This endpoint retrieves the detailed profile a specfic game.

<aside class="dev">Check if this endpoint is still accurate or needs to be revised.</aside>

### HTTP Request
`GET https://gametize.com/api2/games/ID.json`

<aside class="notice">Remember to replace "<code>ID</code>" with the desired game ID!"</aside>

### Header(s)
Name | Usage | Default | Example | Description
---|---|---|---|---
Authorization | optional | null | Bearer 2073-02fde5e7-097a-4971-a4d4-de7154113ed7 | Get data pertaining to you. This includes whether you have joined the game etc.

## Game Challenges

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

This endpoint retrieves a list of challenges in the specified game containing the specified keyword.

<aside class="success">Use this endpoint to searching for challenges containing a specific keyword.</aside>

### HTTP Request
`GET https://gametize.com/api2/games/ID/challenges.json`

<aside class="notice">Remember to replace "<code>ID</code>" with the desired game ID!"</aside>

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

## Game Claims

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

This endpoint retrieves a list of claims for all challenges in the specified game.

### HTTP Request

`GET https://gametize.com/api2/api2/games/ID/claims.json`

<aside class="notice">Remember to replace "<code>ID</code>" with the desired game ID!</aside>

### Parameter(s)
Name | Usage | Default | Example | Description
---|---|---|---|---
page | optional | 1 | 1 | Specify which page of results to retrieve.
limit | optional | 10 | 5 | Specify the number of results to be returned on each page.
user_id | optional | 0 | 2 | Get claims in respect to a particular user in the game.
filter | optional | null | image | Filter data based on content type. Available options: image.

### Header(s)
Name | Usage | Default | Example | Description
---|---|---|---|---
Authorization | optional | null | Bearer 2073-02fde5e7-097a-4971-a4d4-de7154113ed7 | Get data pertaining to you. This includes whether you have voted on the claim.

## Game Users

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

This endpoint retrieves a list of users specified game.

### HTTP Request

`GET https://gametize.com/api2/games/ID/users.json`

<aside class="notice">Remember to replace "<code>ID</code>" with the desired game ID!</aside>

### Parameter(s)
Name | Usage | Default | Example | Description
---|---|---|---|---
page | optional | 1 | 1 | Specify which page of results to retrieve.
limit | optional | 10 | 5 | Specify the number of results to be returned on each page.

### Header(s)
Name | Usage | Default | Example | Description
---|---|---|---|---
Authorization | optional | null | Bearer 2073-02fde5e7-097a-4971-a4d4-de7154113ed7 | Get data pertaining to you. This includes whether you have followed this user or if this user has followed you.

## Game Leaderboard

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

This endpoint retrieves a list of players on the leaderboard for the specified game.

### HTTP Request

`GET https://gametize.com/api2/games/ID/leaderboard.json`

<aside class="notice">Remember to replace "<code>ID</code>" with the desired game ID!</aside>

### Parameter(s)
Name | Usage | Default | Example | Description
---|---|---|---|---
page | optional | 1 | 1 | Specify which page of results to retrieve.
limit | optional | 10 | 5 | Specify the number of results to be returned on each page.

<aside class="dev">The 2.5.4 REST API Docs do not list <code>session_key</code> as one of the parameters for this HTTP request... Is this an error or is this accurate? Check with tech team...</aside>

## Game Leaderboard Overview

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

This endpoint retrieves the leaderboard overview of a game. Overview view types which my be returned include:
1. A single array of **Top 5** users if
  * User **is** in the top 5 or,
  * User has not earned any points.
2. An array of **Top 3** users *and* an array which includes the user's current position if
  * User **is not** in the top 5.

### HTTP Request

`GET https://gametize.com/api2/games/ID/leaderboard_overview.json`

<aside class="notice">Remember to replace "<code>ID</code>" with the desired game ID!</aside>

### Parameter(s)
Name | Usage | Default | Example | Description
---|---|---|---|---
user_id | required | 0 | 2 | Get the leaderboard overview with respect to a particular user in game.

<aside class="dev">Some params are still undocumented (as of 05/02/2018); consult Gametize library source code and update here.</aside>

<aside class="dev">The 2.5.4 REST API Docs do not list <code>session_key</code> as one of the parameters for this HTTP request... Is this an error or is this accurate? Check with tech team...</aside>

## Game Items

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

This endpoint retrieves the list of items **to be earned** in the specified game. Another user's ID may be specified if 

### HTTP Request

`GET https://gametize.com/api2/games/ID/items.json`

<aside class="notice">Remember to replace "<code>ID</code>" with the desired game ID!</aside>

### Parameter(s)
Name | Usage | Default | Example | Description
---|---|---|---|---
user_id | required | 0 | 2 | The user_id with respect to whom the items will be retrieved.

### Header(s)
Name | Usage | Default | Example | Description
---|---|---|---|---
Authorization | optional | null | Bearer 2073-02fde5e7-097a-4971-a4d4-de7154113ed7 | Get data pertaining to you. This includes whether you have earned this item or not.

## Game Comments

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

This endpoint retrieves the list of comments for the specified game.

### HTTP Request

`GET https://gametize.com/api2/games/ID/comments.json`

<aside class="notice">Remember to replace "<code>ID</code>" with the desired game ID!</aside>

### Parameter(s)
Name | Usage | Default | Example | Description
---|---|---|---|---
page | optional | 1 | 1 | Specify which page of results to retrieve.
limit | optional | 10 | 5 | Specify the number of results to be returned on each page.

<aside class="dev">The 2.5.4 REST API Docs do not list <code>session_key</code> as one of the parameters for this HTTP request... Is this an error or is this accurate? Check with tech team...</aside>
