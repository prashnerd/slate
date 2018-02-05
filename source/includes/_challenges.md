# Challenges

Challenges are the lowest level of categorization for the Gametize platform. Challenges are activities for the user to complete, which can range from submitting a photograph and/or a text comment (*Standard Challenges*) to simply clicking on a button (*Confirmation Challenges*) to scanning a QR code (*QR Challenges*).

When a User completes a challenge, it referred to as a "**claim**"". Claims can vary depending on the challenge type, since it depends on what the user has to submit to complete the challenge.

If a challenge is set to have non-private completions, users may view other users' activity, which allow them to vote and comment on those users' completions.

Collecting the data from claims, votes and comments on a challenge can be a rather slow operation if the project has a lot of users/activity. 

<aside class="quote"><em>It's a happy problem.</em> - <strong>Damon Widjaja, Co-founder of Gametize</strong></aside>

## Challenge Profile

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

```shell
```

```javascript
```

>The above code returns JSON structured like this:

```json
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
Authorization | optional | null | Bearer 2073-02fde5e7-097a-4971-a4d4-de7154113ed7 | Get data pertaining to you. This includes whether you have voted on the claim.

## Challenge Comments

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
