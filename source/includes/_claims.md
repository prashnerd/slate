# Claims

## Claim Profile

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

This endpoint retrieves the detailed profile of a specific claim.

### HTTP Request
`GET https://yourdomain/claims/ID.json`

<aside class="notice">Remember to replace "<code>ID</code>" with the desired claim ID!"</aside>

### Header(s)
Name | Usage | Default | Example | Description
---|---|---|---|---
Authorization | optional | null | Bearer 2073-02fde5e7-097a-4971-a4d4-de7154113ed7 | Get data pertaining to you. This includes whether you have voted on the claim.

## Claim Comments

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

This endpoint retrieves a list of comments on the specified claim.

### HTTP Request
`GET https://yourdomain/users/ID/bookmarks.json`

<aside class="notice">Remember to replace "<code>ID</code>" with the desired claim ID!"</aside>

### Parameter(s)

Name | Usage | Default | Example | Description
---|---|---|---|---
page | optional | 1 | 1 | Specify which page of results to retrieve.
limit | optional | 10 | 5 | Specify the number of results to be returned on each page.

### Header(s)
Name | Usage | Default | Example | Description
---|---|---|---|---
Authorization | optional | null | Bearer 2073-02fde5e7-097a-4971-a4d4-de7154113ed7 | Get data pertaining to you.

<aside class="dev">The 2.5.4 REST API Docs do not list <code>session_key</code> as one of the parameters for this HTTP request... Is this an error or is this accurate? Check with tech team...</aside>
