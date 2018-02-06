# Users

## User Profile

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

This endpoint retrieves the detailed profile of a user, specified by ID.

### HTTP Request

`GET https://yourdomain/api2/users/ID.json`

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

This endpoint retrieves a profile overview of a user, specified by ID. 

### HTTP Request
`GET https://yourdomain/api2/users/ID/widget.json`

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

This endpoint retrieves a list of users **who follow the specified user**.

### HTTP Request
`GET https://yourdomain/users/ID/followers.json`

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

This endpoint retrieves a list of users **this user follows**.

### HTTP Request
`GET https://yourdomain/users/ID/following.json`

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

## User Claims

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

The description of this API call goes here.

### HTTP Request
`GET https://yourdomain/users/ID/claims.json`

<aside class="notice">Remember to replace "<code>ID</code>" with the desired template ID!"</aside>

### Parameter(s)
Name | Usage | Default | Example | Description
---|---|---|---|---
page | optional | 1 | 1 | Specify which page of results to retrieve.
limit | optional | 10 | 5 | Specify the number of results to be returned on each page.
filter | optional | null | image | Filter data based on content type. Available options: image.

### Header(s)
Name | Usage | Default | Example | Description
---|---|---|---|---
Authorization | optional | null | Bearer 2073-02fde5e7-097a-4971-a4d4-de7154113ed7 | Get data pertaining to you. This includes whether you have voted on the claim.

## Joined Bundles

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

This endpoints retrieves the list of bundles the user is participating/has participated in.

### HTTP Request
`GET https://yourdomain/template/ID/function.json`

<aside class="notice">Remember to replace "<code>ID</code>" with the desired template ID!"</aside>

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

This endpoint retrieves a list of challenges that the user has **accepted**.

### HTTP Request
`GET https://yourdomain/users/ID/accepts.json`

<aside class="notice">Remember to replace "<code>ID</code>" with the desired user ID!"</aside>

### Parameter(s)
Name | Usage | Default | Example | Description
---|---|---|---|---
page | optional | 1 | 1 | Specify which page of results to retrieve.
limit | optional | 10 | 5 | Specify the number of results to be returned on each page.
bundle_id | optional | 0 | 3 | Filter the accepted challenges by a specific bundle.

### Header(s)
Name | Usage | Default | Example | Description
---|---|---|---|---
Authorization | optional | null | Bearer 2073-02fde5e7-097a-4971-a4d4-de7154113ed7 | Get data pertaining to you. This includes whether you have claimed the challenge.

## Bookmarked Challenges

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

This endpoint retrieves a list of challenges that the user has **bookmarked**.

### HTTP Request
`GET https://yourdomain/users/ID/bookmarks.json`

<aside class="notice">Remember to replace "<code>ID</code>" with the desired user ID!"</aside>

### Parameter(s)

Name | Usage | Default | Example | Description
---|---|---|---|---
page | optional | 1 | 1 | Specify which page of results to retrieve.
limit | optional | 10 | 5 | Specify the number of results to be returned on each page.
bundle_id | optional | 0 | 3 | Filter the bookmarked challenges by a specific bundle.

### Header(s)
Name | Usage | Default | Example | Description
---|---|---|---|---
Authorization | optional | null | Bearer 2073-02fde5e7-097a-4971-a4d4-de7154113ed7 | Get data pertaining to you. This includes whether you have claimed the challenge.

## Earned Items

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

This endpoint retrieves a list of items **earned** by the user. 

### HTTP Request
`GET https://yourdomain/users/ID/items.json`

<aside class="notice">Remember to replace "<code>ID</code>" with the desired user ID!"</aside>

### Header(s)
Name | Usage | Default | Example | Description
---|---|---|---|---
Authorization | optional | null | Bearer 2073-02fde5e7-097a-4971-a4d4-de7154113ed7 | Get data pertaining to you. This includes whether you have earned this item or not.

## Purchased Items

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

This endpoint gets the list of items **purchased** by the user. Note that the user is prohibited from viewing other users' purchased items.

### HTTP Request
`GET https://yourdomain/users/ID/items_purchased.json`

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
