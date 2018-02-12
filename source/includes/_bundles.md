# Bundles

<aside class="dev">Rename this section to "<strong>Project</strong>"? This is presumably more familiar terminology for the end user to recognise.</aside>

## Bundle Games

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

This endpoint retrieves a list of games in the specified bundle.

### HTTP Request
`GET https://gametize.com/api2/bundles/ID/game.json`

<aside class="notice">Remember to replace "<code>ID</code>" with the desired bundle ID!</aside>

### Parameter(s)

Name | Usage | Default | Example | Description
---|---|---|---|---
page | optional | 1 | 1 | Specify which page of results to retrieve.
limit | optional | 10 | 5 | Specify the number of results to be returned on each page.

### Header(s)

Name | Usage | Default | Example | Description
---|---|---|---|---
Authorization | optional | null | Bearer 2073-02fde5e7-097a-4971-a4d4-de7154113ed7 | Get data pertaining to you. This includes whether you have joined the game.

## Bundle Challenges

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

This endpoint returns a list of challenges in the specified bundle.

<aside class="success">Use this API call to search for challenges, using the useful <code>keywords</code> parameter!</aside>

### HTTP Request
`GET https://gametize.com/api2/bundles/ID/challenges.json`

<aside class="notice">Remember to replace "<code>ID</code>" with the desired bundle ID!</aside>

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

## Bundle Claims

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

This endpoint returns a list of claims for all challenges in the specified bundle.

### HTTP Request
`GET https://gametize.com/api2/bundles/ID/claims.json`

<aside class="notice">Remember to replace "<code>ID</code>" with the desired bundle ID!</aside>

### Parameter(s)
Name | Usage | null | Example | Description
---|---|---|---|---
page | optional | 1 | 1 | Specify which page of resultts to retrieve.
limit | optional | 10 | 5 | Specify the number of results to be returned on each page.
type | optional | null | following | Get claims in respect to certain classification for the logged in user (session_key is required). Available options: following.
filter | optional | null | image | filter data based on content type. Available options: image.
user_id | **required** | 0 | 2 | Get claims in respect to a particular user in the bundle.

<aside class="warning">Note that in this case the <code>user_id</code> parameter is <strong>REQUIRED</strong>! <br>Failure to provide a <code>user_id</code> parameter <b><em>will result in this API call failing</em></b>.</aside>

### Header(s)
Name | Usage | Default | Example | Description
---|---|---|---|---
Authorization | optional | null | Bearer 2073-02fde5e7-097a-4971-a4d4-de7154113ed7 | Get data with respect to you. This includes whether you have voted on the claim.

## Bundle Items

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

This endpoint retrieves a list of items in the specified bundle with respect to the a user. 

### HTTP Request
`GET https://gametize.com/api2/bundles/ID/items.json`

<aside class="notice">Remember to replace "<code>ID</code>" with the desired bundle ID!</aside>

### Parameter(s)
Name | Usage | null | Example | Description
---|---|---|---|---
user_id | **required** | 0 | 2 | Get claims in respect to a particular user in the bundle.

<aside class="warning">Note that in this case the <code>user_id</code> parameter is <strong>REQUIRED</strong>! <br>Failure to provide a <code>user_id</code> parameter <b><em>will result in this API call failing</em></b>.</aside>

### Header(s)
Name | Usage | Default | Example | Description
---|---|---|---|---
Authorization | optional | null | Bearer 2073-02fde5e7-097a-4971-a4d4-de7154113ed7 | Get data with respect to you. This includes whether you have earned this item or not.

## Bundle Store

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

This endpoint retrieves a list of **purchasable** items in a bundle.

### HTTP Request
`GET https://gametize.com/api2/bundles/ID/store.json`

<aside class="notice">Remember to replace "<code>ID</code>" with the desired bundle ID!</aside>

### Paramater(s)
Name | Usage | Default | Example | Description
---|---|---|---|---
page | optional | 1 | 1 | Specify which page of resultts to retrieve.
limit | optional | 10 | 5 | Specify the number of results to be returned on each page.

### Header(s)
Name | Usage | Default | Example | Description
---|---|---|---|---
Authorization | optional | null | Bearer 2073-02fde5e7-097a-4971-a4d4-de7154113ed7 | Get data with respect to you. This includes whether you have earned this item or not.

## Bundle Users

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

This endpoint retrieves a list of users in the specified bundle.

### HTTP Request
`GET https://gametize.com/api2/bundles/ID/users.json`

<aside class="notice">Remember to replace "<code>ID</code>" with the desired bundle ID!</aside>

### Parameter(s)
Name | Usage | Default | Example | Description
---|---|---|---|---
page | optional | 1 | 1 | Specify which page of resultts to retrieve.
limit | optional | 10 | 5 | Specify the number of results to be returned on each page.

### Header(s)
Name | Usage | Default | Example | Description
---|---|---|---|---
Authorization | optional | null | Bearer 2073-02fde5e7-097a-4971-a4d4-de7154113ed7 | Get data with respect to you. This includes whether you have followed this user or if this user has followed you.

## Bundle Teams

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

This endpoint retrieves a list of teams in the specified bundle.

### HTTP Request
`GET https://gametize.com/api2/bundles/ID/teams.json`

<aside class="notice">Remember to replace "<code>ID</code>" with the desired bundle ID!</aside>

### Parameter(s)
Name | Usage | Default | Example | Description
---|---|---|---|---
page | optional | 1 | 1 | Specify which page of resultts to retrieve.
limit | optional | 10 | 5 | Specify the number of results to be returned on each page.

### Header(s)
Name | Usage | Default | Example | Description
---|---|---|---|---
Authorization | optional | null | Bearer 2073-02fde5e7-097a-4971-a4d4-de7154113ed7 | Get data with respect to you.

## Validate User

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

This endpoint retrieves the bundle status with respect to a logged-in user. 

### HTTP Request
`GET https://gametize.com/api2/bundles/(ID or ALIAS)/validate.json`

<aside class="notice">Remember to replace "<code>ID</code>" with the desired bundle ID or alias!</aside>

### Header(s)
Name | Usage | Default | Example | Description
---|---|---|---|---
Authorization | **required** | null | Bearer 2073-02fde5e7-097a-4971-a4d4-de7154113ed7 | Get data with respect to you.

<aside class="warning">Note that in this case the <code>session_key</code> parameter is <strong>REQUIRED</strong>! <br>Failure to provide a <code>session_key</code> parameter <b><em>will result in this API call failing</em></b>.</aside>
